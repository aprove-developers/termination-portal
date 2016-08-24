---
title: Higher Order Rewriting
permalink: /Higher_Order_Rewriting/
---

General conditions:

- Allow lambda binders.

- Use Church simply type lambda calculus without type variables. No type constructors by now.

- Same type for both sides of the rule.

- Typability is guaranteed.

- Function declaration distinguishes between input (argument) types and the output type. The input and output types can be functional (include arrows). As an example

` f: (int , int , (int -> int) ) -> (int->int)`

has three input types (where the third one is functional) and a functional output. Thus if a:int then we can have

` (f(a,a,\lam x.a) a) `

as a term. Functions can only be used with all its arguments. For writing examples in applicative form, one can define f as:

` f: () -> (int -> int -> (int -> int) -> int -> int)`

then the term would be

` (f a a \lam x.a a) `

Categories:

- Rewriting with matching modulo alpha and union beta.

- Rewriting with higher-order pattern matching on beta-normal eta-long forms (HRS). In this case, left and right hand sides are assumed to be normalized.

- Other categories may be considered in the near future. For instance, we can add STTRS and use the problem families without binders, but with a different semantics.

- We postpone certification for the future.

Syntax:

A precise syntax following the standards of the TPDB will be defined very soon.

Comments are welcome.

Albert

[Category:Categories](/Category:Categories "wikilink")
