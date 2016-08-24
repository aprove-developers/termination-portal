---
title: Logic Programming
permalink: /Logic_Programming/
---

This page is to record the current status of discussion on cleaning up the Logic Programming Category of the Termination Competition.

(Discussion should take place on the termtools mailing list.)

Syntax/Semantics for Input/Output
---------------------------------

The set of queries, for which termination should be analyzed, is given by a comment of the form "%query: <predicate>(<arguments>).". Here, <predicate> is the root symbol of all queries to analyze while <arguments> is a comma-separated list of argument indicators which specify whether the argument at the particular position must be a ground term or can be an arbitrary term. There are three pairs of argument indicators in use (historically grown) where the first indicator specifies ground arguments and the second specifies arbitrary arguments: i and o (for input and output), b and f (for bound and free), and g and a (for ground and any). Example:

%query: p(i,o).

This means all queries :- p(s,t). where s is a ground term and t can be any term. If the root symbol has no arguments, the parantheses are omitted. Example:

%query: p.

Problematic Examples
--------------------

The following examples are empty:

-   LP/talp/apt/dc_mod.pl
-   LP/talp/apt/gt_mod.pl

The following examples contain non-trivial built-in predicates that are potentially handled in very different ways by the individual tools (leading to potentially different termination status):

-   LP/lpexamples/factorial.pl
-   LP/lpexamples/fib-oi.pl
-   LP/lpexamples/fib.pl
-   LP/lpexamples/hanoi.pl
-   LP/lpexamples/kay4.pl
-   LP/lpexamples/numbervars.pl
-   LP/lpexamples/primes.pl
-   LP/lpexamples/tautology.pl
-   LP/lpexamples/totient.pl
-   LP/talp/apt/curry_ap.pl
-   LP/talp/apt/dc_mod.pl
-   LP/talp/apt/dc_schema.pl
-   LP/talp/apt/gt_mod.pl
-   LP/talp/apt/gtsolve.pl
-   LP/talp/apt/mergesort_ap_variant.pl
-   LP/talp/maria/aiakl.pl
-   LP/talp/maria/ann.pl
-   LP/talp/maria/bid.pl
-   LP/talp/maria/boyer.pl
-   LP/talp/maria/browse.pl
-   LP/talp/maria/deriv-oii.pl
-   LP/talp/maria/deriv.pl
-   LP/talp/maria/fib.pl
-   LP/talp/maria/grammar.pl
-   LP/talp/maria/grammar2.pl
-   LP/talp/maria/hanoiapp.pl
-   LP/talp/maria/mmatrix.pl
-   LP/talp/maria/money.pl
-   LP/talp/maria/occur.pl
-   LP/talp/maria/peephole.pl
-   LP/talp/maria/progeom.pl
-   LP/talp/maria/qplan.pl
-   LP/talp/maria/qsortapp.pl
-   LP/talp/maria/query.pl
-   LP/talp/maria/rdtok.pl
-   LP/talp/maria/read.pl
-   LP/talp/maria/serialize.pl
-   LP/talp/maria/tak.pl
-   LP/talp/maria/tictactoe.pl
-   LP/talp/maria/warplan.pl
-   LP/talp/taboch/permute2.pl
-   LP/talp/taboch/queens.pl
-   LP/terminweb/old-terminweb/mergesort.pl
-   LP/terminweb/old-terminweb/queens.pl
-   LP/terminweb/old-terminweb/quicksort.pl

Questions
---------

-   should empty examples be removed?
-   how to handle built-ins that the tool does not support?
-   do we want to have a (sub-)category "pure logic programs"?

Unification with or without Occurs Check
----------------------------------------

Currently, there are some examples in the LP-Prolog category where termination depends on whether unification is performed with or without the occurs check. Following the treatment of overflows in the Java categories, in such cases both YES and NO answers (with consistent proofs) are valid.

Participants
------------

The following is a list of participants to this category

-   [Tools:AProVE](/Tools:AProVE "wikilink")

[Category:Categories](/Category:Categories "wikilink")
