---
title: Star Exec
permalink: /Star_Exec/
---

[StarExec](http://www.starexec.org/) is a cross-community solver execution and benchmark library service under joint development (since 2012) at the University of Iowa and the University of Miami. Its goal is to facilitate the experimental evaluation of logic solvers and other automated reasoning tools by providing a shared storage and computing infrastructure to store, manage and make available benchmark libraries; execute comparative evaluations; and run solver competitions.

The termination community intends to use this platform for running the competition in 2014 (and other tasks, like running experiments, archiving benchmarks and results, etc.)

We use this wiki page to collect items that we need to keep in mind.

There are some notes from 2012 below, for historical reference. An important change is that Starexec now provides [programmatic access](https://www.starexec.org/starexec/public/manual.txt) to their platform. This has successfully been used for the [Confluence competition 2013](http://coco.nue.riec.tohoku.ac.jp/2013/). Termcomp 2014 will do similarly: run competition on Starexec, but present data via separate web service.

Starexec for Termcomp in 2014
-----------------------------

information for participants (submitting and running solvers) - moved to [Termination_Competition_2014](/Termination_Competition_2014 "wikilink")

Running the Competition (Entries are from 2012, don't edit)
-----------------------------------------------------------

Open Questions:

-   Format of results: The specification does not speak explicitly about the format of the results. Is this going to be handled using Post-Processors? ([Marc Brockschmidt](/User:Mmjb "wikilink") 16:19, 12 June 2012 (CEST)). That would be most welcome also for certification: currently the post-processing does not only perform syntactic checks (correct XML, ...), but it checks whether the short answer YES/NO in combination with the input corresponds to the generated proof. It sometimes occurred that these checks detected some real bugs in the output. (RT)
-   Scoring systems: How can a scoring system like we use for the complexity competition be implemented? Post-processors seem to be restricted to working on one solver/result pair, while our scoring needs to see all results in a competition for a given example. ([Marc Brockschmidt](/User:Mmjb "wikilink") 16:19, 12 June 2012 (CEST)). The situation is even more complex: some of the results are used multiple times, e.g. there is one score for all complexity tools and another score for looking only at the open source complexity tools. (RT)
-   Will there be "Teams"? StarExec seems to know Communitys and single users, but not about the fact that some tools are produced by a group of people. ([Marc Brockschmidt](/User:Mmjb "wikilink") 16:19, 12 June 2012 (CEST))
-   How are benchmark sets (note: the organizers call the individual examples/problems/TRSs/... "benchmarks") organized? For example I'd like to have the official TPDB and private benchmark sets (which might be submitted to TPDB lateron). Furthermore, it is very useful to have complex ways of picking the relevant benchmark for a tool run (not just "the whole TPDB", but maybe "just the Java Bytecode benchmarks which are not yet in the TPDB"). Here having a number of user-defineable tags for each benchmark and being able to pick benchmark sets based on boolean combinations of tags can be a solution I'd like to see. ([C-Otto](/User:C-Otto "wikilink") 16:46, 12 June 2012 (CEST))
-   What further information do benchmarks have? We made good experience with storing information about the expected result (entered manually), so that runs giving a different result can be identified easily. Furthermore, it is useful to get a list of tool runs in which the specific benchmark could be solved. Statistical data (for example: this benchmark has never been solved, yet) is useful, too. ([C-Otto](/User:C-Otto "wikilink") 16:46, 12 June 2012 (CEST)) JW: SMT-Comp attaches a "status" property (SAT/UNSAT) to the benchmark, so I'm sure Starexec will have this. Statistical data should not be stored with the benchmark, since it will change ("never"), but it should be made available via queries (see below)
-   How will inherited example sets be handled (i.e., at the moment, the TPDB does not contain complexity examples, but these are derived from the TPDB) ([Marc Brockschmidt](/User:Mmjb "wikilink") 16:58, 12 June 2012 (CEST))
-   verified termination categories: these require a two-stage execution, first stage is that solvers run on problems, producing proof traces; second stage is that verifiers run on proof traces. (JW)

Extra Features
--------------

-   legacy data: it would be very useful to be able to compare data over time, and even back in time (like "has this problem (benchmark) ever been solved"). For this, star-exec needs a way to import competition results. (JW)
-   submission of new problems: it would be prefereable to have this automated: new benchmark sets can be uploaded to the platform and marked as "submitted for next competition", then they can be syntax-checked, and known solvers can be run on them. (JW)
-   for automatic submissions several new problems arise (RT)
    -   in which familys should the new problems be organized
    -   for which categories is the problem suitable (TRS / SRS / DCi / RC / ...)
    -   is there an automated check for duplicates
-   "live" interface: for demonstration/education it would be good to be able to create "experiments" on-the-fly. Upload a problem, or select from data base, then possibly edit it, then run a selection of solvers on that. (JW)
-   reasonable and stable URL for each and every data item (solver, competition (experiment), problem (benchmark), result). These URLs must work also when not logged it. (note: presently termcomp does not have URLs for (raw form of) problems? (JW) RT: There is a fixed URL for individual problems via its id like [1](http://termcomp.uibk.ac.at/termcomp/tpdb/tpviewer.seam?tpId=177248)) JW: yes but this links to a rendered version, I don't see the raw (.xtc) data there?
-   expressive textual query language, for querying all (public) data, where queries must allow arbitrary combinations. E.g., "the 10 smallest problems from category X that were unsolved in all previous competitions", "all results where prover Y's output contains the words Z" (yes that could be expensive but some indices could be pre-built) (JW)
