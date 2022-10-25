---
layout: page
title: Setup
---

> ## Data
> **Download** the data file [Portal_rodents_19772002_simplified.csv](https://github.com/villanueval/OpenRefine-ecology-lesson/raw/gh-pages/data/Portal_rodents_19772002_simplified.csv), which is a csv file that will open in a new browser tab. Be sure to right click or control click in order to save the file (NOTE: In Safari, right click and select `Download linked file`; in Chrome and Firefox, right-click and select `Save link as...`). Make a note of the location (i.e. the folder, your Desktop) to which you save the file.
>
> ### About the data
> The data for this lesson is a part of the Data Carpentry Ecology workshop.
> It is a teaching version of the Portal Database. The data in this lesson
> is a subset of the teaching version that has been intentionally 'messed up'
> for this lesson.
>
> The data for this lesson and the workshop are in the
> [Portal Project Teaching Database](https://figshare.com/articles/Portal_Project_Teaching_Database/1314459)
> available on FigShare, with a CC-BY license
> available for reuse.
{: .prereq}

> ## Software
>
> For this lesson you will need **OpenRefine version 3.6.2** and a web browser.
>
> Note: OpenRefine is a Java program that runs on your machine (not in the cloud). It runs inside your browser, but no web connection is needed.
>
> Download OpenRefine version 3.6.2 from [http://openrefine.org/download.html](http://openrefine.org/download.html).
> * Do not select beta versions or the release candidates.
> * If you are on Windows and do not have Java installed, download the version `Windows kit with embedded Java`.
> * Unzip the downloaded file into a directory and name that directory something like OpenRefine.
> * Check below for further instructions depending on your operating system.
>
> OpenRefine requires one of these web browsers:
>  * Google Chrome
>  * Chromium
>  * Opera
>  * Microsoft Edge
>  
> OpenRefine has some issues with Firefox. Internet Explorer is not supported.
>
> Note: Other versions of OpenRefine should work, but the results might be different due to changes in the software or default settings.
{: .prereq}


### Windows

- Go to your newly created OpenRefine directory.
- Launch OpenRefine by double clicking on `openrefine.exe` (this will launch a command prompt window first; ignore that, and wait for OpenRefine to launch in the web browser, which is where you will interact with the program).
  - If Windows displays a blue window titled `Microsoft Defender SmartScreen prevented an unrecognized app from starting`, click on `More info` and then click on `Run anyway`.
- If you are using a different browser, or OpenRefine does not automatically open for you, point your browser at http://127.0.0.1:3333/ or http://localhost:3333 to launch the program.

### Mac

- Go to your newly created OpenRefine directory.
- Drag the OpenRefine icon into Applications folder, and `Ctrl-click/Open…` it.
  - If Mac shows an error that it cannot verify the developer, `Right-click` or `Ctrl-click` the icon and select `Open`. If it does not allow to open the program, repeat the process and there will be an `Open` button the second time. Additional details [here](https://github.com/OpenRefine/OpenRefine/issues/2191).
- If you are using a different browser, or OpenRefine does not automatically open for you, point your browser at http://127.0.0.1:3333/ or http://localhost:3333 to launch the program.

### Linux

- Navigate to your newly created OpenRefine directory using the command line.
- Type `./refine` into the terminal within the OpenRefine directory
- If you are using a different browser, or OpenRefine does not automatically open for you, point your browser at http://127.0.0.1:3333/ or http://localhost:3333 to launch the program.
