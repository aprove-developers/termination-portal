---
title: Termination and Complexity Competition 2016
permalink: /Termination_and_Complexity_Competition_2016/
---

In 2016, the Termination and Complexity Competition will be affiliated with the [15th International Workshop on Termination](http://cl-informatik.uibk.ac.at/events/wst-2016/) and it will take place "live" during the workshop. Participants may give a short presentation of their tool during the competition session at the workshop. The competition will be run on the [StarExec platform](http://www.starexec.org/).

Dates
-----

-   Tool Registration: July 31, 2016 (detail: [Termination_Competition_2016_Registration](/Termination_Competition_2016_Registration "wikilink"))
-   Problem Submission: August 14, 2016
-   Updates of Registered Tools: August 21, 2016
-   Competition: September 5-6, 2016

Competition Categories
----------------------

The competition contains several categories for termination and complexity from the areas of term rewriting (all categories with HO/FO-TRSs, with- or without strategies) and programming languages (Logic Programming, Haskell, Java, C, integer transition systems, ...)

Competition Procedure
---------------------

All participants in the same category will be run on a [subset](http://www.termination-portal.org/wiki/Termination_Competition_Problem_Selection_Algorithm) of the existing problems of this category. The number of problems used in the competition is not fixed and will depend on the number of existing problems. The problem selection algorithm will be the same as in previous years [Termination_Competition_Problem_Selection_Algorithm](/Termination_Competition_Problem_Selection_Algorithm "wikilink"). The selection is made so that the whole competition will be executed live during the competition session of WST 2016. There might be modifications of the rules suggested by the organizer and decided by the SC.

The wall-clock timeout will be 30 seconds, and 4 cores will be available (if a tool wants to use concurrent execution). A longer timeout for selected categories might be possible and has to be negotiated with the participants of that category.

The tools will be started in their directory and obtain

-   the problem file name on the command line,
-   and extra info from environment variables, cf. [Termination Competition 2014 technical details](/Termination_Competition_2014_technical_details "wikilink")

The tools are expected to give an answer (YES, NO, MAYBE) in the first line on stdout, followed by a proof in ASCII, HTML, or CPF format. Exceptions to these rules are the [certified](http://www.termination-portal.org/wiki/Termination_Competition_Certified_Categories_Competition) (see also the [CPF-website](http://cl-informatik.uibk.ac.at/software/cpf/)) and [complexity](http://cl-informatik.uibk.ac.at/users/georg/cbr/competition/) categories. See all existing [categories](http://www.termination-portal.org/wiki/Category:Categories) for more details.

For those problems where a correct answer is (partially) known, any contradictory answer will be penalized by -10 points.

For those categories devoted to prove only termination or non-termination, the score of a tool is the number of non-contradictory answers minus the given penalization (if any).

Committees
----------

Steering Committee

-   Jürgen Giesl, RWTH Aachen, Germany
-   Frederic Mesnard, Université de la Réunion, France
-   Albert Rubio (chair), UPC Barcelona, Spain
-   René Thiemann, Universität Innsbruck, Austria
-   Johannes Waldmann, HTWK Leipzig, Germany

Organizing Commmittee

-   Johannes Waldmann, HTWK Leipzig, Germany (StarExec)
-   René Thiemann, Universität Innsbruck, Austria (CPF)
-   Akihisa Yamada, Universität Innsbruck, Austria (TPDB)

Registration
------------

Participants must register

-   on Starexec (so you can upload and test your solver): enter your data at [StarExecRegistration](https://www.starexec.org/starexec/public/registration.jsp), indicating the competition categories where they plan to enter tools and problems, and then upload their contributions to [StarExec](http://www.starexec.org)

-   -   and\* with the competition's organizer, J. Waldmann (so I known what solver/configuration to use). Details will be announced here: [Termination Competition 2016 Registration](/Termination_Competition_2016_Registration "wikilink")

Note: if I (J. Waldmann) don't know you ("knowing" is roughly symmetrical), then I will ask you to specify: what termination tool you're working on, what competition categories you plan to take part in, your affiliation (in case you're a student, also the name of your advisor/research group leader). The email address you give in the registration should be your institutional one.

We recommend to register early. After the deadline, access to [StarExec](http://www.starexec.org) might be restricted. We need time to prepare the competition, and other competitions may be running in parallel.

It is highly recommended that participants also subscribe to the [termtools](http://lists.lri.fr/mailman/listinfo/termtools) mailing list, because that is where announcements will be made, and where discussion takes place.

StarExec Information
--------------------

this refers to StarExec in general, and not to Termination in particular.

-   [user guide](https://wiki.uiowa.edu/display/stardev/User+Guide)
-   [announcements and discussion](http://starexec.lefora.com/directory) ([combined feed for recent messages](http://starexec.lefora.com/feed/get/type/rss/source/domain/id/280028))
-   [announcements and discussion](http://starexec.forumotion.com/) (discontinued, but contains some information that is still valid and not available elsewhere)

Technical Detail
----------------

The competition will be running on [StarExec](http://www.starexec.org/) - a cross-community solver (tool) execution and benchmark (problem) library service under joint development (since 2012) at the University of Iowa and the University of Miami.

Competition data will be presented via [star-exec-presenter](https://github.com/stefanvonderkrone/star-exec-presenter) - developed and running at HTWK Leipzig.

Technical details about the execution platform (as of 2014) can be found [here](http://www.termination-portal.org/wiki/Termination_Competition_2014_technical_details).

Contact
-------

To contact the steering committee of the termination competition, send an email to terminationcompetitionsc<at>lists.rwth-aachen.de.

The competition organizers can be reached at johannes.waldmann<at>htwk-leipzig.de

Send new problems for the competition to akihisa.yamada<at>uibk.ac.at

Changes with respect to 2015
----------------------------

These lists reflect the discussion in the community, and in the steering committee. Items are preliminary, and not officially binding. Please do not edit this list (unless you're in the SC). Instead, send proposals to termtools or terminationcompetitionsc mailing list, or create a new wiki page and put a link here.

Adopted changes:

-   The CPF version is in the process of being updated from version 2.3 to version 2.4. This transition consists mainly of incremental changes. The details of the changes are documented in the [CPF repository log](http://cl2-informatik.uibk.ac.at/rewriting/mercurial.cgi/CPF). The only non-incremental change is that now there is a dedicated input format for termination problems modulo AC, which before have been encoded as relative termination problems.
