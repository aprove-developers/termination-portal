---
title: TPDB
permalink: /TPDB/
---

The Termination Problems Data Base collects termination problems that are being used in termination competitions.

Syntax and semantics specification
----------------------------------

-   for versions from 7.\* onwards (XML format): [xtc.xsd](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB/raw-file/tip/xml/xtc.xsd), already part of the [TPDB](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB)
-   for versions up to 5.\*: <http://www.lri.fr/~marche/tpdb/format.html>

see also:

-   output specification for certified categories: <http://cl-informatik.uibk.ac.at/software/cpf/>

Data
----

-   version 9.0 (2014), 10.3 (2015) <http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB>
-   version 7.\* (2009), 8.0 (2010), 8.0.1 (2011), 8.0.6 (2012) and 8.0.7 (2013) <http://termcomp.uibk.ac.at/status/downloads/>
-   version 6.0.2 <http://termcomp.uibk.ac.at/termcomp/docs/tpdb-6.0.2.tar.gz>
-   version 5.0.2 (2008..2009) <http://termcomp.uibk.ac.at/termcomp/docs/tpdb-5.0.2.tar.gz>
-   earlier versions (2003 .. 2007) <http://www.lri.fr/~marche/tpdb/>

Sources
-------

The following are references for classical problem sets that appear in TPDB.

-   TRS/SK90 Joachim Steinbach, Ulrich Kühler: Check your Ordering - termination proofs and open Problems, Technical Report SR-90-25, Universität Kaiserslautern, 1990.
-   TRS/D33 Nachum Dershowitz: 33 Examples of Termination, 1995 Proc. French Spring School of Theoretical Computer Science, LNCS 909, <http://www.math.tau.ac.il/~nachumd/papers/printemp-print.pdf>
-   TRS/AG01 Thomas Arts, Jürgen Giesl: Termination of term rewriting using dependency pairs, 2000, <http://dblp.uni-trier.de/rec/bibtex/journals/tcs/ArtsG00> <http://verify.rwth-aachen.de/giesl/papers/ibn-97-46.ps>
-   SRS/Zantema 128 string rewriting termination problems collected by Hans Zantema (2004?)

TPDB problems are collected from a variety of sources, by a variety of contributors. Often, the author of the problem is not the creator of the respective TPDB file. Sometimes, TPDB file structure (directory names) have been changed.

Tools
-----

-   converter from pre-7 (textual) format to 7.\* (XML) format: <http://termcomp.uibk.ac.at/current/convert.jar> , usage:

`java -jar convert.jar someTrs.trs > someTrs.xml `

-   converter from 7.\* (XML) format to pre-7 (textual) format: [xtc2tpdb.xsl](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB/raw-file/tip/xml/xtc2tpdb.xsl), already part of the [TPDB](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB), usage:

`xsltproc xtc2tpdb.xsl someTrs.xml > someTrs.trs`

-   Haskell library for reading and writing TPDB (plain and XML format) [1](http://hackage.haskell.org/package/tpdb)
