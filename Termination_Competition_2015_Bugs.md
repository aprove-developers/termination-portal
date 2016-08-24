---
title: Termination Competition 2015 Bugs
permalink: /Termination_Competition_2015_Bugs/
---

strange outputs from test runs before competition, cf. [1](http://lists.lri.fr/pipermail/termtools/2015-July/001062.html)

fresh:

-   <http://nfa.imn.htwk-leipzig.de/termcomp-devel/problems/9848>

already commented upon:

-   <http://nfa.imn.htwk-leipzig.de/termcomp-devel/problems/9663/9665/9682/9683>
-   <http://nfa.imn.htwk-leipzig.de/termcomp-devel/problems/9632/9652>
-   <http://nfa.imn.htwk-leipzig.de/termcomp-devel/problems/9546/9548/9568/9569>

comments on the above

-   <http://lists.lri.fr/pipermail/termtools/2015-July/001063.html>
-   <http://lists.lri.fr/pipermail/termtools/2015-July/001064.html>

when you view such "problems" links, you might be seeing some non-conflicts because of

-   confusing termination and cycle-termination
-   postprocessor confused by time-outs (see <https://github.com/stefanvonderkrone/star-exec-presenter/issues/93> )
