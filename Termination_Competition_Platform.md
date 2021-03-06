---
title: Termination Competition Platform
permalink: /Termination_Competition_Platform/
---

Note
====

There is (will be) a well-defined process of making design decisions w.r.t. the Termination Competition Execution and Presentation Platform (via mailing list, steering committee), and then the Host decides on implementation.

For features that have run through this process, the [<http://dev.aspsimon.org/bugzilla/buglist.cgi?bug_file_loc>=&bug_file_loc_type=allwordssubstr&bug_id=&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED termcomp Bugzilla] is the right place for bug reports.

Below here, we just collect some ideas for later consideration.

Wishlist: Query Interface
=========================

The idea is to provide a web interface for queries over the results data base(s). We aim for flexibility, but will start with some simple prototype. Please list here some typical queries that you would want to execute.

-   what problems were solved in srs-standard, but not in srs-standard-certified?
-   what are the problems that were solved in (insert category here)-2008 but not in 2007 (yes, we plan to import earlier competition results into the data base)?
-   what is the problem/tool in (insert category here) with the longest/shortest proof (file size)/execution time?

-   what are the problems that generate a coq timeout for some tool?
-   what is the average size of the (xml|coq) files generated by a given tool?
-   what are the (problems|results) that are (solved|certified) by all the tools in some set of tools?

-   here is a [result presentation for Color in certified categories](http://color.loria.fr/comp.html) that Frederic built "by hand" (?) The query interface should automatically produce such or and similar charts.

what might also be helpful: can you name a web site with some configurable query functionality that you think is especially well-designed and worth learning from?

Christian Sternagel: I would also like to be able to query the problem data base and not only the results data base(s). (J.W.: there is a [query interface for tpdb](http://colo5-c703.uibk.ac.at:8080/termcomp/tpdb/tpsearch.seam) already. what features are missing? C.S.: Since it is currently not working, it is merely a placeholder for a query interface.)

Missing features:

-   give me all problems from 2007 that are left linear/overlapping/dummy SRSs/... (i.e., properties of problems)
-   boolean combination of properties
-   wild cards
-   give results statistics for parts of a category, e.g., only selected subdirectories

Execution Component
===================

The termination competition platform will be extended by a component allowing users to create custom experiments comparing different tools on a custom selection of termination problems. the document linked below outlines the proposed functionality this component will offer.

<http://dev.aspsimon.org/workspace/projectdocs/termexec.pdf>
