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
* Show the power of undo / redo.

----------------------------------------------------

# Lesson

## Creating a Project

Start the program. (Double-click on the google-refine.exe file. Java services will start on your machine, and Refine will open in your Firefox browser).

Note the file types Open Refine handles: TSV, CSF, *SV, Excel (.xls .xlsx), JSON, XML, RDF as XML, Google Data documents. Support for other formats can be added with Google Refine extensions.

In this first step, we'll browse our computer to the sample data file for this lesson. In this case, I've modified the Portal_rodents csv file. I added several columns: scientificName, locality, county, state, country and I generated several more columns in the lesson itself (JSON, decimalLatitude, decimalLongitude). Data in locality, county, country, JSON, decimalLatitude and decimalLongitude are contrived and are in no way related to the original dataset. When doing this demo, the columns: JSON, decimalLatitude, decimalLongitude can be deleted, and then recreated if time, with a call to a locality service, and subsequent parsing of the JSON data returned by the service.

If you haven't already, download the data from:  
[https://www.dropbox.com/s/kbb4k00eanm19lg/Portal_rodents_19772002_scinameUUIDs.csv?dl=0](https://www.dropbox.com/s/kbb4k00eanm19lg/Portal_rodents_19772002_scinameUUIDs.csv?dl=0)


**Once Refine is open, you'll be asked if you want to Create, Open, or Import a Project.**

````
  - Click Browse, find Portal_rodents_19772002_scinameUUIDs.csv
  - Click next to open Portal_rodents_19772002_scinameUUIDs.csv
  - Refine gives you a preview - a chance to show you it understood the file. If, for example, your file was really tab-delimited, the preview might look strange, you would choose the correct separator in the box shown and click "update preview."
  - If all looks well, click _Create Project._
```

## Faceting

*Exploring data by applying multiple filters*

OpenRefine supports faceted browsing as a mechanism for

* seeing a big picture of your data, and
* filtering down to just the subset of rows that you want to change in bulk.

Typically, you create a facet on a particular column. The facet summarizes the cells in that column to give you a big picture on that column, and allows you to filter to some subset of rows for which their cells in that column satisfy some constraint. That's a bit abstract, so let's jump into some examples.

[More on faceting](https://github.com/OpenRefine/OpenRefine/wiki/Faceting)

````
  - Scroll over to the scientificName column.
  - Click the down arrow and choose > Facet > Text facet.
  - In the left margin, you'll see a box containing every unique, distinct value in the scientificName column and how many times that value occurs in the column.
  - Try sorting this facet by name and by count. Do you notice any problems with the data? What are they?
  - Hover the mouse over one of the names in the Facet list. You should see that you have an "edit" function available. You could use this to fix an error immediately, and OpenRefine will ask if you want to make the same correction to every value it finds like that one (or not). But OpenRefine offers even better ways to find and fix these errors, which we'll use instead.
````

## Cluster

In OpenRefine, clustering means "finding groups of different values that might be alternative representations of the same thing". For example, the two strings "New York" and "new york" are very likely to refer to the same concept and just have capitalization differences. Likewise, "Gödel" and "Godel" probably refer to the same person. Clustering is a very powerful tool for cleaning datasets which contain misspelled or mistyped entries.
OpenRefine has several clustering algorithms built in. Experiment with them, and learn more about these algorithms and how they work. 

[More on clustering](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth)

````
  - In the scientificName Text Facet we created in the step above, click the _Cluster_ button.
  - In the resulting pop-up window, you can change the Method and the Keying Function. Try different combinations to see what different mergers of values are suggested.
  - Select the _key collision_ method and _metaphone3_ keying function. It should identify three clusters. Click the _Merge?_ box beside each, then click _Merge Selected and Recluster_ to apply the corrections to the dataset.
  - Try selecting different Methods and Keying Functions again, to see what new mergers are suggested. You may find there are still improvements that can be made, but don't Merge again; just Close when you're done.  We'll now see other operations that will help us detect and correct the remaining problems, and that have more general uses besides.
````

## Split

If data in a column needs to be split into multiple columns, and the parts are separated by a common separator (say a comma, or a space), you can use that separator to divide up the bits into their own columns.

````
  - Go to the drop-down tab at the top of the scientificName column. Choose Edit Column > Split into several columns.
  - In the pop-up, in the Separator box, replace the comma with a space.
  - Remove the check in the box that says "Remove the column".
  - Click "OK". You'll get some new columns called _scientificName 1_, _scientificName 2_, and so on.
  - Notice that in some cases _scientificName 1_ and _scientificName 2_ are empty. Why is this? What do you think we should do about it?
````

## Undo / Redo

Strings with spaces at the beginning or end are particularly hard for humans to distinguish from strings without. Having identified a few such cases while we were trying to split a column, let's go back and correct those error in the original column before we try to split it again.

````
  - Click where it says Undo / Redo on the left side of the screen. All the changes you have made so far are listed here.
  - Click on the previous step that you want to go back to. The added columns will disappear.
````

## Trim Leading and Trailing Whitespace

We'd like to remove extra blank characters from the beginning of any scientificNames that have them. We'll also get rid of blank characters from the ends at the same time.

````
  - In the header for the column _scientificName_, choose Edit cells > Common transforms > Trim leading and trailing whitespace.
  - Notice that the Split step has now disappeared from the Undo / Redo pane on the left. 
  - Perform the same Split operation on scientificName that you undid earlier. This time you should only get two new columns.
````

Previous: [Getting Started with OpenRefine](00-getting-started.html)  Next: [Scripts from OpenRefine](02-scripts.html)
