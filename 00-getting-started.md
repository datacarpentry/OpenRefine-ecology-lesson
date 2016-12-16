---
layout: lesson
root: .
title: Getting Started with Open Refine
minutes: .
---

# Learning Objectives

* Motivate participants to clean, organize, enhance data before inserting it into a database or merging it with other data files.
* Introduce participants to Open Refine as a powerful data-cleaning tool.
* Encourage dataset exploration; look at the data with the visualization tools in Open Refine.

----------------------------------------------------

# Lesson

## Motivations for the Open Refine Lesson

* It's really important that you know what you did. More journals/grants/etc. are also making it important for them to know what you did. You can capture all steps done to your data in Open Refine to the raw file and share them with your publication as supplemental material.
* All steps are easily reversed in Refine.
* You _must_ save your work to a new file; Refine _does not_ modify your original dataset.
* Data is often very messy - and this tool saves a lot of cleaning headaches.
* Data cleaning steps often need repeating with multiple files. Refine is perfect for speeding up repetitive tasks.
* Some concepts like clustering algorithms are quite complex, but Refine makes it easy to introduce them, use them, and show their power.

## Before we get started

* Check that you have Firefox or Chrome browsers installed. Open Refine runs in your default browser. It will not run correctly in Internet Explorer.
* Download software from [http://openrefine.org](http://openrefine.org) if you have not done this yet.
* Unzip the downloaded file into a directory by double-clicking it (Mac) or right-clicking and selecting "Extract..." on Windows. Name that directory something like Open-Refine.
* Go to your newly created Open-Refine directory.
* Launch Open Refine
  * Windows: Click the google-refine.exe (this will launch a command prompt window, but you can ignore that and wait for the browser to launch)
  * Mac: Drag icon into Applications folder, and Ctrl-click/Open... it. (See [this article](https://support.apple.com/kb/PH21769?locale=en_US) for more information on what you're doing here.)
  * Linux: Type `./refine` into the terminal within the OpenRefine directory
* Note: this is a Java program that runs on your machine (not in the cloud). It runs inside your browser, but no web connection is needed.
* If you are using a different browser, or OpenRefine does not automatically open for you, point your browser at http://127.0.0.1:3333/ or http://localhost:3333 to launch the program.

## Basics of Open Refine

You can find out a lot more about Open Refine at [http://openrefine.org]() and check out some great introductory videos. There is a [Google Group](https://groups.google.com/forum/?hl=en#!forum/openrefine) that can answer a lot of beginner questions and problems. There is also an [Open Refine Google Plus community](https://plus.google.com/communities/117280693504889048168) where you can find a lot of help and a lot of folks from the life sciences are members. As with other programs of this type, Open Refine libraries are available too, where you can find a script you need and copy it into your Refine instance to run it on your dataset.

## Features
* Open source ([source on GitHub](https://github.com/OpenRefine/OpenRefine)).
* A large growing community, from novice to expert, ready to help.
* Works with large-ish datasets (100,000 rows). Does not scale to many millions. (yet).

Next: [Working with OpenRefine](01-working-with-openrefine.html)
