---
title: Star Exec Test
permalink: /Star_Exec_Test/
---

This is an collection of notes that I (JW) am making while using the Star Exec service. The plan is to submit some benchmarks (from TPDB), submit some solvers (initially, my own Matchbox because that's easiest for me to modify if necessary), and run some jobs. Ordering of notes is mostly by time (during that process), and not by importance.

-   password is transmitted via http (not https)?
-   white on black lettering is hurting my eyes. Please make it black on white. (The "public dev wiki" does it right)
-   "report a bug" equals "mail to developer". I would much prefer a bug tracker that is world-readable, to avoid double reports, and be able to follow progress.

Defining a benchmark type

-   order of user guide is inverted (I am doing: 1. define benchmark type, 2. upload benchmark, 3. upload solver)
-   when adding a benchmark type, platform asks for name/description/processor. I don't want a processor, but it seems I am required to do so. Platform could provide a default processor that just says "starexec-valid=true".
-   definining the benchmark type (SRS_Standard) seems OK.

Uploading a benchmark set

-   the "upload benchmarks" in the space explorer is somewhat hidden (need to expand the "root" symbol in the left bar). I upload a .tar.gz file that corresponds to the SRS_Standard subdir of tpdb-8.0.6. There are several import options, I keep the defaults. Import seems OK, I see the directory structure in the left bar.

Uploading a solver

-   platform spec says that executable must be named ./bin/run_\* (after extracting the archive). Hm, that will most likely result in a [tar bomb](http://www.linfo.org/tarbomb.html).
-   spec does not say (but Ben told me) that OS/Hardware is Redhat 5.8/x86_64. So I am compiling and statically linking matchbox in a Centos5.8 VM, and add run_cert and run_nocert bash scripts. Upload seems OK, I see the two run_ scripts as "configurations".

Defining and starting a Job

-   I want to run matchbox on a subset of the benchmarks that I just uploaded. I select 20 seconds timeout. The unit of measurement is missing when entering the timeout (minutes? seconds? but it is in the user guide) I leave "postprocessor = none" as it is.
-   the "next" button is on the far right. I have a narrow browser window, so I need to scroll.
-   when I select "choose benchmark, next", I don't see how to select a subset (it shows "benchmark/empty").
-   so I go back to "run all benchmarks" where I don't know the difference between "in current space" and "in current space with hierarchy". (platform should show the benchmark tree, and provide "next" button for selection of subsets anyway)
-   I say "run Ternmination" and "submit". Resulting in "http 400 - bad request - the create job request was malformed"
-   There's an option to go back, which I do, and chose "run termination and hierarchy", and this seems to work.

Looking at job's output

-   the job that I started does appear in a summary view (as described in "Gathering result" from user guide). I am trying to get "job details" by clicking on the summary/status line but this does not seem to work (the web server hangs?)
-   I don't see an easy way to update the summary view. (If I click reload in the browser, I am back to the start screen).
-   Here I'd wish that the job has an URL so it can be bookmarked and viewed later (and if it was public, the URL should work without logging in first)
-   I figure that extraction of the solver's answer (the YES/NO from first line of stdout) should have been done by a post-processor, producing like "starexec-result=YES"
-   Now, starexec seems to hang completely. Could this indicate that matchbox is indeed running ... Sure it will try to allocate space, and use some cores, but I hope the platform applies reasonable ulimits.

Update on output: this seems to work now, cf. [<http://starexec.cs.uiowa.edu/starexec/services/jobs/pairs/29550/stdout?limit>=-1] [<http://starexec.cs.uiowa.edu/starexec/services/jobs/pairs/29549/stdout?limit>=-1]. I can also download a .tar.gz archive with complete output

Output format, post-processors

-   looking at the above output, it seems that stdout is merged with stderr. This would make life hard for the post-processor (if the solver outputs diagnostics on stderr before writing final result on stdout).
