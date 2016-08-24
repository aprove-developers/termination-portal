---
title: Outermost
permalink: /Outermost/
---

This page is to record the current status of the proposed Outermost Strategy Category of the Termination Competition.

The first installation of this event is planned for November 4, 2008.

Overview of the Event
---------------------

It is a challenging topic to automatically prove termination of term rewriting with respect to outermost rewriting strategy. This strategy is especially interesting since it establishes the basis of lazy programming languages as Haskell, Miranda or Clean where programming with infinite structures is common practice and therefore full termination (with respect to an arbitrary strategy) cannot be expected.

-   Hans Zantema:

We should decide whether we take ground or open. For instance,

`   f(x,a)      -> f(x,b)`
`   b           -> a`
`   f(a,x)      -> a`
`   f(b,x)      -> a`
`   f(f(x,y),z) -> a`

is ground outermost terminating (when restricting to symbols occurring in the TRS), but not outermost terminating if we allow open terms or allowed to extend the signature. Since the open variant is more robust (it does not change by extending the signature) I propose to allow open terms in the definition of outermost termination, by which the above example is NOT outermost terminating.

-   René Thiemann:

I would also prefer the outermost variant, since currently some methods (for disproving) are only correct for outermost termination and not for outermost ground termination. Moreover, by extending the signature every tool that only can prove outermost ground termination can also prove outermost termination.

-   Joerg Endrullis:

I also tend to outermost termination including open terms.

Problem selection
-----------------

-   René Thiemann suggests:

All TRSs where full termination has not already been proven. If there is a special category of "interesting" outermost-examples then I suggest to add all non-terminating TRSs to this category. The reason is that these examples are interesting since only provers which are aware of the outermost-strategy can solve these examples.

-   Hans Zantema:

I agree with Joerg that apart from these TRSs where full termination has not already been proven special TRSs with outermost strategy should be considered. Giving both of these subcategories equal weight is OK with me. The main point to be done now is to extend the present list of only 6 TRSs in TPDB with outermost strategy. A competiton does not make sense before this list has some reasonable size and content.

A proposal for 50 new examples is found in <http://www.win.tue.nl/~hzantema/ex.zip>. It is my intension to submit these. If you have remarks, or suggestions for extensions, please let me know.

-   Joerg Endrullis:

Yes, I will add some more examples to the outermost category. Unfortunately the search in the termination competition interface does not work. Searching for outermost examples yields always the empty result, such that one cannot see which examples are already there.

Scoring
-------

-   Joerg Endrullis suggests:

If we use all TRSs where full termination has not already been proven, then these examples will dominate the outermost category. However this is no problem, since a balance can be reached by choosing an appropriate scoring.

I would suggest to split the score. That is, give 50 points for the tool that proves most of the examples with "STRATEGY OUTERMOST" terminating, and 50 points for the tool that proves most of the "TRSs where full termination has not already been proven" to be outermost terminating. The non-winning tools get in both categories 50 \* (number of problems solved) / (number of problems solved by winner). Thus in theory a tool winning both categories obtains 100 points.

-   comment on Joerg's proposal (by René):

If the idea of a splitting is applied then I would count every valid answer for the "interesting" examples and not only the YES-answers.

Participants
------------

insert your name here if you intend to participate.

-   AProVE-team
-   Matthias Raffelsieper, Hans Zantema
-   Christian Sternagel and Rene Thiemann (TTT2)
-   Joerg Endrullis (Jambox)
-   Johannes Waldmann (Matchbox), but will need more time
