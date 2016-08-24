---
title: C Programs
permalink: /C_Programs/
---

[Category:Categories](/Category:Categories "wikilink")

Proposed semantics
------------------

-   The starting point is the main function without arguments.

-   Functions which are only declared, but not defined, are considered to be terminating, have no side effects, and return a non-deterministic value according to the function's return type.

-   The special (and only declared) function __VERIFIER_nondet_String() returns a non-deterministic C String, i.e., a pointer to some freshly allocated memory where the last byte of this allocation is the value '\\0' (we may provide a standard implementation for this function, but provers are allowed to hard-code its semantics).

-   In C, memory-unsafe programs can behave arbitrarily. Therefore, neither YES nor NO is a correct result for programs violating memory safety. So a proof of memory safety needs to be part of a termination proof. If there is interest for that, we could also offer an additional category where memory safety can be assumed and where no programs are allowed which might violate memory safety.

-   We assume integers to be mathematical integers, i.e., over- or underflows cannot occur. If there is interest for that, we could also offer an additional category where overflows of unsigned integers are treated as two's complement overflows and where neither YES nor NO is a correct result for programs with overflows of signed integers.

-   Integer division by negative numbers is assumed to be done by truncation towards zero (as in the C99 standard and no implementation-defined behavior as in the C89 standard).

-   We assume that allocation of memory always succeeds, i.e., alloca and malloc never return null pointers and allocation of constant size arrays cannot lead to undefined behavior. Moreover, read access to allocated, but uninitialized memory is assumed to just return a non-deterministic value.

-   We assume the following sizes of primitive data types:

`    bool: 8 bit`
`    char: 8 bit`
`    short: 16 bit`
`    int: 32 bit`
`    long: 64 bit`
`    float: 32 bit`
`    double: 64 bit`
`    pointer: 64 bit`

-   Programs where the evaluation order of operations is not defined according to the C standard and where different execution orders of the operations lead to different resulting states are not allowed. As an example, the program

`int main(){`
`    int x = 0;`
`    while( x++ == x );`
`}`


is not allowed since the evaluation order between ++ and == is not defined according to the C standard and if ++ is evaluated first, the program terminates whereas it does not if == is evaluated first. To enable an automatic check for such programs, we disallow all programs `P` where the execution of `gcc -c -std=c99 -Wsequence-point P` shows a warning.

-   The scoring should be the same as in all other categories (proving termination or non-termination both gives 1 point and there will be a penalty for wrong answers).

-   Time limit: 300 seconds.

See also
--------

Section D. of [Termination Competition on Software Verification (SV-COMP)](http://sv-comp.sosy-lab.org/2014/demo.php)
