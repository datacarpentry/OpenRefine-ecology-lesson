---
title: "Opening and Exploring Data"
teaching: 20
exercises: 15
questions:
- "How can we import our data into OpenRefine?"
- "How can we summarise our data?"
- "How can we find errors in our data?"
- "How can we edit data to fix errors?"
- "How can we convert column data from one data type to another?"
objectives:
- "Create a new OpenRefine project from a CSV file"
- "Learn about different types of facets and how they can be used to summarise data of different data types"
keypoints:
- "Faceting can identify errors or outliers in data"
---

## Creating a project

Start OpenRefine, which will open in your browser (at the address `http://127.0.0.0:3333`). Once OpenRefine is launched in your
browser, the left margin has options to `Create Project`, `Open Project`, or `Import Project`. Here we will create a new
project and import our portal rodents data. 

![OpenRefine Create Project](../fig/openrefine-create-project.png)

1. Click `Create Project` from the left margin and select then `This Computer` (because you're uploading data from your
   computer).  
2. Click `Choose Files` and browse to where you stored the file `Portal_rodents_19772002_scinameUUIDs.csv`. Select the
   file and click `Open`, or just double-click on the filename.
3. Click `Next>>` under the browse button to upload the data into OpenRefine.  
4. On the next screen, OpenRefine will present you with a preview of your data. You can check here for obvious errors,
   if, for example, your file was tab-delimited rather than comma-delimited, the preview would look strange (and you
   could correct it by choosing the correct separator and clicking the `Update Preview` button on the right. If you
   selected the wrong file, click `<<Start Over` at the top left.

    ![OpenRefine Import Data](../fig/openrefine-data-import.png)

4. In the middle of the page, will be a set of options (`Character encoding`, etc.). Make sure the tick box next to
   `Trim leading & trailing whitespace from strings` is not ticked. (We're going to need the leading whitespace in one
   of our examples.) 
5. If all looks well, click `Create Project>>` in the top right. You will be presented with a view onto your data. This
   is OpenRefine!

Let's now start exploring and getting a higher-level overview of our data - summarising and looking for potential 
outliers and errors.

> ## Data file types supported
> OpenRefine can import a variety of different file types, including tab separated (`tsv`), 
> comma separated (`csv`), Excel (`xls`, `xlsx`), JSON, XML, RDF as XML, and Google Spreadsheets. 
> See the [OpenRefine Importers page](https://github.com/OpenRefine/OpenRefine/wiki/Importers) for more information.
{: .callout}

## Data faceting

Facets are one of the most useful features of OpenRefine. Data faceting is a process of exploring data by applying
multiple filters to investigate its composition. It also allows you to identify a subset of data that you wish to change
in bulk.

> ## OpenRefine Wiki: Faceting 
> Full documentation on faceting can be found at [OpenRefine Wiki: Faceting](https://github.com/OpenRefine/OpenRefine/wiki/Faceting)
{: .callout}

OpenRefine supports a range of facets, including:
- Text facet for working with textual data, 
- Numeric and Scatterplot facets for working with numeric data,
- Timeline facet for working with dates, and
- number of customized facets (some of which we will cover shortly).

### Text facet
A 'text facet' groups all the identical text values in a column and lists each value with the number of records in which
it appears. The facet information always appears in the left hand panel in the OpenRefine interface. We will use text
faceting to look for potential errors in the `scientificName` column.

1. Click the down arrow next to the `scientificName` column.
2. Choose `Facet` > `Text facet`.
3. In the left panel, you'll now see a box containing every unique value in the `scientificName` column 
along with a number representing how many times that value occurs in the column.

    ![OpenRefine Text Facet](../fig/openrefine-text-facet.png)

4. You can click in this panel to sort the facet by `name` and `count`. Do you notice any problems with the data? What
   are they?
5. Hover the mouse over any one of the names in the left panel. You should see that you have an `edit` function
   available. 
6. You could use this to fix an error immediately, and OpenRefine will ask whether you want to make the same correction
   to every value equal to the one you identified. But OpenRefine offers even better ways to find and fix errors across
   the whole dataset, which we will use instead. We will learn about these when we talk about clustering.

There will be several near-identical entries in `scientificName`. For example, there is one entry for `Ammospermophilis harrisi` and
one entry for `Ammospermophilus harrisii`. These are both misspellings of `Ammospermophilus harrisi`. We will see how to correct these 
misspelled and mistyped entries in a later exercise.  

> ## Exercise
>
> 1. Using faceting, find out how many years are represented in the census (via the `yr` column).  
>
> 2. Is the column formatted as a number, date or text?
>
> 3. Which year has the most and which year has the least observations?
> 
> > ## Solution
> > 
> > 1. For the column `yr` do `Facet` > `Text facet`. A box will appear in the left panel showing that there are 26 unique entries in
> >    this column.  
> > 2. If you try to apply a Numeric facet on the same column, you may notice that it won't work. This is because, by default, all columns in OpenRefine are
> >    formatted as text.
> > 3. You can change the data format to numbers by selecting the down arrow next to
> >    the `yr` column name, selecting `Edit cells` > `Common transforms` > `To number`. Notice when this change was
> >    applied that the values in the column changed from black to green, and from left-justified to right-justified. 
> >    If you now select `Facet` > `Numeric facet` on column `yr`, a new box is created that shows a histogram of the number of 
> >    entries per year. Notice that the data is shown as a number, not a date.
> > 4. You can also transform the column data type to be date by selecting `Edit cells` > `Common transforms` > `To date`. Note the
> >    program will assume all entries take place on 1st January of the year. You can now choose a Timeline facet. If 
> >    you change the date to date data type, undo that action from the Undo/Redo tab to revert to the numeric data 
> >    type before moving on to the next step. 
> >    We will cover undoing/redoing actions in more detail shortly.
> > 5. Click `Sort by count` in the Text facet box to order the counts numerically. The year with the most observations
>      is 1997, and the year with the least is 1977. 
> > 
> {: .solution}
{: .challenge}

> ## Default data type 
>
> Be default, all data imported in OpenRefine is treated as text. You have to tell OpenRefine explicitly 
> to treat columns differently via `Edit cells` > `Common transforms`, e.g. as numbers. If you change the 
> data type - it will appear in green. 
>
{: .callout}

### Facets for working with numbers

As we have seen in the previous exercise, when data is initially imported into OpenRefine, 
all the columns are treated as text values. We have seen that we can
transform columns to other data types (e.g. number or date) using the `Edit cells` > `Common transforms` feature. Here
we will experiment more with changing columns to numbers to see what additional capabilities this grants us.

Transform cells in the `recordID` column to numbers by clicking the down arrow for the column, then `Edit cells` >
`Common transforms…` > `To number`. You will notice the `recordID` values change from left-justified to right-justified,
and from black to green.

> ## Exercise
>
> Transform more columns, e.g. `recordID` and `yr`, from text to numbers. Can all columns be transformed to numbers?
>
> > ## Solution
> >
> > To convert to number, a column must include only numerals (0-9). If you apply a number transformation to
> > a column that does not meet this criterion (e.g. `scientificName` column), 
> > you might get an error and no data will be transformed (you can check this under the `Undo / Redo`
> > tab: you will see the stage will be described `Text transform on 0 cells`.)
> >
> {: .solution}
{: .challenge}

Facets for working with numbers, including numeric and scatterplot facets, display graphs instead of lists of values. 
These graphs include 'drag and drop' controls you can use to set a start and end range to filter the data displayed. 

#### Numeric facet
Sometimes there are non-numeric values or blanks in a column which could represent errors in data entry. We can use
OpenRefine to find them with a `Numeric facet`. Remove the facets we created previously before you proceed to gain 
more space.

1. For a column you have transformed to numbers, e.g. `recordID`, edit one or two cells and replace the numbers with text (such as `abc`)
   or with a blank (i.e. no space, number or text). To do so, hover over the cell you want to modify and an `edit` button
   will appear. Click on it and you will be able to modify the cell's value. If you receive an error `Not a valid
   number`, try again and this time change the `Data Type` in the edit box to `Text`.

   ![OpenRefine Clustering](../fig/openrefine-numeric-data.png)

2. Now use the drop down menu next to the column name, select `Facet > Numeric facet` to apply a numeric facet to the 
column you edited. The graph representing the numeric facet will appear in the left panel.

   ![OpenRefine Clustering](../fig/openrefine-numeric-facet.png)

3. Notice that there are several checkboxes in this facet: `Numeric`, `Non-numeric`, `Blank`, and `Error`. Below these
   are counts showing the number of matching cells in each category. You should see checks for `Non-numeric` and `Blank`
   if you changed some values.

   ![OpenRefine Clustering](../fig/openrefine-numeric-facet-options.png)

4. Experiment with checking or unchecking these boxes, and notice how this affects your data table.

When you have finished examining the numeric data, remove this facet by clicking the `x` in the upper left corner of its
panel. Note that this does not undo the edits you made to the cells in this column. If you want to reverse these edits,
use the `Undo / Redo` function.

#### Scatterplot facet

Now that we have multiple columns representing numbers, we can see how they relate to one another using the scatterplot
facet.

Select a numeric column, for example `recordID`, and use the pulldown menu to > `Facet` > `Scatterplot facet`. A new
window called `Scatterplot Matrix` will appear. It contains grids for each pair of numeric columns that have been
plotted against each other (the number will vary
dependent on how many columns you have transformed to numbers).

![OpenRefine Scatterplot Facet](../fig/openrefine-scatterplot-facet.png)

1. Examine the scatterplots overall. Do the patterns make sense?
2. Why does the scatterplot for `recordID` vs `period` have the pattern it does?

We can examine one pair of columns by clicking on its square in the `Scatterplot Matrix` A new facet with only that pair
of columns will appear in the left margin as an interactive graph. Click in the scatterplot facet in the left margin and
drag to highlight a rectangle. This is a very powerful way of subsetting data of interest.

![OpenRefine Scatterplot Facet](../fig/openrefine-scatterplot-highlighted.png)

The scatterplot `recordID` vs `period` has a slightly unexpected shape - you would probably expect a
linear graph. Instead, there are some negative values on the `period` axis. These are potentially errors in the data.
You can click anywhere on the graph to get rid of the subsetting.

### Other types of facets
In addition to Text, Numeric, Scatterplot and Timeline facets, OpenRefine also supports a 
range of customized facets:

* Word facet - this breaks down text into words and counts the number of records in which each word appears
* Duplicates facet - this results in a binary facet of 'true' or 'false'. Rows appear in the 'true' facet if the value in the selected column is an exact match for a value in the same column in another row
* Text length facet - creates a numeric facet based on the length (number of characters) of the text in each row for the selected column. This can be useful for spotting incorrect or unusual data in a field where specific lengths are expected (e.g. if the values are expected to be years, any row with a text length more than 4 for that column is likely to be incorrect)
* Facet by blank - a binary facet of 'true' or 'false'. Rows appear in the 'true' facet if they have no data present in that column. This is useful when looking for rows missing key data.

Facets are used to group together common values. OpenRefine limits the number of values allowed in a single facet to
ensure the software does not perform slowly or run out of memory. If you create a facet where there are many unique
values (for example, a facet on a 'book title' column in a data set that has one row per book) the facet created will be
very large and may either slow down the application, or OpenRefine will refuse to create the facet.
