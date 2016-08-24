---
title: Termination Competition 2014 technical details
permalink: /Termination_Competition_2014_technical_details/
---

We intend to run the competition on [StarExec](http://www.starexec.org/) - a cross-community solver execution and benchmark library service under joint development (since 2012) at the University of Iowa and the University of Miami. Its goal is to facilitate the experimental evaluation of logic solvers and other automated reasoning tools by providing a shared storage and computing infrastructure to store, manage and make available benchmark libraries; execute comparative evaluations; and run solver competitions.

For displaying the results of the termination competition, we are building a separate web service at HTWK Leipzig.

Here is some information for participants: (reverse chronological - newest first)

-   benchmarks are renamed by the platform: <http://starexec.forumotion.com/t60-restore-file-extension-for-renamed-benchmarks#145>
-   announcements by the starexec team: <http://starexec.wordpress.com/>
-   solvers will be called with the file name of the termination problem as the *only* argument. Solvers can read environment variables to enquire about timeout (and other parameters), cf. <https://wiki.uiowa.edu/display/stardev/User+Guide#UserGuide-SpecialVariables>
-   it is helpful to follow other solver communities, e.g., [SMT COMP 2014](http://smtcomp.sourceforge.net/2014/)
-   submit solvers for testing the platform [1](http://lists.lri.fr/pipermail/termtools/2014-February/000940.html)
-   how to register on starexec [2](http://lists.lri.fr/pipermail/termtools/2014-February/000943.html) NOTE: there may be service interruptions (e.g., sudden changes in benchmark arrangement).
-   STAREXEC_MAX_MEM only 750 MB? [3](http://lists.lri.fr/pipermail/termtools/2014-February/000941.html) (UPDATE: this was out of date, the limit is actually 64 GB)
-   Beware if your solver writes to stderr. The "postprocessor" (that expects YES|NO in the first line, for termination) gets to see stdout and stderr merged. If you have trace/log output, you can only show it after the actual answer.
-   hardware on starexec: see [4](https://www.starexec.org/starexec/public/machine-specs.txt) Solvers are run on nodes with 4 cores each.
-   software on starexec: RHEL 6.3 (so [Centos 6.3](http://mirror.nsc.liu.se/centos-store/6.3/isos/x86_64/) should be a close match). Package selection, see [5](http://starexec.forumotion.com/t23-problem-with-dynamic-linking#47)
-   java is available on starexec nodes (jdk 1.6.0_41) - see [6](http://starexec.forumotion.com/t27-install-more-recent-jre-on-nodes) - see also remark on ulimits and -Xmx [7](http://starexec.forumotion.com/t34-ulimits-settings-may-hurt-java-programs#69)

information on the web GUI (under construction) for presenting results [Star_Exec_Presenter](/Star_Exec_Presenter "wikilink")

Separate page with impressions from using the demo version of Star Exec, in 2012: [Star_Exec_Test](/Star_Exec_Test "wikilink")
