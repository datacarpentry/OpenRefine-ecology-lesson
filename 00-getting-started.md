---
layout: lesson
root: .
title: Getting Started with Open Refine
minutes: 
---

# Learning Objectives

* Motivate participants to clean, organize, enhance data before inserting it into a database or merging it with other data files.
* Introduce participants to Open Refine as a powerful data-cleaning tool.
* Encourage dataset exploration; look at the data with the visualization tools in Open Refine.

----------------------------------------------------

# Lesson

## Motivations for the Open Refine Lesson

* Data is often very messy - and Open Refine saves a lot of cleaning headaches.
* Data cleaning steps often need repeating with multiple files. Open Refine is perfect for speeding up repetitive tasks.
* Although Open Refine runs in a web browser, it keeps all your data locally on your computer - your data file is not sent to any remote site or server.
* All data modification steps are easily reversed in Open Refine. Also, your original data file is not modified, if you want to save your changes you explicitly need to export it to a new data file.
* It's really important that you know what you did to the data. More journals/grants/etc. are also expecting you to know (and show) what you did. You can capture all steps done to your data in Open Refine to a script and share these with your publication as supplemental material.
* Some concepts like clustering algorithms are quite complex, but Open Refine makes it easy to introduce them, use them, and show their power.


## Before we get started

* Check that you have Firefox browser installed. Open Refine runs in this browser. It will not run in IE.
* Download software from [http://openrefine.org](http://openrefine.org) if you have not done this yet.
* Unzip the downloaded file into a directory. Name that directory something like Open-Refine
* Note that "double-clicking" a zipped file on a windows machine sometimes results in a correctly unzipped set of files, other times, this is not successful. Try installing 7-Zip (http://www.7-zip.org) and use 7-Zip to extract all files from the zipped file to the desired directory.
* Go to your newly created Open-Refine directory.
* Launch Open Refine
  * Windows: Click the google-refine.exe
  * Mac: Drag icon into Applications folder and double-click it
  * Linux: Run ./refine
* Note, this is a Java program that runs on your machine (not in the cloud). It runs inside the Firefox browser, but no web connection is needed.
* If you are using a different browser, or OpenRefine does not automatically open for you, point your browser at http://127.0.0.1:3333/ to launch the program.

## Basics of Open Refine

You can find out a lot more about Open Refine at http://openrefine.org and check out some great introductory videos. There is also an Open Refine Google Plus community https://plus.google.com/communities/117280693504889048168 where you can find a lot of help and a lot of folks from the life sciences are members. As with other programs of this type, Open Refine libraries are available too, where you can find a script you need and copy it into your Open Refine instance to run it on your dataset.

* Open source.
* A large growing community, from novice to expert, ready to help.
* Works with large-ish datasets (100,000 rows). Does not scale to many millions. (yet).

Next: [Working with OpenRefine](01-working-with-openrefine.html)
