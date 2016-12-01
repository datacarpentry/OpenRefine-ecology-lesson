---
layout: lesson
root: .
title: Working with Open Refine
minutes: .
---

# Learning Objectives

* Create a new OpenRefine project from a `CSV` file
* Recognize how facets can be used to have an overview of the data 
* Use sort and include/exclude to identify and understand possible mistakes in the data
* Apply clustering algorithms to correct multiple typos in a variable at once
* Show how undo/redo allows to recreate previous steps of the data manipulations
* Show how to split the values from one column into multiple columns
* Show how to solve the common mistake of trailing/leading white spaces

----------------------------------------------------

# Lesson

## Creating a Project

Launch OpenRefine (see [Getting Started with OpenRefine](00-getting-started.html).

OpenRefine can import a variety of file types, including tab separated (`*.tsv`), comma separated (`*.csv`), Excel (`*.xls`, `*.xlsx`), JSON, XML, RDF as XML, Google Spreadsheets. See the [OpenRefine Importers page](https://github.com/OpenRefine/OpenRefine/wiki/Importers) for more information.

In this first step, we'll browse our computer to the sample data file for this lesson. In this case, We modified the `Portal_rodents` CSV file, adding several columns: `scientificName`, `locality`, `county`, `state`, `country` and generating several more columns in the lesson itself (`JSON`, `decimalLatitude`, `decimalLongitude`). Data in `locality`, `county`, `country`, `JSON`, `decimalLatitude` and `decimalLongitude` are contrived and are in no way related to the original dataset. 

If you haven't already, download the data from:  
[https://www.dropbox.com/s/kbb4k00eanm19lg/Portal_rodents_19772002_scinameUUIDs.csv](https://www.dropbox.com/s/kbb4k00eanm19lg/Portal_rodents_19772002_scinameUUIDs.csv)

Once OpenRefine is launched in your browser, the left margin as options to **Create Project**, **Open Project**, or **Import Project**. Here we create a project, which just takes a couple steps:

1. click **Create Project** to bring you to "Get data from" "**This Computer**".
2. Click **Browse...** and select file `Portal_rodents_19772002_scinameUUIDs.csv`. Click **Open** in the browse window to finish selection 
3. Click **Next>>** under the browse button to upload data into OpenRefine.
4. Refine gives you a preview - a chance to show you it understood the file. If, for example, your file was really tab-delimited, the preview might look strange, you would choose the correct separator in the box shown and click **Update Preview** (look in bottom panel). If this is the wrong file, click **<<Start Over** (look in upper left region).
5. If all looks well, click **Create Project>>** (look in upper right corner).

Note that at step 1, you could upload data in a standard form from a web address by using "Get data from" "**Web Addresses (URLs)**". However, this will not work on a dropbox address as above.

## Faceting

*Exploring data by applying multiple filters*

OpenRefine supports faceted browsing as a mechanism for

* seeing a big picture of your data, and
* filtering down to just the subset of rows that you want to change in bulk.

Typically, you create a facet on a particular column. The facet summarizes the cells in that column to give you a big picture on that column, and allows you to filter to some subset of rows for which their cells in that column satisfy some constraint. That's a bit abstract, so let's jump into some examples. 

> ## Challenge
>
> Use **Facet** to examine the scientific names. Below are some suggested steps.

1. Scroll over to the **scientificName** column.
2. Click the down arrow and choose **> Facet > Text facet**.
3. In the left margin, you'll see a box containing every unique, distinct value in the **scientificName** column. OpenRefine shows you how many times that value occurs in the column (a count), and allows you to sort (order) your facets by **name** or **count**.
3. Edit an entry. Note that at any time, in any cell of the Facet box, or data cell in the Refine window, you have access to **edit** and can fix an error immediately. OpenRefine will even ask you if you'd like to make that same correction to every value it finds like that one (or not).

[More on faceting](https://github.com/OpenRefine/OpenRefine/wiki/Faceting)

## Cluster

One of the most magical bits of Refine, the moment you realize what you've been missing. Refine has several clustering algorithms built in. Experiment with them, and learn more about these algorithms and how they work. 

In OpenRefine, clustering refers to the operation of "finding groups of different values that might be alternative representations of the same thing". For example, the two strings "New York" and "new york" are very likely to refer to the same concept and just have capitalization differences. Likewise, "Gödel" and "Godel" probably refer to the same person. 

> ## Challenge
>
> Use **Cluster** to check for errors in scientific names. Below are some suggested steps.

1. In this example, in the **scientificName** Text Facet box we created in the step above, click the **Cluster** button.
2. In the resulting pop-up window, you can change the algorithm method, and keying function. Try different combinations to see what happens. For example, with this dataset, the **nearest neighbor** method with the **PPM** keying function shows the power of clustering the best. 
3. Intentional errors in these scientific names have been introduced to show how errors (typos) in any position can be found with this method. All errors can then be fixed by simply entering the correct value in the box on the right. Often, the algorithm has guessed correctly. 
4. After corrections are made in this window, you can either **Merge Selected & Close** or **Merge Selected & Re-Cluster**. Close the pop-up with the **Close** button if it does not otherwise disappear.

[More on clustering](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth)

## Split columns into multiple columns

If data in a column needs to be split into multiple columns, and the strings in the cells are separated by a common separator (say a comma, or a space), you can use that separator to divide up the bits into their own columns.

> ## Challenge
>
> Use **Split** to split scientific names in two. Below are some suggested steps.

1. Go to the drop-down tab at the top of the column that you need to split into multiple columns. For example, go to the **scientificName** column and choose from drop-down **> Edit Column > Split into several columns...**.
2. In the pop-up, for **Separator**, replace the comma "," with a space
3. Remove the check in the box that says **Remove this column**.
4. Click **OK** to split the column into two new columns.
5. You'll get two extra columns called, in this case: **scientificName 1** and **scientificName 2**.
6. Change the name of the first column to "Genus" by using the drop-down arrow: **> Edit Column > Rename this column**, changing the name, and clicking **OK**.

> ## Challenge
>
> Try to change the name of the second new column to "species". How can you correct the problem you encounter?

## Leading or trailing white space

If you did this column split on the original **scientificName** column (before facet and cluster changes), the new columns would reveal an error in a few names that have spaces at the beginning (so-called leading white space). These can be easily removed with another Refine feature in the column drop-down choices. In the drop-down arrow for a column select **> Edit cells > Common transforms > Trim leading and trailing whitespace**.

## Undo changes

To **Undo** the creation of new columns, or any number of earlier changes, look in the left margin and notice there is a tab for **Undo / Redo**. Click the **Undo / Redo** and select back one step to remove the most recent change (all steps, all changes are saved here). Just click the previous step to go back. The extra columns will be gone.

Previous: [Getting Started with OpenRefine](00-getting-started.html)  Next: [Filtering, Excluding and Sorting](02-filter-exclude-sort.html)