---
title: Star Exec Presenter
permalink: /Star_Exec_Presenter/
---

While the competition will be run on Starexec, results will be presented on a separate platform that is currently under construction at HTWK Leipzig.

Notes for implementation:

-   the executor merges stdout and stderr and prepends each line by a time stamp (separated by TAB). This time stamp must be removed...
    -   by the postprocessor (running on starexec, and grepping for the YES/NO result)
    -   by the presenter (reading jobpair-information) especially for re-uploading the output for later certification.
