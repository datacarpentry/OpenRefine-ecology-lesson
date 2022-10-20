---
layout: page
title: "Instructor Notes"
---

## Lesson motivation and learning objectives


## Lesson design

* This lesson takes about 100-115 minutes with learners installing the tool and working through the examples and challenges.

## Technical tips and tricks

Ask the learners to install and test running the program before the workshop. This will reveal usual problems that can be fixed before the workshop.

### OpenRefine version

The current version of the lesson has been tested with OpenRefine 3.6.2. Using older versions is not recommended, behavior may be different and cause confusion in the learners.

Windows users should download the "Windows kit with embedded Java" version from the [Download page](https://openrefine.org/download.html) to avoid having to install Java.

Mac users can use the kit available in the [Download page](https://openrefine.org/download.html), Java does not have to be installed separately.

Linux users must install Java in their system.

### Creating a Project

Start the program. (Double-click on the openrefine.exe file. A command line box might show up, this needs to be left open, and OpenRefine will open in the browser).

Note the file types OpenRefine handles: TSV, CSF, *SV, Excel (.xls .xlsx), JSON, XML, RDF as XML, Google Data documents. Support for other formats can be added with OpenRefine extensions.

In this first step, we'll browse our computer to the sample data file for this lesson (If you haven't already, download the data from:
https://ndownloader.figshare.com/files/7823341). In this case, I've modified the Portal_rodents.csv file. I added several columns: scientificName, locality, county, state, country and I generated several more columns in the lesson itself (JSON, decimalLatitude, decimalLongitude). Data in locality, county, country, JSON, decimalLatitude and decimalLongitude are contrived and are in no way related to the original dataset.

**Once OpenRefine is open, you'll be asked if you want to Create, Open, or Import a Project.**

  - Click Browse, find Portal_rodents_19772002_scinameUUIDs.csv
  - Click next to open Portal_rodents_19772002_scinameUUIDs.csv
  - OpenRefine gives you a preview - a chance to show you it understood the file. If, for example, your file was really tab-delimited, the preview might look strange, you would choose the correct separator in the box shown and click "update preview."
  - If all looks well, click _Create Project._

### Faceting

*Exploring data by applying multiple filters*

OpenRefine supports faceted browsing as a mechanism for

* seeing a big picture of your data, and
* filtering down to just the subset of rows that you want to change in bulk.

Typically, you create a facet on a particular column. The facet summarizes the cells in that column to give you a big picture of that column, and allows you to filter to some subset of rows for which their cells in that column satisfy some constraint. That's a bit abstract, so let's jump into some examples.

[More on faceting](https://docs.openrefine.org/manual/facets/)

  - Scroll over to the scientificName column
  - Click the down arrow and choose Facet > Text facet
  - In the left margin, you'll see a box containing every unique value in the scientificName column and OpenRefine shows you how many times that value occurs in the column (a count), and allows you to sort (order) your facets by name or count.
  - Edit. Note that at any time, in any cell of the Facet box, or data cell in the OpenRefine window, you have access to "edit" and can fix an error immediately. OpenRefine will even ask you if you'd like to make that same correction to every value it finds like that one (or not).

### Clustering
In OpenRefine, clustering refers to the operation of "finding groups of different values that might be alternative representations of the same thing". For example, the two strings "New York" and "new york" are very likely to refer to the same concept and just have capitalization differences. Likewise, "Gödel" and "Godel" probably refer to the same person.

One of the most magical bits of OpenRefine, the moment you realize what you've been missing. OpenRefine has several clustering algorithms built in. Experiment with them, and learn more about these algorithms and how they work.

[More on clustering](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth)

  - In this example, in the scientificName Text Facet we created in the step above, click the _Cluster_ button.
  - In the resulting pop-up window, you can change the algorithm method, and keying function. Try different combinations to see the difference.
  - For example, with this dataset, the _nearest neighbor_ method with the _PPM_ keying function shows the power of clustering the best.
  - Intentional errors in these scientific names have been introduced to show how errors (typos) in any position can be found with this method. All errors can then be fixed by simply entering the correct value in the box on the right. Often, the algorithm has guessed correctly.
  - After corrections are made in this window, you can either Merge and Close the Cluster pop-up, or Merge and Re-cluster.

### Split / Undo - Redo

If data in a column needs to be split into multiple columns, and the strings in the cells are separated by a common separator (say a comma, or a space), you can use that separator to divide up the bits into their own columns.

  - Go to the drop-down tab at the top of the column that you need to split into multiple columns
  - For example, go to the scientificName column > from drop-down choose Edit Column > Split into several columns
  - In the pop-up, for separator, remove the comma, put in a space
  - Remove the check in the box that says "remove column after splitting"
  - You'll get two extra columns called, in this case: scientificName 1, scientificName 2
  - To Undo create columns, look just above the scientificName cluster in the left side of the screen. Click where it says Undo / Redo. Click back one step (all steps, all changes are saved here). Just go back to the previous step and click. The extra columns will be gone.

## Common problems

* If learners are using a browser other than Firefox, or OpenRefine does not automatically open for them when they click the .exe file, have them point their browser at http://127.0.0.1:3333/ or http://localhost:3333 to launch the program.

* Mac users with the newest operating system will have to allow this to run by "allowing everything" to run. They can change the setting back after the exercise.

* Some students will run into issues with
  - unzipping, don't run from the zip file
  - finding the .exe file once the software has been unzipped
  - finding the data file on their computers after downloading
