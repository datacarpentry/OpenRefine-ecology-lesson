---
title: "Working with OpenRefine"
teaching: 15
exercises: 20
questions:
- "How can we bring our data into OpenRefine?"
- "How can we sort and summarize our data?"
- "How can we find and correct errors in our raw data?"
objectives:
- "Create a new OpenRefine project from a CSV file."
- "Recall what facets are and how they are used to sort and summarize data."
- "Recall what clustering is and how it is applied to group and edit typos."
- "Manipulate data using previous steps with undo/redo."
- "Employ drop-downs to split values from one column into multiple columns."
- "Employ drop-downs to remove white spaces from cells."
keypoints:
- "Faceting and clustering approaches can identify errors or outliers in data."
---

# Lesson

## Creating a Project


Start the program. (Double-click on the openrefine.exe file (or google-refine.exe if using an older version). Java services will start on your machine, and OpenRefine will open in your browser).

Launch OpenRefine (see [Getting Started with OpenRefine](http://www.datacarpentry.org/OpenRefine-ecology-lesson/00-getting-started/)).

OpenRefine can import a variety of file types, including tab separated (`tsv`), comma separated (`csv`), Excel (`xls`, `xlsx`), JSON, XML, RDF as XML, Google Spreadsheets. See the [OpenRefine Importers page](https://github.com/OpenRefine/OpenRefine/wiki/Importers) for more information.

In this first step, we'll browse our computer to the sample data file for this lesson. In this case, we modified the `Portal_rodents` CSV file, adding several columns: `scientificName`, `locality`, `county`, `state`, `country` and generating several more columns in the lesson itself (`JSON`, `decimalLatitude`, `decimalLongitude`). Data in `locality`, `county`, `country`, `JSON`, `decimalLatitude` and `decimalLongitude` are contrived and are in no way related to the original dataset. 

If you haven't already, download the data from:  
[https://ndownloader.figshare.com/files/7823341](https://ndownloader.figshare.com/files/7823341)

Once OpenRefine is launched in your browser, the left margin has options to `Create Project`, `Open Project`, or `Import Project`. Here we will create a new project:

1. click `Create Project` and select `Get data from` `This Computer`.  
2. Click `Choose Files` and select the file `Portal_rodents_19772002_scinameUUIDs.csv`. Click `Open` or double-click on the filename.
3. Click `Next>>` under the browse button to upload the data into OpenRefine.  
4. OpenRefine gives you a preview - a chance to show you it understood the file. If, for example, your file was really tab-delimited, the preview might look strange, you would choose the correct separator in the box shown and click `Update Preview` (bottom left). If this is the wrong file, click `<<Start Over` (upper left).  
5. If all looks well, click `Create Project>>` (upper right). 

Note that at step 1, you could upload data in a standard form from a web address by selecting `Get data from` `Web Addresses (URLs)`. However, this won't work for all URLs.

## Faceting

*Exploring data by applying multiple filters*

OpenRefine supports faceted browsing as a mechanism for

* seeing a big picture of your data, and
* filtering down to just the subset of rows that you want to change in bulk.

Typically, you create a facet on a particular column. The facet summarizes the cells in that column to give you a big picture of that column, and allows you to filter to some subset of rows for which the cells in that column satisfy some constraint. That's a bit abstract, so let's jump into some examples. 

[More on faceting](https://github.com/OpenRefine/OpenRefine/wiki/Faceting)

Here we will use faceting to look for potential errors in data entry in the `scientificName` column.

1. Scroll over to the `scientificName` column.
2. Click the down arrow and choose `Facet` > `Text facet`.
3. In the left panel, you'll now see a box containing every unique value in the `scientificName` column 
along with a number representing how many times that value occurs in the column.
4. Try sorting this facet by name and by count. Do you notice any problems with the data? What are they?
5. Hover the mouse over one of the names in the `Facet` list. You should see that you have an `edit` function available. 
6. You could use this to fix an error immediately, and OpenRefine will ask whether you want to make the same correction to every value it finds like that one. But OpenRefine offers even better ways to find and fix these errors, which we'll use instead. We'll learn about these when we talk about clustering.

> ## Solution
> 
> There will be several near-identical entries in `scientificName`. For example, there is one entry for `Ammospermophilis harrisi` and
> one entry for `Ammospermophilus harrisii`. These are both misspellings of `Ammospermophilus harrisi`. We will see how to correct these 
> misspelled and mistyped entries in a later exercise.  
{: .solution}

> ## Exercise
>
> 1. Using faceting, find out how many years are represented in the census.  
>
> 2. Is the column formatted as Number, Date, or Text? How does changing the format change the faceting display?
>
> 3. Which years have the most and least observations?
> 
> > ## Solution
> > 
> > 1. For the column `yr` do `Facet` > `Text facet`. A box will appear in the left panel showing that there are 26 unique entries in
> > this column.  
> > 2. By default, the column `yr` is formatted as Text. You can change the format by doing `Edit cells` > `Common transforms` > 
> > `To number`. Doing `Facet` > `Numeric facet` creates a box in the left panel that shows a histogram of the number of 
> > entries per year. Notice that the data is shown as a number, not a date. If you instead transform the column to a date, the 
> > program will assume all entries are on January 1st of the year.   
> > 3. After creating a facet, click `Sort by count` in the facet box. The year with the most observations is 1997. The least is 1977. 
> > 
> {: .solution}
{: .challenge}

## Clustering

In OpenRefine, clustering means "finding groups of different values that might be alternative representations of the same thing". For example, the two strings `New York` and `new york` are very likely to refer to the same concept and just have capitalization differences. Likewise, `Gödel` and `Godel` probably refer to the same person. Clustering is a very powerful tool for cleaning datasets which contain misspelled or mistyped entries. OpenRefine has several clustering algorithms built in. Experiment with them, and learn more about these algorithms and how they work. 

1. In the `scientificName` Text Facet we created in the step above, click the `Cluster` button.
2. In the resulting pop-up window, you can change the `Method` and the `Keying Function`. Try different combinations to 
 see what different mergers of values are suggested.
3. Select the `key collision` method and `metaphone3` keying function. It should identify three clusters. 
4. Click the `Merge?` box beside each, then click `Merge Selected and Recluster` to apply the corrections to the dataset.
4. Try selecting different `Methods` and `Keying Functions` again, to see what new merges are suggested. You may find there are 
 still improvements that can be made, but don't `Merge` again; just `Close` when you're done.  We'll now 
 see other operations that will help us detect and correct the remaining problems, and that have other, more general uses.

Important: If you `Merge` using a different method or keying function, or more times than described in the instructions above, 
your solutions for later exercises will not be the same as shown in those exercise solutions.

[More on clustering](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth)

## Split


If data in a column needs to be split into multiple columns, and the parts are separated by a common separator (say a comma, or a space), you can use that separator to divide up the pieces into their own columns.


1. Let us suppose we want to split the `scientificName` column into separate colums for genus and for species. 
2. Click the down arrow at the top of the `scientificName` column. Choose `Edit Column` > `Split into several columns...`
3. In the pop-up, in the `Separator` box, replace the comma with a space.
4. Uncheck the box that says `Remove this column`.
5. Click `OK`. You'll get some new columns called `scientificName 1`, `scientificName 2`, and so on.
6. Notice that in some cases `scientificName 1` and `scientificName 2` are empty. Why is this? What do you think we 
can do to fix this?

> ## Solution
> 
> The entries that have data in `scientificName 3` and `scientificName 4` but not the first two `scientificName` columns 
> had an extra space at the beginning of the entry. Leading white spaces are very difficult to notice when cleaning data
> manually. This is another advantage of using OpenRefine to clean your data. We'll look at how to 
> fix leading and trailing white spaces in a later exercise.
{: .solution}

> ## Exercise
>
> Try to change the name of the second new column to "species". How can you correct the problem you encounter?
> 
> > ## Solution
> > 
> > On the `scientificName 2` column, click the down arrow and then `Edit column` > `Rename this column`. Type "species" into the box
> > that appears. A pop-up will appear that says `Another column already named species`. This is because there is another column
> > where we've recorded the species abbreviation. You can choose another name like `speciesName` for this column or change the other 
> > `species` column you can change the name to `speciesAbbreviation`.
> {: .solution}
{: .challenge}

## Undo / Redo

It's common while exploring and cleaning a dataset to discover after you've made a change that you really should have done something else first. OpenRefine provides `Undo` and `Redo` operations to make this easy.


1. Click where it says `Undo / Redo` on the left side of the screen. All the changes you have made so far are listed here.
2. Click on the step that you want to go back to, in this case the previous step. The added columns will disappear.
3. Notice that you can still click on the last step and make the columns reappear, and toggle back and forth between these states.
4. Leave the dataset in the state in which the `scientificNames` were clustered, but not yet split.

Important: If you skip this step, your solutions for later exercises will not be the same as shown in those exercise solutions.

## Trim Leading and Trailing Whitespace

Words with spaces at the beginning or end are particularly hard for we humans to tell from strings without, but the blank characters will make a difference to the computer. We usually want to remove these. OpenRefine provides a tool to remove blank characters from the beginning and end of any entries that have them.


1. In the header for the column `scientificName`, choose `Edit cells` > `Common transforms` > `Trim leading and trailing whitespace`.
2. Notice that the `Split` step has now disappeared from the `Undo / Redo` pane on the left and is replaced with a `Text transform on 3 cells`
3. Perform the same `Split` operation on `scientificName` that you undid earlier. This time you should only get two new columns. Why?

> ## Solution
> 
> Removing the leading white spaces means that each entry in this column has exactly one space (between the genus and species names). 
> Therefore, when you split with space as the separator, you will get only two columns.
{: .solution}

Important: `Undo` the splitting step before moving on to the next lesson. If you skip this step, your solutions 
for later exercises will not be the same as shown in those exercise solutions.

