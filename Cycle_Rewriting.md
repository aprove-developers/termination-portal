---
title: Cycle Rewriting
permalink: /Cycle_Rewriting/
---

Introduction
------------

A cycle can be seen as a string of which the left end is connected to the right end, by which the string has no left end or right end any more. For instance, all of the strings abcd, bcda, cdab, dabc represent the same cycle.

Cycle rewriting applies [string rewrite rules](http://www.termination-portal.org/wiki/String_Rewriting) to cycles.

For instance, the string rewrite rule bc → cac can be applied to the cycle represented by the string cdab resulting in dacac.

Termination of a cycle rewrite relation means that there does not exist a cycle which has an infinite derivation using cycle rewrite steps. Cycle termination is different from termination of string rewrite systems, since e.g. the system R={ab → ba} is terminating as a string rewrite system, but it is not cycle-terminating, since ab and ba represent the same cycle. An example for a cycle-terminating system is {aa → aba}.

Formal Definition of Cycles and Cycle Rewriting
-----------------------------------------------

### Cycles

Let Σ be an alphabet. Two strings u,v ∈ Σ<sup>\*</sup> represent the same cycle (u ∼ v) iff there exist strings w<sub>1</sub>,w<sub>2</sub> such that u = w<sub>1</sub>w<sub>2</sub> and v = w<sub>2</sub>w<sub>1</sub>.

A <strong>cycle</strong> is an equivalence class w.r.t. ∼.

We write [u] for such an equivalence class with representative u.

### Cycle Rewriting

Let R = {l<sub>1</sub> → r<sub>1</sub>,...,l<sub>n</sub> → r<sub>n</sub>} be a string rewrite system. The cycle rewrite relation of R o‍→<sub>R</sub> is: [u] o‍→<sub>R</sub> [v] iff ∃w∈Σ<sup>\*</sup>: u ∼ lw, (l → r) ∈ R, and v ∼ rw

### Cycle Termination

A cycle rewrite relation o‍→<sub>R</sub> is non-terminating iff there exists an infinite sequence of cycle rewrite steps, i.e. there exist strings u<sub>1</sub>,u<sub>2</sub>,... ∈Σ<sup>\*</sup> s.t. [u<sub>i</sub>] o‍→<sub>R</sub> [u<sub>i+1</sub>] for all i.

A cycle rewrite relation o‍→<sub>R</sub> is terminating iff it is not non-terminating.

Input Format for Cycle Termination Provers
------------------------------------------

Every termination problem for [string rewrite systems](http://www.termination-portal.org/wiki/String_Rewriting) is also a termination problem for cycle rewrite systems. The input format for provers is the same as for string rewrite systems (problems can be found in the [TPDB](http://termination-portal.org/wiki/TPDB)).

Implementations
---------------

An approach to prove cycle termination using trace-decreasing matrix interpretations is implemented in the tool [torpacyc](http://www.win.tue.nl/~hzantema/torpa.html). Another approach is to reduce cycle termination to string termination by a sound and complete transformation and then applying a termination prover for termination of string rewrite systems. Several of those transformations and combinations of these techniques and [torpacyc](http://www.win.tue.nl/~hzantema/torpa.html) are included in the tool [cycsrs](http://www.ki.informatik.uni-frankfurt.de/research/cycsrs/) which can also be used [online](http://www.ki.informatik.uni-frankfurt.de/research/cycsrs/cgi/prove).

Further Reading
---------------

Cycle rewriting was introduced in [[1](/#ZBK14 "wikilink")] where its complexity was analyzed and termination techniques using arctic and tropical matrix interpretations based on type graphs were developed.

In [[2](/#SZ "wikilink")] further termination techniques for cycle termination were introduced: trace-decreasing matrix interpretations as well as sound and complete transformations from cycle to string termination.

### References

:\#<span id="ZBK14"></span> H. Zantema, H.J.S. Bruggink and B. Koenig, [Termination of cycle rewriting](http://dx.doi.org/10.1007/978-3-319-08918-8_33), Proceedings of Joint International Conference, RTA-TLCA 2014, Vienna, Austria, July 14-17, 2014 Springer Lecture Notes in Computer Science 8560, pages 476-490

:\#<span id="SZ15"></span> David Sabel and Hans Zantema. [Transforming Cycle Rewriting into String Rewriting.](http://drops.dagstuhl.de/opus/volltexte/2015/5203) In Maribel Fernández, editor, 26th International Conference on Rewriting Techniques and Applications (RTA 2015), volume 36 of Leibniz International Proceedings in Informatics (LIPIcs), pages 285-300, Dagstuhl, Germany, June 2015. Schloss Dagstuhl-Leibniz-Zentrum fuer Informatik.

[Category:Categories](/Category:Categories "wikilink")
