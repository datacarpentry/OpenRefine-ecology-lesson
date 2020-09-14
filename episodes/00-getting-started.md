---
title: "Introduction"
teaching: 10
exercises: 0
questions:
- "What is OpenRefine useful for?"
objectives:
- "Describe OpenRefine’s uses and applications."
- "Differentiate data cleaning from data organization."
- "Experiment with OpenRefine’s user interface."
- "Locate helpful resources to learn more about OpenRefine."
keypoints:
- "OpenRefine is a powerful, free and open source tool that can be used for data cleaning."
- "OpenRefine will automatically track any steps you take in working with your data."
---

# Lesson

## Motivations for the OpenRefine Lesson


- It is important to know what you did to your data. Additionally, journals,
  granting agencies, and other institutions are requiring documentation of the
  steps you took when working with your data. With OpenRefine, you can capture
  all actions applied to your raw data and share them with your publication as
  supplemental material.
- You *must* export your modified dataset to a new file: OpenRefine does not
  write back into your original sources. If you don't save it, your OpenRefine
  work will be lost.
- Any operation that changes the data in OpenRefine can be easily reversed or
  undone.
- Data is often very messy, and this tool saves a lot of time on cleaning
  headaches.
- Data cleaning steps often need repeating with multiple files. OpenRefine is
  perfect for speeding up repetitive tasks by replaying previous actions on
  multiple datasets.
- Some concepts such as clustering algorithms are quite complex, but OpenRefine
  makes it easy to introduce them, use them, and show their power.
 
## Before we get started


The following setup is necessary before we can get started (instructions [here](../setup.html)).

Do you need help with any of the following?

- Download and install software from <http://openrefine.org/download.html>
- Download this [data file](https://ndownloader.figshare.com/files/7823341) and save to your desktop
- Launch OpenRefine in Mozilla Firefox or Google Chrome
- If after installation and running OpenRefine, it does not automatically open for you, point your browser at <http://127.0.0.1:3333/> or <http://localhost:3333/> to launch the program.


What is OpenRefine?

  - OpenRefine is a Java program that runs on your machine (not in the cloud): it is a desktop application that uses your web browser as a graphical interface. No internet connection is needed, and none of the data or commands you enter in OpenRefine are sent to a remote server.
  - OpenRefine does not modify your original dataset. All actions are easily reversed in OpenRefine and you can capture all the actions applied to your data and share this documentation with your publication as supplemental material. OpenRefine saves as you go. You can return to the project at any time to pick up where you left off, or export your data to a new file.
 - OpenRefine can be used to standardise and clean data across your file.
    
It can help you:

- Get an overview of a data set
- Resolve inconsistencies in a data set
- Help you split data up into more granular parts
- Match local data up to other data sets
- Enhance a data set with data from other sources
- Save a set of data cleaning steps to replay on multiple files


OpenRefine is a powerful, free and open source tool with a large growing community of practice. More help can be found at <http://openrefine.org>.



## Basics of OpenRefine

You can find out a lot more about OpenRefine at [http://openrefine.org](http://openrefine.org) and check out some great [introductory videos](https://www.youtube.com/channel/UCqwSVsJ8CWD9pQUZDbJC1ew). There is a [Google Group](https://groups.google.com/forum/#!forum/openrefine) that can answer a lot of beginner questions and problems. OpenRefine [recipes](https://github.com/OpenRefine/OpenRefine/wiki/Recipes), scripts, projects, and extensions are available too, where you can find and copy them into your OpenRefine instance to run on your dataset.

The OpenRefine GitHub wiki page has a [reference](https://github.com/OpenRefine/OpenRefine/wiki/GREL-Functions) of the General Refine Expression Language (GREL).

## Features

* Open source ([source on GitHub](https://github.com/OpenRefine/OpenRefine)).
* A large growing community, from novice to expert, ready to help.
* Works with large-ish datasets (100,000 rows). Does not scale to many millions. (yet).

