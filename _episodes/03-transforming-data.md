---
title: "Transforming Data"
teaching: 30
exercises: 10
questions:
- "How can we transform our data to correct errors?"
objectives:
- "Learn about clustering and how it is applied to group and edit typos."
- "Split values from one column into multiple columns."
- "Manipulate data using previous cleaning steps with undo/redo."
- "Remove leading and trailing white spaces from cells."
- "Learn to use GREL (General Refine Expression Language) for advanced data transformations."
keypoints:
- "Clustering can identify outliers in data and help us fix errors in bulk."
- "GREL (General Refine Expression Language) is a powerful tool for transforming data."
---

So far we have learned to use various facets to inspect and explore our data. Text facet 
also allowed us to directly edit a subset of data in bulk. We have also seen how we can transform the data type 
from text to numeric. OpenRefine offers a number of
other functionalities to transform and restructure the data. 

## Data clustering

Clustering allows you to find groups of entries that are are not identical but are 
sufficiently similar that they may be alternative representations of the same thing (term or data value). 
For example, the two strings `New York` and `new york` are very likely to refer to the same concept and just have a
capitalisation differences. Likewise, `Björk` and `Bjork` probably refer to the same person. These kinds of variations
occur a lot in scientific data. Clustering gives us a tool to resolve them.

OpenRefine provides different clustering algorithms. The best way to understand how they work is to experiment with
them.

1. If you removed it, reinstate the `scientificName` text facet (you can also remove all the other facets to gain some space).
In the `scientificName` text facet box - click the `Cluster` button.
2. In the resulting pop-up window, you can change the `Method` and the `Keying Function`. Try different combinations to
   see what different mergers of values are suggested.
3. If you select the `key collision` method and the `metaphone3` keying function. It should identify three clusters.

   ![OpenRefine Clustering](../fig/openrefine-clustering.png)

