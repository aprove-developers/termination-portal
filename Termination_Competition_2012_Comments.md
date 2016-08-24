---
title: Termination Competition 2012 Comments
permalink: /Termination_Competition_2012_Comments/
---

Participants and observers may put their comments here. These could be used when a report on the competition is prepared.

SRS Certified
=============

-   machbox-cert gets a "failed validation" [here](http://termcomp.uibk.ac.at/termcomp/competition/resultDetail.seam?resultId=402459&cid=39568). What happened? It prints YES on stdout, but then CPF output raises an exception because a pattern for RIsEmpty is missing [here](http://dfa.imn.htwk-leipzig.de/cgi-bin/gitweb.cgi?p=tpdb.git;a=blob;f=TPDB/CPF/Proof/Xml.hs;h=8cd244666cc1b7f7ea8dc435534f74130ae7bd3f;hb=HEAD#l85). Obviously the author did not believe that any of the problems could be solved by linear additive weights alone ...
-   matchbox-cert has a higher score (108) than matchbox-uncert (103) which is interesting. Johannes, can you please explain.
-   AProVE-CeTA gets a "failed validation" [here](http://termcomp.uibk.ac.at/termcomp/competition/resultDetail.seam?resultId=404090&cid=108046). The reason is that AProVE used some additional inference rules that are not described in their IJCAR'12 paper on non-looping non-terminating derivations.
-   AProVE and AProVE-CeTA have the same YES-count (141) which shows that the restriction to certifiable techniques imposes a neglectable restriction for SRSs. For NO-answers, AProVE beats AProVE-Cert due to the use of an uncertified technique to find non-looping non-terminating derivations of Oppelt08 (which however in several examples just detected a loop).

Complexity Certified
====================

This year, for the first time, complexity proofs can also be provided in the standardized CPF format which allows for certification. Here, TcT-Cert ant CaT-Cert and restricted versions of TcT and CaT which only use techniques that are currently supported by CeTA, i.e.: rule-shifting using matrix-interpretations over the naturals or the rationals. Clearly, this is a severe restriction in the configuration of the tools. The consequences are however not always severe:

-   For **Derivational Complexity - Full Rewriting**, the certified tools already achieve over 62 % of the score of the uncertified tools. Some examples could not be handled at all (the main missing techniques seems to be matchbounds) and for some TRSs the derived complexity is just higher (currently CeTA can only infer the dimension of a triangular matrix interpretation as degree of the complexity.)
-   For **Derivational Complexity - Innermost**, the difference in score is much higher: the certified tool got around 39 % of the uncertified tool. This is explained easily since one additional missing technique is often applied on these examples: the removal of useless rules, i.e., rules which are never applicable since some argument of the left-hand side contains already a redex (which in my opinion (RT) shows that these examples are not really intended for innermost rewriting).
-   For **Runtime Complexity** the certifiers clearly miss Dependency Pairs and related techniques and here the difference in score is highest: the certified tool got only 35 % for full rewriting and 20 % for innermost rewriting of the score in comparison to the uncertified tools.
-   Although the uncertified tools should be more powerful, one can also find some examples where only the certified tools have been successful. The obvious reason is that if less techniques are available then more time can be spent on each individual technique, i.e., search for suitable orders, and sometimes this additional time was required to find the proof.

TRS and TRS innermost Certified
===============================

-   The main difference between AProVE and AProVE-CeTA is due to three techniques: bounded increase, the induction processor, and uncurrying/A-transformation in the innermost case.

Java Bytecode
=============

-   The example "Overflow.jar" was chosen. However, its termination depends on the handling of integers. If integers are implemented like in Java (i.e. their range is bounded), this example does not terminate (for any input). Maybe we should remove this (and other examples whose termination behaviour depends on the implementation of bounded integers)?

Termcomp
========

-   AProVE has hit a new record in large proofs: the one for TRS/MNZ_10/labelled is 535 MB large. Please do not try to load it during the competition, as most likely it will result in an out-of-memory exception on the termcomp-platform when trying to generate the HTML-page presenting this proof. CF As far as I recall, AProVE generated a proof of this size for this example already in the competition of 2010. For obvious reasons, I do not dare to check this on TermComp right now.
