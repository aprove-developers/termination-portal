---
title: Handling DG and SCCs
permalink: /Handling_DG_and_SCCs/
---

(draft, please extend)

Dependency Graphs
=================

how to handle approximations? for every missing edge, indicate why it is not necessary?

Strongly Connected Components
=============================

Termination Prover computes SCCs and outputs them. Proof assistant does not have to recompute SCCs (which is costly). Prover has to indicate topological ordering on SCCs. Assistant checks that there are no backward edges between components in this ordering.
