---
title: Termination Competition Problem Selection Algorithm
permalink: /Termination_Competition_Problem_Selection_Algorithm/
---

We will fix some number "c" with 0 \< c \< 1. This number indicates the percentage of problems to be taken from each family. So in principle, we would like to choose c \* |F| problems from each family F. Here, |F| is the number of problems in the family F.

In order to avoid problems with very large or very small families, there will be two additional numbers "a" and "b" with 0 \< a \< b. Here, "a" is the minimum number of examples that should be chosen from each family. Similarly, "b" is the maximum number of examples that should be chosen from each family.

To illustrate this, let c = 1/2 and let a = 10 and b = 100. Then for a family F with 50 problems, we would randomly choose c \* |F| = 25 problems from the family F. For a family F with 16 problems, we would not choose c \* |F| = 8 problems, because this number would be smaller than a = 10. Instead, we would choose a = 10 problems randomly. For a family with 300 problems, we would not choose c \* |F| = 150 problems, because this number would be larger than b = 100. Instead, we would choose b = 100 problems randomly.

To summarize, for every family F, we randomly choose:

`   c * |F| problems, if a <= c*|F| <= b`
`   a       problems, if c*|F| < a           `
`   b       problems, if b < c*|F|`

This rule is applied to every family with the same numbers a,b,c.

The numbers "a", "b" and "c" will be chosen such that the competition can complete in time, which depends on the number of new TPDB submissions and participants. (The numbers have been a = 10, b = 75, c = 0.3 in the last year.)
