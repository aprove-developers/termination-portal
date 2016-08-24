---
title: Termination Competition 2015
permalink: /Termination_Competition_2015/
---

In 2015, the Termination Competition ([Call for Participation](http://lists.lri.fr/pipermail/termtools/2015-June/000984.html)) will be affiliated with [CADE-25](http://conference.mi.fu-berlin.de/cade-25/).

News
----

**Thu Aug 6 12:39:19 CEST 2015**

[Java done, others (TRS/SRS) starting](http://lists.lri.fr/pipermail/termtools/2015-August/001079.html) [Complexity Categories now running](http://lists.lri.fr/pipermail/termtools/2015-August/001076.html), [Technical Problems with AProVE (C Category)](http://lists.lri.fr/pipermail/termtools/2015-August/001075.html)

**Wed Aug 5 21:03:53 CEST 2015**

With [help from starexec](http://starexec.lefora.com/topic/61), I have restored the combined results presentation. It contains the jobs from today, and it already shows the jobs that will run tomorrow:

-   [Competition Categories](http://nfa.imn.htwk-leipzig.de/termcomp-2015/competitions/4) (at least two participants each)
-   [Demonstration Categories](http://nfa.imn.htwk-leipzig.de/termcomp-2015/competitions/5) (one participant each - note that TCT2/TCT3 count as one, because they come from the same team)

**Wed Aug 5 15:08:14 CEST 2015**

These categories are finished (display is now included in the combined view)

-   TRS Standard, TRS Standard certified, Cycle termination, C programs, C Integer programs.

and we will start complexity and others tomorrow (about 10 am CEST)

**Wed Aug 5 07:12:56 CEST 2015**

Final [list of participants](http://nfa.imn.htwk-leipzig.de/termcomp-2015/registered/Y2015)

We are having [serious](https://github.com/stefanvonderkrone/star-exec-presenter/issues/94) [difficulties](http://starexec.lefora.com/topic/61) starting live-size competition jobs.

We will try to start anyway, at 10:30 CEST today, but results may trickle in rather slowly, and the combined results presentation may not work initially. That's why here's a list of jobs for individual categories (to be extended as we move forward)

Dates
-----

-   registration of tools: July 1
-   submission of problems: July 7
-   updates of registered tools: July 29 (extended deadline)
-   competition runs: August 5 and 6 (during CADE)

Competition Categories and Awards
---------------------------------

The competition contains several categories from the areas of

-   termination of term rewriting (all categories with HO/FO-TRSs, with- or without strategies)
-   complexity analysis of term rewriting (all complexity categories)
-   termination of programming languages (Logic Programming, Haskell, Java, C, ...)

Competition Procedure
---------------------

All participants in the same category will be run on a [subset](http://www.termination-portal.org/wiki/Termination_Competition_Problem_Selection_Algorithm) of the existing problems of this category. The number of problems used in the competition is not fixed and will depend on the number of existing problems. The problem selection algorithm will be the same as in previous years [Termination_Competition_Problem_Selection_Algorithm](/Termination_Competition_Problem_Selection_Algorithm "wikilink") There might be modifications of the rules suggested by the organizer and decided by the SC.

The wall-clock timeout will be 60 (up to 300) seconds, and 4 cores will be available (if a tool wants to use concurrent execution).

The tools will be started in their directory and obtain

-   the problem file name on the command line,
-   and extra info from environment variables, cf. [Termination Competition 2014 technical details](/Termination_Competition_2014_technical_details "wikilink")

The tools are expected to give an answer (YES, NO, MAYBE) in the first line on stdout, followed by a proof in ASCII, HTML, or CPF format. Exceptions to these rules are the [certified](http://www.termination-portal.org/wiki/Termination_Competition_Certified_Categories_Competition) (see also the [CPF-website](http://cl-informatik.uibk.ac.at/software/cpf/)) and [complexity](http://cl-informatik.uibk.ac.at/users/georg/cbr/competition/) categories. See all existing [categories](http://www.termination-portal.org/wiki/Category:Categories) for more details.

For those problems where a correct answer is (partially) known, any contradictory answer will be penalized with a high negative score. Moreover, those buggy systems may have the opportunity to provide a corrected version that will be run again after the end of the live execution (displaying the new results afterwards, but out of competition).

For those categories devoted to prove only termination or non-termination, the score of a tool is the number of non-contradictory answers minus the given penalization (if any).

Committees
----------

Steering Committee

-   Jürgen Giesl, RWTH Aachen, Germany
-   Frederic Mesnard, Université de la Réunion, France
-   Albert Rubio (chair), UPC Barcelona, Spain
-   Rene Thiemann, Universität Innsbruck, Austria
-   Johannes Waldmann, HTWK Leipzig, Germany

Organizing Commmittee

-   Johannes Waldmann, HTWK Leipzig, Germany

Registration
------------

Participants must register

-   on Starexec (so you can upload and test your solver): enter your data at [StarExecRegistration](https://www.starexec.org/starexec/public/registration.jsp), indicating the competition categories where they plan to enter tools and problems, and then upload their contributions to [StarExec](http://www.starexec.org)

-   -   and\* with the Termination Competition Organizer (so I known what solver/configuration to use). Details will be announced here: [Termination Competition 2015 Registration](/Termination_Competition_2015_Registration "wikilink")

Note: if I (J. Waldmann) don't know you ("knowing" is roughly symmetrical), then I will ask you to specify: what termination tool you're working on, what competition categories you plan to take part in, your affiliation (in case you're a student, also the name of your advisor/research group leader). The email address you give in the registration should be your institutional one.

We recommend to register early. After the deadline, access to [StarExec](http://www.starexec.org) might be restricted. We need time to prepare the competition, and other competitions may be running in parallel.

It is highly recommended that participants also subscribe to the [termtools](http://lists.lri.fr/mailman/listinfo/termtools) mailing list, because that is where announcements will be made, and where discussion takes place.

StarExec Wiki
-------------

Lots of useful information about StarExec is available [here](https://wiki.uiowa.edu/display/stardev/User+Guide).

Technical Detail
----------------

The competition will be running on [StarExec](http://www.starexec.org/) - a cross-community solver (tool) execution and benchmark (problem) library service under joint development (since 2012) at the University of Iowa and the University of Miami.

Competition data will be presented via [star-exec-presenter](https://github.com/stefanvonderkrone/star-exec-presenter) - developed and running at HTWK Leipzig.

Technical details about the execution platform (as of 2014) can be found [here](http://www.termination-portal.org/wiki/Termination_Competition_2014_technical_details).

Contact
-------

To contact the steering committee of the termination competition, send an email to terminationcompetitionsc<at>lists.rwth-aachen.de.

The competition organizers can be reached at johannes.waldmann<at>htwk-leipzig.de

Send new problems for the competition to rene.thiemann<at>uibk.ac.at

Changes with respect to 2014
----------------------------

These lists reflect the discussion in the community, and in the steering committee. Items are preliminary, and not officially binding. Please do not edit this list (unless you're in the SC). Instead, send proposals to termtools or terminationcompetitionsc mailing list, or create a new wiki page and put a link here.

Proposed changes:

-   The answering scheme and the scoring of the complexity category slightly changed. The new version of the grammar and the updated scoring mechanism are described in more detail on the [complexity related page](http://cl-informatik.uibk.ac.at/users/georg/cbr/competition/), and below is just a small summary of the changes.
    -   The grammar for answers was simplified and is now less ambiguous.
    -   The grammar for answers now explicitly contains lower bounds.
    -   Lower bounds will be counted for complexity.

Adopted changes:

-   The CPF version has been updated from version 2.2 to version 2.3. This transition consists of purely incremental changes. The details of the changes are documented in the [CPF repository log](http://cl2-informatik.uibk.ac.at/rewriting/mercurial.cgi/CPF).

-   In addition to the category for "full" C programs, we also intend to have a category for "C integer" programs. These are essentially integer transition systems formulated as imperative programs in C syntax. A detailed definition can be found [here](http://www.termination-portal.org/wiki/C_Integer_Programs).

TODO
----

See [Termination Competition 2015 TODO](/Termination_Competition_2015_TODO "wikilink")
