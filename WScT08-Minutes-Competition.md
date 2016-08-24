---
title: WScT08-Minutes-Competition
permalink: /WScT08-Minutes-Competition/
---

(These are minutes of the meeting. Please do not edit this page except for correcting obvious mistakes. Make links to separate pages for further discussions.)

-   Unique IDs for problems in database
    -   Idea: short IDs that can be used in papers
    -   Different suggested formats (nrs are relative, e.g., 2008-1 and 2009-1 possible):
        -   nameOfAuthor-year-nr (problem of uniqueness)
        -   abbreviatedNameOfAuthor-year-nr (problem of uniqueness)
        -   login-year-nr
        -   year-archiveNr-fileNr
        -   year-fileNr
        -   nr
    -   Question: Who decides format? Would be nice to have decision soon

-   Annotation of termination problems
    -   Comments can be added by user
    -   Status at time of submission (open in theory, solved on paper, solved, solved certified, ...)
    -   Presentation will show above points and computed information (like date of submission, solved by xx tools, ...)

-   Submission of many problems
    -   Zip-files which contain xml-file for adding initial comments, etc.
    -   Format of xml-file has to be fixed
    -   Should be same format for adding and for retrieving examples
    -   To discuss: relation to system-part of XTC-format

-   Wishlist for termination competition platform
    -   Testing should be frequently possible
    -   Extract challenging problems and letting them run with higher time-limit
    -   Quotas for experiments? Accessing non-approved examples? Using non-approved tools? Mainly Innsbruck is in charge and makes rules public
    -   SQL-variant for selection problems and evaluate results, where several properties can be used within queries
    -   Scoring should be flexible
    -   Categories as queries (incl. randomSubsetOf(..)) + timeout(s) + scoring
    -   New category: XML-proofs given, certifiers compete
    -   Possibility to manually attach proofs for problem (difficult to find/human assisted, or large and put it as challenge for certificating category)
    -   Open source (Obergurgl 2007 this was stated)
    -   https

-   Discussion whether TRSs should be removed from standard categories which do not satisfy variable condition

-   Timeouts for verified competition
    -   Discussion whether there are separate timeouts on proof-finding and checking, or one global timeout
    -   Majority was for separate timeouts

### Proposed XML Format for Import/Export to the termination database

See here: [TPDB_XML_Format](/TPDB_XML_Format "wikilink")
