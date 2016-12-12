---
layout: lesson
root: .
title: Getting Started with OpenRefine
minutes:
---

# Learning Objectives

* Describe OpenRefine’s uses and applications.
* Differentiate data cleaning from data organization.
* Experiment with OpenRefine’s user interface.
* Locate helpful resources to learn more about OpenRefine.

----------------------------------------------------

# Lesson

## Motivations for the OpenRefine Lesson

* It is important to know what you did to your data. Additionally, journals, granting agencies, and other institutions are requiring documentation of the steps you took when working with your data. With OpenRefine, you can capture all actions applied to your raw data and share them with your publication as supplemental material.
* All actions are easily reversed in OpenRefine.
* You _must_ save your work to a new file; OpenRefine _does not_ modify your original dataset.
* Data is often very messy, and this tool saves a lot of time on cleaning headaches.
* Data cleaning steps often need repeating with multiple files. OpenRefine is perfect for speeding up repetitive tasks by replaying previous actions on multiple datasets.
* Some concepts such as clustering algorithms are quite complex, but OpenRefine makes it easy to introduce them, use them, and show their power.

## Before we get started

* Check that you have Firefox or Chrome browsers installed and set as your default browser. OpenRefine runs in your default browser. It will not run correctly in Internet Explorer.
* Download software from [http://openrefine.org](http://openrefine.org) if you have not done this yet.
* Unzip the downloaded file into a directory by double-clicking it (Mac) or right-clicking and selecting "Extract..." on Windows. Name that directory something like OpenRefine.
* Go to your newly created OpenRefine directory.
* Launch OpenRefine
  * Windows: Click the google-refine.exe (this will launch a command prompt window, but you can ignore that and wait for the browser to launch)
  * Mac: Drag icon into Applications folder, and Ctrl-click/Open... it. (See [this article](https://support.apple.com/kb/PH21769?locale=en_US) for more information on what you're doing here.)
  * Linux: Type `./refine` into the terminal within the OpenRefine directory
* Note: this is a Java program that runs on your machine (not in the cloud). It runs inside your browser, but no web connection is needed.
* If you are using a different browser, or OpenRefine does not automatically open for you, point your browser at http://127.0.0.1:3333/ or http://localhost:3333 to launch the program.

## Basics of OpenRefine

You can find out a lot more about OpenRefine at [http://openrefine.org]() and check out some great introductory videos. There is a [Google Group](https://groups.google.com/forum/?hl=en#!forum/openrefine) that can answer a lot of beginner questions and problems. There is also an [OpenRefine Google Plus community](https://plus.google.com/communities/117280693504889048168) where you can find a lot of help and a lot of folks from the life sciences are members. As with other programs of this type, OpenRefine libraries are available too, where you can find a script you need and copy it into your OpenRefine instance to run it on your dataset.

## Features
* Open source ([source on GitHub](https://github.com/OpenRefine/OpenRefine)).
* A large growing community, from novice to expert, ready to help.
* Works with large-ish datasets (100,000 rows). Does not scale to many millions. (yet).

Next: [Working with OpenRefine](01-working-with-openrefine.html)
