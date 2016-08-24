---
title: MicroTTT
permalink: /MicroTTT/
---

MicroTTT is a prototype written in OCaml that generates XML-output as termination proofs using only the dependency pair transformation, estimated dependency graphs, strongly connected components decomposition, and simple projections combined with the subterm criterion. Additionally it is possible to read in such XML-proofs and - using the same methods as for generating a proof - check them for correctness.

-   the source code is available [here](http://cl-informatik.uibk.ac.at/~griff/mttt/mttt.tar.bz2)
-   the specification of the XML-format [here](http://cl-informatik.uibk.ac.at/~griff/mttt/rscc.xsd)

Note that Ruby needs to be installed for compilation of microTTT, since the internal preprocessor of it is written in that language.
