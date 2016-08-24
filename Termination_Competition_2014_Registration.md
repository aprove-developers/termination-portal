---
title: Termination Competition 2014 Registration
permalink: /Termination_Competition_2014_Registration/
---

Procedure
---------

Registration (by June 15)

-   get an account on starexec
-   send to the organizer, in email, the name of your solver and the categories that you want to enter

Solver pre-submission (by June 22) and submission (by July 1)

-   upload your solver to starexec. In your solver description on starexec, give: name of solver, name and affiliation of (main) author(s), URL for more detail.
-   send to J. Waldmann, in email, for each of your categories, the pair of solver-id and configuration-id, and grant read access on star-exec. You can send preliminary id pairs, you can update them until July 1.

Benchmark submission (by July 1)

-   upload benchmarks on starexec (in some subspace of your space)
-   send to R. Thiemann, in email, the pathname of this subspace, and grant read access on star-exec.

Note: for granting access: create a subspace of your space, put your solver/benchmarks there, and copy the respective user to this subspace. ( <http://starexec.forumotion.com/t80-how-can-the-space-leader-use-non-public-solvers#189> ) We will then link to your solver. (Beware of <http://starexec.forumotion.com/t97-no-recycling-for-things-that-are-still-referenced> )

Participants
------------

update Mon Jun 23 13:37:26 CEST 2014

announcement: <http://lists.lri.fr/pipermail/termtools/2014-June/000958.html>

check this page for current registration data: <http://nfa.imn.htwk-leipzig.de/termcomp/registered>

the following is for historic reference only:

registrations, by (meta-)categories. last updated Tue Jun 17 10:24:51 CEST 2014

(This list to be edited by the competition organizer only. Please send email in case of any errors or omissions.)

-   Termination of Term Rewriting (and Transition Systems)
    -   TRS Standard: TTT2, NaTT, AProVE, Wanda, muterm
    -   SRS Standard: TTT2, NaTT, AProVE, muterm
    -   TRS Relative: TTT2, AProVE
    -   SRS Relative: TTT2, AProVE
    -   TRS Standard certified: TTT2, matchbox, AProVE
    -   SRS Standard certified: TTT2, matchbox, AProVE
    -   TRS Relative certified: TTT2, AProVE
    -   SRS Relative certified: TTT2, AProVE
    -   TRS Equational: AProVE, muterm
    -   TRS Conditional: AProVE, muterm
    -   TRS Context Sensitive: AProVE, muterm
    -   TRS Innermost: AProVE, muterm
    -   TRS Outermost: AProVE
    -   TRS Innermost certified: AProVE
    -   TRS Outermost certified: AProVE
    -   Higher-Order rewriting (union beta): Wanda, THOR
    -   integer transition systems: T2, AProVE, Ctrl
    -   Integer TRS: AProVE, Ctrl

-   Complexity Analysis of Term Rewriting
    -   Derivational Complexity - Full Rewriting: TCT, CaT
    -   Runtime Complexity – Full Rewriting: TCT, CaT
    -   Runtime Complexity – Innermost Rewriting: TCT, AProVE
    -   Derivational Complexity - Full Rewriting certified: CaT
    -   Runtime Complexity – Full Rewriting certified: CaT
    -   Runtime Complexity – Innermost Rewriting certified: AProVE

-   Termination of Programming Languages
    -   C: AProVE, T2, Ultimate Buchi Automizer, lsi.upc tool
    -   Java: AProVE, Julia
    -   Logic Programming: AProVE
    -   Functional Programming: AProVE

-   Verification of Termination of Term Rewriting
    -   TRS Standard: CeTA, Rainbow
    -   TRS Relative: CeTA
    -   TRS Innermost: CeTA
    -   TRS Outermost: CeTA
    -   TRS Conditional: CeTA
    -   TRS Context-Sensitive: CeTA
    -   SRS Standard: CeTA
    -   SRS Relative: CeTA

-   Verification of Complexity Analysis of Term Rewriting:
    -   Derivational Complexity - Full Rewriting: CeTA
    -   Runtime Complexity – Full Rewriting: CeTA

Note on Certified Categories
----------------------------

-   Participants of a certified category need to state which verifier they are targetting (it could be several).
-   Writers of verifiers need to state the syntax and semantics of the certificates that they are accepting (e.g., by publishing their verifier specification and/or implementation, with exact version information)
    -   CeTA will use version 2.15, see <http://cl-informatik.uibk.ac.at/software/ceta/>

Note: on starexec, you can choose "ceta-postproc" to get immediate verification (by an earlier CeTA version, and with some extra problems, see <https://github.com/jwaldmann/ceta-postproc/issues> )

new benchmarks
--------------

-   TRS Standard
    -   hydra (submitted by Harald Zankl)
-   C Programs
    -   208 examples (submitted by Thomas Ströder) <http://lists.lri.fr/pipermail/termtools/2014-June/000957.html>
-   integer transition systems
    -   examples (generated from the JBC examples via AProVE Termination Graphs) are available under ID "34547" (Marc Brockschmidt)
