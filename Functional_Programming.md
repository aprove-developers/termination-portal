---
title: Functional Programming
permalink: /Functional_Programming/
---

Within the Termination Competition, there is a category on Functional Programming where the object is to prove termination of Haskell functions automatically.

Currently, the Termination Problems Data Base contains 1676 functions from the Haskell Prelude, and AProVE shows termination of 1294 of them.

Termination of Haskell Functions
--------------------------------

This category compares tools that automatically analyze termination of Haskell programs. If one considers a whole Haskell program, termination corresponds to finishing the computation in finite time on every possible input. Since Haskell uses lazy/on-demand evaluation, this notion is not directly useful for analysis of single functions. Consider for example a program containing:

    map :: (a -> b) -> [a] -> [b]
    map f [] = []
    map f (x:xs) = (f x):(map f xs)

    bot :: a -> b
    bot = bot

    zeros :: [Integer]
    zeros = 0:zeros

    strange :: (Integer -> Integer) -> Integer
    strange f
        | f 23 == 42    = strange f
        | otherwise     = 5

Intuitively a specific function evaluation (where the value of every argument is supplied) is terminating if the Haskell evaluation strategy needs finitely many steps to compute the result completely. This means, that evaluation does not stop when reaching a term headed by a constructor: it will continue evaluating the arguments of this constructor. Hence, the function zeros is considered non-terminating.

When analyzing the termination behavior of a function itself (without specific arguments), the picture gets slightly more complicated. If one allows arbitrary arguments, then nearly every Haskell function will not finish in finitely many steps. Even a function as head would need to be considered non-terminating if one would allow non-terminating arguments: head bot will obviously not terminate. Hence, this idea is not useful. Instead one regards a function as terminating, if it finishes in a finite number of steps whenever it is called with terminating arguments. This can be written formally as follows:

**Definition: (Termination of Haskell Expressions)** The set of terminating Haskell expressions is defined as the smallest set, such that t is in this set iff:

-   t does not start an infinite evaluation sequence, and
-   if t evaluates to an expression c t<sub>1</sub> ... t<sub>n</sub> where c is a constructor then t<sub>1</sub> ... t<sub>n</sub> must also be terminating expressions, and
-   if t evaluates to an expression f t<sub>1</sub> ... t<sub>n</sub> where f is a function symbol and the type of t is α -\> β, then f t<sub>1</sub> ... t<sub>n</sub> t' must be terminating for every terminating expression t'.

This means that in the above program the expression `map` would be considered terminating, while the expression `\f -> map f zeros` would be non-terminating. On the other hand head `zeros` is obviously nonterminating. The expression `\x -> if x == 23 then 42 else 5` is terminating, while the function `strange` is not. This is because by the third point in the definition one needs to analyze strange called with any terminating argument (like our lambda expression) which would result in a non-terminating behavior.

The semantics of "termination" (in the context of the competition) is discussed e.g. in <http://lists.lri.fr/pipermail/termtools/2006-March/000179.html>

The Problem Format
------------------

Every input for the FP category is a file containing a Haskell module with exactly the compiler pragma `htermination`, that specifies the start term. The start term is any Haskell expression containing no free variables. Function names, constructors etc. bound in the module itself can be used.

    {-# htermination (foldr1 :: (a -> a -> a) -> (List a) -> a) #-}

    import qualified Prelude

    data MyBool = MyTrue | MyFalse
    data List a = Cons a (List a) | Nil

    foldr1 :: (a -> a -> a) -> (List a) -> a
    foldr1 f (Cons x Nil) = x
    foldr1 f (Cons x xs) = f x (foldr1 f xs)

Implementations
---------------

The termination analyzer AProVE has a web front end <http://aprove.informatik.rwth-aachen.de/eval/Haskell/>

[Category:Categories](/Category:Categories "wikilink")
