---
title: XTC Format Specification
permalink: /XTC_Format_Specification/
---

Schema
======

The schema `xtc.xsd` is part of the termination problem database ([TPDB](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB)) in the subdirectory `xml`. The schema can be inspected [within the browser](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB/file/tip/xml/xtc.xsd) or [downloaded](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB/raw-file/tip/xml/xtc.xsd).

XML Structure
=============

The XML structure has the following main blocks:

-   <trs>: this block contains all the information pertinent to the TRS itself. A more detailed description is below.
-   <strategy>: this corresponds to the (STRATEGY ) block in the TPDB format.
-   <startterm>: this is an extension for complexity analysis
-   <status>: this is a meta-information block which contains information relating to the known termination status of a given problem.
-   <metainformation>: more meta-information pertaining to the author of a problem, can also contain free-form comments.

Both <status> and <metainformation> will be stored in the database, but stripped from input files for the purposes of running the competition.

The <trs> block is structured as follows:

-   <rules>: this block contains all the rules of a TRS, relative rules are separated into a separate child <relrules>; both these blocks can contain multiple <rule> children, consisting of a <lhs>, <rhs> and optional <conditions> block.
-   <signature>: this block contains the list of function symbols with their signatures (name, arity, theory and context-sensitive replacement-map).
-   <comment>: a free-form comment field about this TRS itself.
-   <conditiontype>: for conditional TRS, this block is used to select the type of condition to be applied.

The full structure can be seen in the XML Schema file linked above.

XSLT Transformation
===================

There are stylesheets to transform the XML-files into HTML or ASCII (the old TPDB format). Both stylesheets are contained in the TPDB, subdirectory `xml`.

-   converter to HTML: [xtcHTML.xsl](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB/raw-file/tip/xml/xtcHTML.xsl)
-   converter to ASCII: [xtc2tpdb.xsl](http://cl2-informatik.uibk.ac.at/mercurial.cgi/TPDB/raw-file/tip/xml/xtc2tpdb.xsl)
