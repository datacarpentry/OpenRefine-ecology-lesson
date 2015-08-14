---
layout: lesson
root: .
title: Working with Open Refine
minutes: 
---

# Learning Objectives

* Introduce concept of facets
* Show split columns by defined separator
* Show power of include / exclude, sort by name / count
* Show the power of clustering algorithms to reveal data patterns, data snafus
* If time, show call to an API, a web service (JSON example here from a locality georeferencing service)
* If time, show how to parse the JSON returned from the service.
* Show the power of undo / redo.
* Can be used to introduce
 - scripting
 - regular expressions
 - APIs

----------------------------------------------------

# Lesson

## Creating a Project

Start the program. (Double-click on the google-refine.exe file. Java services will start on your machine, and Refine will open in your Firefox browser).

Note the file types Open Refine handles: TSV, CSF, *SV, Excel (.xls .xlsx), JSON, XML, RDF as XML, Google Data documents. Support for other formats can be added with Google Refine extensions.

In this first step, we'll browse our computer to the sample data file for this lesson. In this case, I've modified the Portal_rodents csv file. I added several columns: scientificName, locality, county, state, country and I generated several more columns in the lesson itself (JSON, decimalLatitude, decimalLongitude). Data in locality, county, country, JSON, decimalLatitude and decimalLongitude are contrived and are in no way related to the original dataset. When doing this demo, the columns: JSON, decimalLatitude, decimalLongitude can be deleted, and then recreated if time, with a call to a locality service, and subsequent parsing of the JSON data returned by the service.

**Once Refine is open, you'll be asked if you want to Create, Open, or Import a Project.**


  - Click Browse, find Portal_rodents_19772002_scinameUUIDs.csv
  - Click next to open Portal_rodents_19772002_scinameUUIDs.csv
  - Refine gives you a preview - a chance to show you it understood the file. If, for example, your file was really tab-delimited, the preview might look strange, you would choose the correct separator in the box shown and click "update preview."
  - If all looks well, click _Create Project._

## Faceting

*Exploring data by applying multiple filters*

OpenRefine supports faceted browsing as a mechanism for

* seeing a big picture of your data, and
* filtering down to just the subset of rows that you want to change in bulk.

Typically, you create a facet on a particular column. The facet summarizes the cells in that column to give you a big picture on that column, and allows you to filter to some subset of rows for which their cells in that column satisfy some constraint. That's a bit abstract, so let's jump into some examples.

[More on faceting](https://github.com/OpenRefine/OpenRefine/wiki/Faceting)


  - Scroll over to the scientificName column
  - Click the down arrow and choose > Facet > Text facet
  - In the left margin, you'll see a box containing every unique, distinct value in the scientificName column and Refine shows you how many times that value occurs in the column (a count), and allows you to sort (order) your facets by name or count.
  - Edit. Note that at any time, in any cell of the Facet box, or data cell in the Refine window, you have access to "edit" and can fix an error immediately. Refine will even ask you if you'd like to make that same correction to every value it finds like that one (or not).

## Cluster

One of the most magical bits of Refine, the moment you realize what you've been missing. Refin\
e has several clustering algorithms built in. Experiment with them, and learn more about these algorithms and how they work. 

[More on clustering](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth)

In OpenRefine, clustering refers to the operation of "finding groups of different values that might be alternative representations of the same thing". For example, the two strings "New York" and "new york" are very likely to refer to the same concept and just have capitalization differences. Likewise, "Gödel" and "Godel" probably refer to the same person.


  - In this example, in the scientificName Text Facet we created in the step above, click the _Cluster_ button.
  - In the resulting pop-up window, you can change the algorithm method, and keying function. Try different combinations to see the difference.
  - For example, with this dataset, the _nearest neighbor_ method with the _PPM_ keying function shows the power of clustering the best. 
  - Intentional errors in these scientific names have been introduced to show how errors (typos) in any position can be found with this method. All errors can then be fixed by simply entering the correct value in the box on the right. Often, the algorithm has guessed correctly. 
  - After corrections are made in this window, you can either Merge and Close the Cluster pop-up, or Merge and Re-cluster.


## Split / Leading - Trailing Whitespace / Undo - Redo

If data in a column needs to be split into multiple columns, and the strings in the cells are separated by a common separator (say a comma, or a space), you can use that separator to divide up the bits into their own columns.

  - Go to the drop-down tab at the top of the column that you need to split into multiple columns
  - For example, go to the scientificName column > from drop-down choose Edit Column > Split into several columns
  - In the pop-up, for separator, remove the comma, put in a space
  - Remove the check in the box that says "remove column after splitting"
  - You'll get two extra columns called, in this case: scientificName 1, scientificName 2
  - This will reveal an error in a few names that have spaces at the beginning (so-called leading white space).
  - These can be easily removed with another Refine feature in the column drop-down choices. See drop-down: Edit cells > Common transforms > Remove leading and trailing whitespace
  - To Undo create columns, look just above the scientificName cluster in the left side of the screen. Click where it says Undo / Redo. Click back one step (all steps, all changes are saved here). Just go back to the previous step and click. The extra columns will be gone.

## Call a Service (this example is set up to georeference locality data, but could use any service).

* For this demo, the instructor may find a web service appropriate to demonstrate.

## Scripts

* Refine saves every change, every edit you make to the dataset in a file you can save on your machine.
* IF you had 20 files to clean, and they all had the same type of errors, and all files had the same columns, you could save the script, open a new file to clean, paste in the script and run it. Voila, clean data.
* In the Undo / Redo section, click Extract, save the bits desired using the check boxes. Save the code in a .txt file. To run these steps on a new dataset, import the new dataset into Refine, open the Extract / Apply section, paste in the .txt file, click Apply.

## Export 

* Save your work when you are done by exporting it in the desire format. Save your files with meaningful names, no spaces. Refine does not change your original dataset.

#### Time estimate for this demo.
* Takes about 20 - 30 minutes to do a good demo.
* If students are going to install and then try this tool out on the provided dataset or their own dataset, it will take longer.
* Mac users with the newest operating system will have to allow this to run by "allowing everything" to run. They can change the setting back after the exercise.
* Some students will run into issues with
  - unzipping
  - finding the .exe file once the software has been unzipped
