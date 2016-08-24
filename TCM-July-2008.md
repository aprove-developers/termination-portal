---
title: TCM-July-2008
permalink: /TCM-July-2008/
---

Date/Time/Location
------------------

15 July 2008, 6:30 pm, during RTA at Hagenberg

Agenda/Minutes
--------------

NOTE: please do not put further discussion on this page (except for correcting mistakes in the recording). Feel free to create additional pages and link from here)

-   current status of the competition test run
    -   the "Torpa problem" (what can programs expect on \$PATH, \$PWD)
    -   the "Jambox problem" (programs that write long proofs)
    -   Q: test run for certified termination?

Discussion: postponed, since technical detail can be handled via email, and Simon is busy this and next week

-   next steps
    -   submission of new prover versions
    -   test runs (by submitters)

Discussion: this shall be possible as soon as the current test run finishes

-   -   submission of new problem (sets)
    -   complete runs (by administrators)
    -   evaluation (by committee) (how and when)

Discussion: (no result)

-   new category suggestions
    -   complexity analysis (Georg Moser, Johannes Waldmann)

Discussion: the goal is that YES answer can annotated by complexity information. Georg and Andreas will submit their complexity prover for testing.

-   -   SN infinity (Hans Zantema, Jörg Endrullis)

Discussion: no consensus. Possibility of extending the current TPDB problem format by allowing top/non-top, strict/non-strict rules. This would allow to do some SN-infinity proofs (after a transformation). (Note: this had already been discussed at Nancy 2007 workshop.)

-   -   we have more categories than people?

Discussion: to focus, we need deadlines (for reporting results on certain categories). Agreement: the next deadline is 1 November 2008, for running new versions of provers on the 2007 categories. after that, there could be a deadline in 2009 shortly before the Workshop on Termination.

Discussion: we still want an ongoing competition, that is, submissions of provers should be possible at all times, and they will be run on all problems immediately, and their results will be shown publically. The deadline is just to freeze a data set for reporting.

-   To discuss and clarify
    -   RAM usage (unlimited I guess)
    -   CPU usage (defined by wall time, so one may use 16 cores? CPU time, so 60 seconds singlethreaded translates to about 4 seconds with 16 threads?)
    -   For CPU time limit the competition can run faster (if the tools run multithreaded), but there is no incentive to do so.
    -   My opinion: Because the machines have 16 CPU cores each, multithreading should be encouraged (read: wall time!)
    -   With wall time 60 seconds would be roughly equivalent to 960 seconds at the old competition

Discussion: this had been discussed and decided before. Use wall time. This encourages to make use of the multicore architecture.

-   details for Termination Workshop 2009 Leipzig
    -   date? (needs to be decided soon, to book the venue)
    -   length/schedule? suggestion:
        -   (day 1) sub-workshop on certified termination
        -   (day 2, 3) termination workshop (if there are more submission, then already start on afternoon of day 1)
        -   (day 4) would be possible to hold the IFIP WG 1.6 meeting
    -   program committee? suggestion: informal workshop, no refereeing, small committee, include people from communities of termination of logic programming, imperative programming

Discussion: Date is around June 2 .. 5 (week after Pfingsten). Schedule as proposed. Local organizer may institute program committee. For submissions, require only abstracts (1 .. 2 pages).
