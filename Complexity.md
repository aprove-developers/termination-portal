---
title: Complexity
permalink: /Complexity/
---

    This page is outdated and no longer maintained.

An up to date version of the content of this page can now be found here: [complexity competition](http://cl-informatik.uibk.ac.at/users/georg/cbr/competition).

* * * * *

This page provides general information on the complexity category; (potential) tool authors or others that may want to join the discussion on various aspects of the category can also go directly to the discussion and rules page; aficionados may be interested in the techniques page.

Introduction
------------

It is a challenging topic to automatically determine upper and lower bounds on the complexity of term rewrite systems (TRSs for short). Here complexity of a TRS basically refers to the maximal length of derivations, measured in the size of the initial terms. Still, depending on rewrite strategies and restrictions on the set of allowed starting terms, various notions of complexity exist. The current focus of the competition is on providing <em>polynomial upper bounds</em> to the complexity of TRSs. Presumably the competition will be extended to lower bounds soon.

Overview of the Complexity Category
-----------------------------------

Currently, depending on considered set of starting terms and strategy, the competition is divided into four categories:

||Derivational Complexity|Runtime Complexity|
|---|-----------------------|------------------|
|Full Rewriting|DC|RC|
|Innermost Rewriting|iDC|iRC|

Derivational complexity and runtime complexity differ in the sense that for derivational complexity, no restrictions on the set of considered starting terms is put. For runtime complexity however, only basic terms (i.e. terms where arguments are formed from constructor symbols) are taken into account. See for example [(Hirokawa, Moser, 2008)](http://dx.doi.org/10.1007/978-3-540-71070-7_32) [(Moser, 2009)](http://arxiv.org/abs/0907.5527) for further reading on the notion of runtime complexity.

Furthermore, we distinguish between complexities induced by full rewriting as opposed to complexities induced by innermost rewriting.

Overview of the Competition
---------------------------

The complexity category is part of the termination competition since 2008. The competition is currently hosted at [1](http://termcomp.uibk.ac.at/termcomp/home.seam), where you can find results of the competitions from [2008](http://termcomp.uibk.ac.at/termcomp/competition/competitionSummary.seam?comp=15991) and [2009](http://termcomp.uibk.ac.at/termcomp/competition/competitionSummary.seam?comp=101722).

### Important Dates

||Deadline/Date|
|---|-------------|
|Tool Submission|July 14, 2010|
|Problem Submission|July 2, 2010 (but see email to termtools)|
|Competition|July 16, 2010|

### Participate

If you want to participate in the competition, go to the [Termination Competition Portal](http://termcomp.uibk.ac.at/), create an account and add your tool. Documentation concerning this process can be found [here](http://termcomp.uibk.ac.at/termcomp/help/register.seam?cid=8144).

Kindly note that in order to participate, your tool needs to be [<em>open source</em>](http://www.opensource.org/).

#### Participating Teams of Past and Upcoming Competitions

Here you can find a list (sorted by tool name) of participants of past competitions and supposed participants of the upcoming competition.

|Tool|Internal Page|text-align="left"|Authors|2008|2009|2010|
|----|-------------|-------------------------|----|----|----|
|[Matchbox](http://www.imn.htwk-leipzig.de/~waldmann/)|[Tools:Matchbox](/Tools:Matchbox "wikilink")|J. Waldmann|---|x|x|
|[TCT](http://cl-informatik.uibk.ac.at/software/tct)|[Tools:TCT](/Tools:TCT "wikilink")|M. Avanzini, G. Moser, A. Schnabl|x|x|x|
|[CaT](http://cl-informatik.uibk.ac.at/software/ttt2)|[Tools:CaT](/Tools:CaT "wikilink")|M. Korp, C. Sternagel, H. Zankl|x|x|x|
|[AProVE](http://aprove.informatik.rwth-aachen.de/)|[Tools:AProVE](/Tools:AProVE "wikilink")|The AProVE Team|---|---|x|
|Oops|[Tools:Oops](/Tools:Oops "wikilink")|Fabian Emmes, Lars Noschinski|---|---|x|
||

An overview of the proof techniques applied by the participants in past competitions can be found [here](/Complexity_Techniques "wikilink").

Past Winners
------------

In 2008, [CaT](/Tools:CaT "wikilink") was the winner of both derivational complexity categories, whereas for runtime complexity only [TCT](/Tools:TCT "wikilink") participated. In 2009, all categories where ruled by [CaT](/Tools:CaT "wikilink"). Congratulations!

For detailed information on the testsuites employed and the actual results of the tools see the [termcomp](http://termcomp.uibk.ac.at) pages.

Overview of the Competition Rules
---------------------------------

Problems are given in the new TPDB-format, see [2](http://www.termination-portal.org/wiki/XTC_Format_Specification) and are selected randomly from the newest version of the Termination Problem Database.

In the selection process, emphasis is put onto selecting problems that could not be automatically verified in past competitions, c.f. page [problem selection](/Complexity:Rules#Problem_Sets_and_Problem_Selection "wikilink") for details. Tools are ranked not only by number of succeeded runs, but in the scoring also the preciseness of the bounds is taken into account. See page [scoring](/Complexity:Rules#scoring "wikilink") for further details.

Unfortunately the database is currently somehow biased towards termination problems. We encourage everybody to submit new problems to the TPDB that are interesting from a complexity related perspective. (In submission please indicate that these examples should go into the complexity benchmark.)

[Category:Categories](/Category:Categories "wikilink")
