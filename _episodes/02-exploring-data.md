---
title: "Exploring Data with OpenRefine"
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

# Lesson

## Creating a Project

Start OpenRefine, which will open in your browser (at the address `http://127.0.0.0:3333`). Once OpenRefine is launched in your
browser, the left margin has options to `Create Project`, `Open Project`, or `Import Project`. Here we will create a new
project and import our portal rodents data.

![OpenRefine Create Project](../fig/openrefine-create-project.png)

1. Click `Create Project` from the left margin and select then `This Computer` (because you're uploading data from your
   computer).  
1. Click `Choose Files` and browse to where you stored the file `Portal_rodents_19772002_scinameUUIDs.csv`. Select the
   file and click `Open`, or just double-click on the filename.
1. Click `Next>>` under the browse button to upload the data into OpenRefine.  
1. On the next screen, OpenRefine will present you with a preview of your data. You can check here for obvious errors, if, for example, your file was tab-delimited rather than comma-delimited, the preview would look strange (and you
   could correct it by choosing the correct separator and clicking the `Update Preview` button on the right. If you selected the wrong file, click `<<Start Over` at the top left.

    ![OpenRefine Import Data](../fig/openrefine-data-import.png)

1. In the middle of the page, will be a set of options (`Character encoding`, etc.). Make sure the tick box next to
   `Trim leading & trailing whitespace from strings` is not ticked. (We're going to need the leading whitespace in one of our examples.)
1. If all looks well, click `Create Project>>` in the top right. You will be presented with a view onto your data. This is OpenRefine!

> ## OpenRefine does not modify your original dataset
> Once your data is imported into a project - OpenRefine leaves your raw data intact and works on a copy which it creates
> inside the newly created project. All the data transformation and cleaning steps you apply will be performed on this copy
> and you can easily undo any changes too.
{: .callout}
> ## Data file types supported
> OpenRefine can import a variety of different file types, including tab separated (`tsv`),
> comma separated (`csv`), Excel (`xls`, `xlsx`), JSON, XML, RDF as XML, and Google Spreadsheets.
> See the [Create a project by importing data](https://docs.openrefine.org/manual/starting#create-a-project-by-importing-data) page for more information.
{: .testimonial}
Let's now start exploring and getting a higher-level overview of our data - summarising and looking for potential outliers and errors.

## Data Faceting

Facets are one of the most useful features of OpenRefine. Data faceting is a process of exploring data by applying multiple filters to investigate its composition. It also allows you to identify a subset of data that you wish to change in bulk.

> ## OpenRefine Wiki: Faceting
> Full documentation on faceting can be found at [Exploring facets: Faceting](https://docs.openrefine.org/manual/facets)
{: .callout}

A `facet` groups all the like values that appear in a column, and allows you to filter the data by those values. It also allows you to edit values across many records at the same time.

One type of facet is called a 'Text facet'. This groups all the identical text values in a column and lists each value with the number of records it appears in. The facet information always appears in the left hand panel in the OpenRefine interface.

Here we will use faceting to look for potential errors in data entry in the `scientificName` column.

1. Scroll over to the `scientificName` column.
2. Click the down arrow and choose `Facet` > `Text facet`.

    ![OpenRefine Facet menu](../fig/ORFacetMenu.png)

3. In the left panel, you'll now see a box containing every unique value in the `scientificName` column
along with a number representing how many times that value occurs in the column.

    ![Faceting results on scientificName column](../fig/ORFacetedScientificName.png)

4. Try sorting this facet by name and by count. Do you notice any problems with the data? What are they?
5. Hover the mouse over one of the names in the `facet` list. You should see that you have an `edit` function available.
6. You could use this to fix an error immediately, and OpenRefine will ask whether you want to make the same correction to every value it finds like that one. But OpenRefine offers even better ways to find and fix these errors, which we'll use instead. We'll learn about these when we talk about clustering.

There will be several near-identical entries in `scientificName`. For example, there is one entry for `Ammospermophilis harrisi` and
one entry for `Ammospermophilus harrisii`. These are both misspellings of `Ammospermophilus harrisi`. We will see how to correct these
misspelled and mistyped entries in a later exercise.  


> ## More on Facets
>
> [OpenRefine Documentation: Exploring Facets](https://docs.openrefine.org/manual/facets)
>
> As well as 'Text facets' OpenRefine also supports a range of other types of facet. These include:
>
> * Numeric facets
> * Timeline facets (for dates)
> * Custom facets
> * Scatterplot facets
>
> **Numeric and Scatterplot facets** display graphs instead of lists of values. The numeric facet graph includes 'drag and drop' controls you can use to set a start and end range to filter the data displayed. These facets are explored further in [Examining Numbers in OpenRefine](http://www.datacarpentry.org/OpenRefine-ecology-lesson/03-numbers/)
>
> **Custom facets** are a range of different types of facets. Some of the default custom facets are:
>
> * Word facet - this breaks down text into words and counts the number of records each word appears in
> * Duplicates facet - this results in a binary facet of 'true' or 'false'. Rows appear in the 'true' facet if the value in the selected column is an exact match for a value in the same column in another row
> * Text length facet - creates a numeric facet based on the length (number of characters) of the text in each row for the selected column. This can be useful for spotting incorrect or unusual data in a field where specific lengths are expected (e.g. if the values are expected to be years, any row with a text length more than 4 for that column is likely to be incorrect)
> * Facet by blank - a binary facet of 'true' or 'false'. Rows appear in the 'true' facet if they have no data present in that column. This is useful when looking for rows missing key data.
{: .callout}

Facets are intended to group together common values and OpenRefine limits the number of values allowed in a single facet to ensure the software does not perform slowly or run out of memory. If you create a facet where there are many unique values (for example, a facet on a 'book title' column in a data set that has one row per book) the facet created will be very large and may either slow down the application, or OpenRefine will not create the facet.

> ## Exercise
>
> 1. Using faceting, find out how many years are represented in the census.  
>
> 3. Which years have the most and least observations?
>
> 2. Is the column formatted as Number, Date, or Text? How does changing the format change the faceting display?
>
> > ## Solution
> >
> > 1. For the column `yr` do `Facet` > `Text facet`. A box will appear in the left panel showing that there are 26 unique entries in
> > this column.  
> > 3. After creating a facet, click `Sort by count` in the facet box. The year with the most observations is 1997. The least is 1977.
> > 2. By default, the column `yr` is formatted as Text. You can change the format by doing `Edit cells` > `Common transforms` >
> > `To number`. Doing `Facet` > `Numeric facet` creates a box in the left panel that shows a histogram of the number of
> > entries per year. Notice that the data is shown as a number, not a date. If you instead transform the column to a date, the
> > program will assume all entries are on January 1st of the year.   
> >
> {: .solution}
{: .challenge}
