---
title: Filtering and Sorting with OpenRefine
teaching: 15
exercises: 20
---

::::::::::::::::::::::::::::::::::::::: objectives

- Employ *text filter* or *include/exclude* to filter to a subset of rows.
- Sort tables by a column.
- Sort tables by multiple columns.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can we select only a subset of our data to work with?
- How can we sort our data?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Filtering

Sometimes you want to view and work only with a subset of data or apply an operation only to a subset.
You can do this by applying various filters to your data.

### Including/excluding data entries on facets

One way to filter down our data is to use the `include` or `exclude` buttons on the entries in a text facet.
If you still have your text facet for `scientificName`, you can use it. If you've closed that facet, recreate it by selecting `Facet` > `Text facet` on the `scientificName` column.

1. In the text facet, hover over one of the names, e.g. *Baiomys taylori*. Notice that when you hover over it, there are buttons to the right for `edit` and `include`.
2. Whilst hovering over *Baiomys taylori*, move to the right and click the `include` option. This will include this species, as signified by the name of the species changing from blue to orange, and new options of `edit` and
  `exclude` will be presented. Note that in the top of the page, "33 matching rows" is now displayed instead of "790 rows".
3. You can include other species in your current filter - e.g. click on *Chaetodipus baileyi* in the same way to include it in the filter.
4. Alternatively, you can click the name of the species to include it in the filter instead of clicking the
  `include`/`exclude` buttons. This will include the selected species and exclude all other options in a single step, which can be useful.
5. Click `include` and `exclude` on the other species and notice how the entries appear and
  disappear from the data table to the right.

Click on `Reset` at the top-right of the facet before continuing to the next step.

### Text filters

One way to filter data is to create a text filter on a column. Close all facets you may have created previously.

1. Click the down arrow next to `scientificName` > `Text filter`. A `scientificName` filter will appear on the left margin below the text facet.

2. Type in `bai` into the text box in the filter and press return. At the top of the page it will report that, out of the 790 rows in the raw data, there are 35 rows in which the text has been found within the `scientificName` column (and these rows will be selected for the
  subsequent steps).
  
  ![](fig/or362-filter-scientificname.png){alt='OpenRefine filtering example'}

3. Near the top of the screen, change `Show:` to 50. This way, you will see all the matching rows in a single page.

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

1. What scientific names are selected by this text filter?
2. How would you restrict the filter to one of the species selected?

:::::::::::::::  solution

## Solution

1. Do `Facet` > `Text facet` on the `scientificName` column after filtering. This will show that
  two names match your filter criteria. They are *Baiomys taylori* and *Chaetodipus baileyi*.
2. To restrict to only one of these two species, you could:

- Check the `case sensitive` box within the `scientificName` facet. Once you do this, you will see that using the upper-case `Bai` will only > > return *Baiomys taylori*, while using lower-case `bai` will only return *Chaetodipus baileyi*.
- You could include more letters in your filter (i.e. typing `baio` will exclusively return *Baiomys taylori*, while `bail` will only return *Chaetodipus baileyi*).

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

## Filters vs. facets

Faceting and filtering look very similar. A good distinction is that faceting gives you an overview of all the data that
is currently selected, while filtering allows you to select a subset of your data for further inspection and analysis.

::::::::::::::::::::::::::::::::::::::::::::::::::

**Important:** Make sure both species (*Baiomys taylori* and *Chaetodipus baileyi*) are included in your filtered dataset before continuing with the rest of the exercises.

## Sort

Sorting data is a useful practice for detecting outliers in data - potential errors and blanks
will sort to the top or the bottom of your data.

You can sort the data in a column by using the drop-down menu available in that column.
There you can sort by `text`, `numbers`, `dates` or `booleans` (`TRUE` or `FALSE` values). You can also specify what order to put `Blanks` and `Errors` in the sorted results.

If this is your first time sorting this table, then the drop-down menu for the selected column shows `Sort...`. Select what you would like to sort by (such as `numbers`). Additional options will then appear for you to fine-tune your sorting.

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

Sort by month. How can you ensure that months are in order?

:::::::::::::::  solution

## Solution

In the `mo` column, select `Sort...` > `numbers` and select `smallest first`. The months are listed from 1 (for January) through 12 (December).



:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

If you try to re-sort a column that you have already used, the drop-down menu changes slightly, to > `Sort` without the `...`, to remind you that you have already used this column. It will give you additional options:

- > `Sort` > `Sort...` - This option enables you to modify your original sort.
- > `Sort` > `Reverse` - This option allows you to reverse the order of the sort.
- > `Sort` > `Remove sort` - This option allows you to undo your sort.

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

Sort the data by `plot`. What year(s) were observations recorded for plot 1 in this filtered dataset?

:::::::::::::::  solution

## Solution

In the `plot` column, select `Sort...` > `numbers` and select `smallest first`. The years represented include 1990 and 1995.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

### Sorting by multiple columns

You can sort by multiple columns by performing sort on additional columns. The sort will depend on the order in which you select columns to sort. To restart the sorting process with a particular column, check the `sort by this column alone` box in the `Sort` pop-up menu.

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

You might like to look for trends in your data by month of collection across years.

1. How do you sort your data by month?
2. How would you do this differently if you were instead trying to see all of your entries in chronological order?

:::::::::::::::  solution

## Solution

1. For the `mo` column, click on `Sort...` and then `numbers`. This will group all entries made in, for example, January,
  together, regardless of the year that entry was collected.
2. For the `yr` column, click on `Sort` > `Sort...` > `numbers` and select `sort by this column alone`. This will undo the
  sorting by month step. Once you've sorted by `yr` you can then apply another sorting step to sort by month within year. To do this
  for the `mo` column, click on `Sort` > `numbers` but do not select `sort by this column alone`. To ensure that all entries are shown
  chronologically, you will need to also sort by days within each month.  Click on the `dy` column then `Sort` > `numbers`.  Your data should now be in chronological order.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

If you go back to one of the already sorted columns and select > `Sort` > `Remove sort`, that column is removed from your multiple sort. If it is the only column sorted, then data reverts to its original order.

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

Sort by `year`, `month` and `day` in some order. Be creative: try sorting as `numbers` or `text`, and in reverse order (`largest to smallest` or `z to a`).

Use `Sort` > `Remove sort` to remove the sort on the second of three columns. Notice how that changes the order.


::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- OpenRefine provides various ways to sort and filter data without affecting the raw data.

::::::::::::::::::::::::::::::::::::::::::::::::::


