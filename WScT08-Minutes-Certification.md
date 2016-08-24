---
title: WScT08-Minutes-Certification
permalink: /WScT08-Minutes-Certification/
---

(These are minutes of the meeting. Please do not edit this page except for correcting obvious mistakes. Make links to separate pages for further discussions.)

-   Notation:
    -   TCG is Termination Certificate Grammar
    -   Rainbow is the translator from TCG, with several backends (one for Color, one for Isabelle)
    -   Another format and another translator is CiME from A3PAT
    -   what's the file extension (.tc, .tcg, .tcf, .xml?)
        -   .xtc (xml termination certificate)
    -   introduce version names/numbers for the format and for the translator(s) (in the .xtc, versioning is by using the proper namespace)

-   extend TCG format towards common format:
    -   make nodes (more) self-contained
    -   have system (termination problem) in each node

-   DG Approx, SCC analysis
    -   give topologically sorted list of SCCs (A3PAT handles graphs and requests this list)
    -   have certificate for each missing edge (allow different kinds of certificates)

-   want to certify non-termination
    -   proposal: new top element: disproof
    -   certify loops (is leaf in proof tree)
        -   loop has: start term, sequence of steps, final position (and substitution?)
        -   step has: position, rule (and substitution?)
    -   later: other nodes in non-termination-proof trees?

-   extend polynomial and (standard) matrix interpretations to rational domain (new XML node types rational-polynomial-interp and rational-matrix-interp)
    -   a rational number is an XML node (enum, denom)
    -   need to provide the delta for the ordering

-   apply argument filtering on ordering
    -   currently, manna-ness has ordering, we want to allow argument-filtering-of-ordering there

-   direct checking of TPG trees (no formal verification) might be useful for testing extensions (Christian has a prototype ([microTTT](/microTTT "wikilink")) but not exactly for Rainbow)

-   re-use in Color some theorems proved in Coccinelle
    -   e.g. prover termination by innermost termination (if nonoverlapping)
    -   modular termination (?)
    -   perhaps have a general transformation (back and forth)

-   plan: generate Isabelle proof from TPG tree
