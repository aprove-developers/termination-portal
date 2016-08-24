---
title: Termination Competition Certified Categories Competition
permalink: /Termination_Competition_Certified_Categories_Competition/
---

Some new elements have been added to the certification problem format.

-   non-confluence proofs of Aoto's FroCoS 13 paper.
-   SRS non-termination proofs of Oppelt's thesis.
-   converting constants into unary symbols.
-   modular non-confluence proofs.
-   string reversal for relative nontermination.
-   switching from innermost to full strategy for non-termination.

Comments are welcome, and if there are none, then these elements will be fixed by June 4, 2014.

See <http://cl-informatik.uibk.ac.at/software/cpf/#devel> for more details.

The certified categories will be run as follows:

-   Tools that can produce output in CPF and that participate in the certified competition are run in parallel to the tools which do not generate CPFs. (Tools may register several times for the same category: uncertified, and CPF-generating w.r.t. certain certifiers.)
-   The certifiers are then run on all generated CPFs.

The more detailed technical description for the certified competition is as follows.

-   Termination tools should provide a script which gets as only arguments the name of the TRS-file (in XTC-format) and the timeout in seconds.

> They should output YES / NO / MAYBE where in the first two cases a proof in [CPF-format (version 2.?)](http://cl-informatik.uibk.ac.at/software/cpf/) has to be printed afterwards. Whereas the general format of CPF 2.? has already been fixed, last minute extensions are accepted until June 17 as long as they are conservative, i.e., do not conflict with existing elements. Every output that does not correspond to this format will be refused. (This is done via xmllint example_proof.xml --huge --noout --schema cpf.xsd)

> To ensure that a (non)termination proof for the right TRS is given, afterwards the script checkEquality.sh [termination/nonTermination] is called which are only successful if the TRS in the XTC-format is the same as the one in the CPF-format and if the proof goal corresponds to the YES / NO answer. Note, that for the equality testing no permutation of rules or renaming of variables is allowed. The script is available for testing from the [CPF-website](http://cl-informatik.uibk.ac.at/software/cpf/).

> For complexity tools the workflow is the same, where from the answer YES(\*,O(n\^i)) / YES(\*,O(1)) the polynomial degree i / 0 of the complexity is extracted, and the script checkEquality.sh [i/0] is called.

-   Certifier can either be in one-pass or two-pass mode and this can be indicated when submitting a certifier.

> In one-pass mode, it is assumed that there is one script which takes as input a CPF-file and the XTC-file in this order and terminates normally if the proof is accepted, and with some error-code if it is not accepted. If the certifier does not accept, it should start its output with UNSUPPORTED or REJECTED on stdout, to differentiate between both outcomes.

> In two-pass mode, there have to be two scripts. The first one takes as input a CPF-file and the XTC-file as before and produces some proof-script on standard-out if everything is fine or exits with some error-code which is interpreted as UNSUPPORTED. The second script is then invoked with the filename of the proof-script and should call the corresponding proof-assistent like Coq, Isabelle, ... It should again exit normally if the proof-script is accepted and with some error-code, otherwise, which is interpreted as REJECTED. Here, both the generated proof-script as well as the output of Coq, Isabelle, ... will be stored.

> In two-pass mode the corresponding times are accumulated. For example, if the first script takes n seconds and there is a global timeout of m seconds, then the second script will be aborted after (m-n) seconds.
