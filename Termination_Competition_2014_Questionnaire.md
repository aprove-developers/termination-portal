---
title: Termination Competition 2014 Questionnaire
permalink: /Termination_Competition_2014_Questionnaire/
---

The following questions regarding Star-Exec are being asked by Aaron Stump and Cesare Tinelli, to all Summer 2014 competition organizers. I (J.W.) will answer, by August 5, and I'd like to collect your comments here. Just enter below the question, but keep the question intact. (I am dropping some administrative questions, but keep the original numbering.)

NOTE: this questionnaire is now CLOSED.

4. What were the advantages and disadvantages of using StarExec for you as competition organizer, in comparison with whatever alternative you would have utilized instead of StarExec?
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

5. What were the most positive aspects of your experience running your competition on StarExec?
-----------------------------------------------------------------------------------------------

It is not longer necessary to maintain hardware and software for each competition separately. This makes the competition more independent of individual research groups and their funding.

The computing power allowed us to run the competition in much less time than before.

6. What were the negative aspects?
----------------------------------

It was not (easily) possible to install auxiliary software needed by the tools.

It was not possible to access remote machines from StarExec, which is needed for some commercial tools that are not willing to let their binaries run on StarExec itself.

Restrictions (e.g., on the name length) for benchmarks prevented the submission of whole benchmark sets instead of just those files violating the restrictions. Only one error was displayed at a time and the user had to successively remove files from the benchmark set before the submission succeeded.

The allowed characters for tool descriptions were very restricted and did not allow a nice representation, e.g., of author names containing special characters. In particular, the restrictions were not documented in a way that the user would know about the restrictions beforehand, but needed to try out several versions until a description was accepted.

It took a lot of time (and hint from a colleague) until I figured out that I can use drag&drop for certain operations.

While uploading a large file you see immediately a web page that shows the progress. However, I was not able to recognize that this is a web page that shows your upload progress. To me it looked like a web page that shows a strange error message.

I wanted to delete a solver. In order to do this I had to do three actions! (delete link, recycle solver, empty recycle bin). Star-Exec told me that I exceed my disk space. First, I was not able to understand why because I wrongly assumed that I had deleted my old solvers. (I forgot some of these three actions).

Solver description does not allow characters like parenthesis or hyphen.

I wanted to put benchmarks and solvers into different spaces because one is public the other is not. But now, it was not easy to create jobs. I always had to link the current solver version into the benchmark space and create the job in the space where I put the benchmarks.

Debugging was time consuming In order to find the next problem, why our solver was not running on Star-Exec I just needed to run the solver on a single benchmark for 10 seconds. However I had to wait for several hours until my job was scheduled. Maybe a queue with fixed 10 second deadline is helpful.

Old Software. The Linux distribution on Star-Exec is very old. I was not able to use a current (precompiled) version of Z3.

10. Where do you think we should focus our development efforts going forward?
-----------------------------------------------------------------------------

A few of the things we are considering are: additional interfaces for viewing job results (maybe similar to the 2-dimensional grid used in Termination; other suggestions?), solver pipelines (output from one stage becomes benchmark for input to the next stage; other details to be determined), more work to make it possible to install and run StarExec on your own server or computer (abstract out security-critical details, installation documention, and abstract the interface to GridEngine so you can use a different third-party tool to run jobs on a cluster, or even just your own desktop), commitment to and documentation of the URLs used for communicating directly with the server. Documentation of restrictions and registration procedures.

There should really be an easy way to install additional software. In the long run, bundling all needed components (JRE, Mono, Clang, SMT-Solver...) is not an acceptable alternative.

11. Do you expect you or your colleagues will likely want to run the next edition of your competition on StarExec?
------------------------------------------------------------------------------------------------------------------

12. How adequate was the help you were able to get either directly from the StarExec team or from the forum?
------------------------------------------------------------------------------------------------------------

Response times could easily exceed one or in some cases even several weeks.

13. How satisfied do you perceive the participants in your competition were with their experience using StarExec?
-----------------------------------------------------------------------------------------------------------------

The submission phase felt very chaotic and submissions involved much more work for the participants than in previous years. The execution phase seemed to run smoothly (at least from the participants' perspective) and very fast.

14. Were there any recurring issues or complaints from the participants in your competition?
--------------------------------------------------------------------------------------------

See answers to question 6.

15. Any further comments or suggestions?
----------------------------------------