4. Tick the `Merge?` checkbox beside each group, then click `Merge Selected and Recluster` to apply the corrections to
   the dataset. Note that the `New Cell Value` column displays the new name that will replace the value in all the cells in the
   group. You can change this (but please don't do so now) if you wish to choose a different value than the suggested one.
5. Try selecting different `Methods` and `Keying Functions` again, to see what new merges are suggested. You may find there are
   still improvements that can be made, but do not `Merge` again; just `Close` when you are done.  We will now
   see other operations that will help us detect and correct the remaining problems, and that have other, more general uses.

**Important:** If you `Merge` using a different method or keying function, or more times than described in the instructions above,
your solutions for later exercises will not be the same as shown in those exercise solutions.

> ## OpenRefine Wiki: Clustering
> Full documentation on clustering can be found at [OpenRefine Wiki: Clustering](https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth)
{: .callout}

## Data splitting

It is easy to split data from one column into multiple columns if the parts are separated by a common separator (say a
comma, or a space).

1. Let us suppose we want to split the `scientificName` column into separate columns, one for genus and one for species.
2. Click the down arrow next to the `scientificName` column. Choose `Edit Column` > `Split into several columns...`
3. In the pop-up, in the `Separator` box, replace the comma with a space (the box will look empty when you're done).
4. Important! Uncheck the box that says `Remove this column`.
5. Click `OK`. You should get some new columns called `scientificName 1`, `scientificName 2`, `scientificName 3`, and `scientificName 4`.
6. Notice that in some cases these newly created columns are empty (you can check by text faceting the
   column). Why? What do you think we can do to fix it?

The entries that have data in `scientificName 3` and `scientificName 4` but not the first two `scientificName` columns
had an extra space at the beginning of the entry. Leading and trailing white spaces are very difficult to notice when cleaning data
manually. This is another advantage of using OpenRefine to clean your data - this process can be automated.
In newer versions of OpenRefine (from version 3.4.1) there is now an option to
clean leading and trailing white spaces from all data when importing the data initially and creating the project.
Because we didn't clean white space at the time of importing the data, we will look at how to
fix leading and trailing white spaces manually in a moment - first we need to undo the splitting step.

## Undoing / Redoing actions

It is common while exploring and cleaning a dataset to make a mistake or decide to change the order of the process
you wish to conduct. OpenRefine provides `Undo` and `Redo` operations to make it easy to roll back your changes.

1. Click `Undo / Redo` in the left side of the screen. All the changes you have made will appear in the left-hand panel.
   The current stage in the data processing is highlighted in blue (i.e. step 4. in the screenshot below). As you click
   on the different stages in the process, the step identified in blue will change and, far more importantly, the data
   will revert to that stage in the processing.

   ![OpenRefine Undo/Redo](../fig/openrefine-undo-redo.png)

2. We want to undo the splitting of the column `scientificName`. Select the stage just
   before the split occurred and the new `scientificName` columns will disappear.
3. Notice that you can still click on the last stage and make the columns reappear, and toggle back and forth between 
these states. You can also select the state more than one steps back and revert to that state.
4. Let's leave the dataset in the state in which the `scientificNames` were clustered, by selecting the stage just before the
   split.

**Important:** If you skip this step, your solutions for later exercises will not be the same as shown in those exercise solutions.

## Trimming Leading and Trailing Whitespace

Words with spaces at the beginning or end are particularly hard for humans to identify from strings without these
spaces (as we have seen with the `scientificName` column). However, blank spaces can make a big difference to computers, so we usually want to remove them.

1. In the header for the column `scientificName`, choose `Edit cells` > `Common transforms` > `Trim leading and trailing whitespace`.
2. Notice that the `Split` step has now disappeared from the `Undo / Redo` pane on the left and is replaced with a `Text transform on 3 cells`
3. Perform the same `Split` operation on `scientificName` that you undid earlier. This time you should now only get two new columns.

Removing the leading white spaces means that each entry in this column has exactly one space 
(between the genus and species parts of the original `scientificName` data).
Therefore, when you now split with space as the separator, you should get only two columns. Let's do this as an exercise.

> ## Exercise
> Repeat the splitting of column `scientificName` exercise.
> > ## Solution
> >
> > On the `scientificName` column, click the down arrow next to the `scientificName` column and 
> > choose `Edit Column` > `Split into several columns...` from the drop down menu. Use a blank character as a separator, 
> > as before. You should now get only two columns `scientificName 1` and `scientificName 2`.
> {: .solution}
{: .challenge}
 
## Renaming columns
 
We now have the genus and species parts neatly separated into 2 columns - `scientificName 1` and `scientificName 2`.
We want to rename these as `genus` and `species`, respectively. 

1. Let's first rename the `scientificName 1` column. On the column, click the down arrow and then `Edit column` > `Rename this column`. 
3. Type "genus" into the box that appears.

> ## Exercise
>
> Try to change the name of the `scientificName 2` column to `species`. What problem do you encounter? How can you fix the problem?
>
> > ## Solution
> >
> > 1. On the `scientificName 2` column, click the down arrow and then `Edit column` > `Rename this column`. 
> > 2. Type "species" into the box that appears. 
> > 3. A pop-up will appear that says `Another column already named species`. This is because there is another column
> > with the same name where we've recorded the species abbreviation. 
> > 4. You can choose another name like `speciesName` for this column or change the other
> > `species` column name to `species_abbreviation` and then come back and rename this column to `species`.
> {: .solution}
{: .challenge}

**Important:** Undo the splitting and renaming steps and retain the white space trimming step 
before moving on (it may be several steps back). If you skip this step, your solutions
for later exercises will not be the same as shown in exercise solutions.
 
## Transforming Data Using GREL

OpenRefine provides a way to write special expressions to accomplish more complex data transformations 
(such as string manipulation or mathematical calculations) to improve the structure of the data.
These functions are written in a special language called [GREL](https://docs.openrefine.org/manual/grel) (General Refine Expression Language). GREL can be used in several places:
1. when transforming cells in a column using the transformation function
2. when adding a column based on another column
3. when creating a custom Text or Numeric facet
4. when creating a new column by fetching data from a URL

We will have a look at the first two of these options; you can explore other yourself - the 
principle of using GREL will be the same and all GREL input windows in OpenRefine will have a 
very similar outlook.

Let's have a look at the column `geolocation` - it contains latitude and longitude coordinates of locations
where observations took place combined together like this: `('30.438056', '-84.247155')`. As can be noted, data contains
round braces "(" and ")" and single quotes "'" around data making it less useful for any processing. 
We want to get rid of all these characters and split the data in two columns to contain individual values 
for latitude and 
longitude.

1. First we want to create a duplicate of the `geolocation` column where we will perform our operations and keep 
the original `geolocation` intact. To do so, on the `geolocation` column click the down arrow and then 
`Edit column` > `Add column based on this column...`.
2. You will be presented with a window to enter a GREL expression telling OpenRefine how to transform the current data
when creating a new column based off it.

   <img src="../fig/grel-duplicate-column.png" alt="Duplicate column functionality" width="600px" />

   GREL `Expression` field contains the expression "value" to begin with. This indicates to use 
   the current "value" of the cell as is when transforming data. In the Preview panel below you can also 
   see the current cell value and what the new value would be after applying the GREL expression to it (in this case - 
   both values will be the same as we are simply duplicating the column). In the `New column name` field type the new
   new name for our duplicate column, e.g. `geolocation_new`. When finished, click `OK` to apply the action.
3. After OpenRefine creates the `geolocation_new` column, we want to do further transformations
   on it to extract longitude and latitude values. To do so, select 
   `Edit cells` > `Transform...` from the drop down menu on the `geolocation_new` column. You will once again be 
   presented with a similar
   window to enter a GREL expression. This time, we want to chain a few functions in the GREL expression 
   to achieve the desired effect of removing round braces and single quotes, 
   like so: `value.replace("(","").replace(")","").replace("'","")`. 
   We are replacing any occurrence of "(" in the cell data value with a blank character (effectively deleting it), and
   then repeating (chaining) similar functions on the output value from the previous function until we remove all 
   unwanted characters. Try typing one function at a time to see what effect it has on the data - you can 
   see the result of applying each expression in the Preview panel.

   <img src="../fig/grel-transform-data.png" alt="Transform data using GREL expression" width="800px" />

   When finished, click `OK` to apply the data transformation.
4. We are now ready to split the `geolocation_new` column using the `Edit Column` > `Split into several columns...`, 
   as we learned earlier in this episode. The separator we want to use in this case is ", " - a comma followed by a blank
   character. If, in addition, you select the `Guess cell type` checkbox in the split column popup window, 
   OpenRefine will correctly identify that the values in new columns are numeric and 
   transform the data type for us as well.

   <img src="../fig/split-column.png" alt="Splitting column using a separator" width="600px" />

5. You should now have 2 new columns with numeric data named `geolocation_new 1` and `geolocation_new 2` 
   representing the extracted longitude and latitude values respectively.
6. Rename your new columns to `longitude` and `latitude` accordingly. You can now make further use of the extracted data from 
other applications, e.g. plot geolocations on a map.
 
GREL offers [rich syntax and a large number of functions](https://docs.openrefine.org/manual/grelfunctions) 
for complex string manipulations (and handling different text formats - JSON, HTML, XML), 
working with numbers, dates and boolean (TRUE/FALSE) values, logical and mathematical operations. We 
strongly recommend learning more on GREL syntax and functionalities.

> ## GREL documentation
> Check the [official GREL documentation](https://docs.openrefine.org/manual/grel) for the full reference on GREL. 
> Here is [another useful GREL guide](https://guides.library.illinois.edu/openrefine/grel) to check out.
{: .callout}