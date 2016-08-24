---
title: Termination Competition 2014
permalink: /Termination_Competition_2014/
---

In 2014, the Termination Competition will be part of the [FLoC Olympic Games](http://vsl2014.at/olympics/).

Current News
------------

Competition results at [1](http://nfa.imn.htwk-leipzig.de/termcomp-2014/competition/20) . Demonstration results at [2](http://nfa.imn.htwk-leipzig.de/termcomp-2014/competition/23). [Termination Competition 2014 Questionnaire](/Termination_Competition_2014_Questionnaire "wikilink"). Also, check the mailing list [3](http://lists.lri.fr/pipermail/termtools/2014-July/thread.html)

Dates
-----

-   call for tools, certifiers, problems: May 26
-   registration of tools: June 15
-   updates of registered tools, submission of problems: July 1
-   competition runs: July 19 - 21
-   results announced: July 21, during the Second FLoC Olympic Games Award Ceremony, Vienna.

Competition Categories and Awards
---------------------------------

The competition contains several categories, grouped in three meta-categories:

-   termination of term rewriting (all categories with HO/FO-TRSs, with- or without strategies)
-   complexity analysis of term rewriting (all complexity categories)
-   termination of programming languages (Logic Programming, Haskell, Java, C, ...)

In each meta-category, a medal will be awarded to the highest-scoring solver.

For every meta-category, we consider the sum of the scores for each category within that meta-category: The score of a tool is determined by the number of other tools which could be beaten in that category.

This puts the emphasis on categories with many competitors. (In particular, a category with just one entrant would produce a zero score.) A category is only run at the competition if there are at least 2 participants and at least 40 examples for this category in the underlying termination problem data base.

New Categories
--------------

This year a new category on termination of C programs will be included (see the details [here](http://www.termination-portal.org/wiki/C_Programs)).

Other categories for "transition systems" or "large scale (Java) programs" are under consideration depending on the number of interested participants and available problems.

Competition Procedure
---------------------

All participants in the same category will be run on a [subset](http://www.termination-portal.org/wiki/Termination_Competition_Problem_Selection_Algorithm) of the existing problems of this category. The number of problems used in the competition is not fixed and will depend on the number of existing problems. The problem selection algorithm will be the same as in previous years (link <http://www.termination-portal.org/wiki/Termination_Competition_Problem_Selection_Algorithm>), however because of moving to [StarExec](http://www.starexec.org), there might be modifications of the rules suggested by the organizer and decided by the SC.

The wall-clock timeout will be 60 (up to 300) seconds, and 4 cores will be available (if a tool wants to use concurrent execution).

For nearly all categories, the tools will be started in their directory and obtain two parameters:

-   the problem file and
-   the timeout in seconds. - UPDATE Thu Jun 12 16:56:23 CEST 2014: one parameter (problem file name) on the command line, extra info from environment variables, see [Termination Competition 2014 technical details](/Termination_Competition_2014_technical_details "wikilink")

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
-   Stefan von der Krone, HTWK Leipzig, Germany

Registration
------------

Participants must register on [StarExecRegistration](https://www.starexec.org/starexec/public/registration.jsp), indicating the competition categories where they plan to enter tools and problems, and then upload their contributions to [StarExec](http://www.starexec.org).

Note: if I (J. Waldmann) don't know you ("knowing" is roughly symmetrical), then I will ask you to specify: what termination tool you're working on, what competition categories you plan to take part in, your affiliation (in case you're a student, also the name of your advisor/research group leader). The email address you give in the registration should be your institutional one.

We recommend to register early. After the deadline, access to [StarExec](http://www.starexec.org) might be restricted. We need time to prepare the competition, and other competitions may be running in parallel.

It is highly recommended that participants also subscribe to the [termtools](http://lists.lri.fr/mailman/listinfo/termtools) mailing list, because that is where announcements will be made, and where discussion takes place.

Registration (Detail)
---------------------

see this page: [Termination Competition 2014 Registration](/Termination_Competition_2014_Registration "wikilink")

StarExec Wiki
-------------

Lots of useful information about StarExec is available [here](https://wiki.uiowa.edu/display/stardev/User+Guide).

Technical Detail
----------------

We intend to run the competition on [StarExec](http://www.starexec.org/) - a cross-community solver (tool) execution and benchmark (problem) library service under joint development (since 2012) at the University of Iowa and the University of Miami.

Technical details about the execution platform can be found [here](http://www.termination-portal.org/wiki/Termination_Competition_2014_technical_details).

Contact
-------

To contact the steering committee of the termination competition, send an email to terminationcompetitionsc<at>lists.rwth-aachen.de.

The competition organizers can be reached at johannes.waldmann<at>htwk-leipzig.de
