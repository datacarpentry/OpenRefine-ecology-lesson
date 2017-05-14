---
title: "Filtering and Sorting with OpenRefine"
teaching: 10
exercises: 10
questions:
- "How can we select only a subset of our data to work with?"
- "How can we sort our data?"
objectives:
- "Filter to a subset of rows by text filter or include/exclude."
- "Sort table by a column."
- "Sort by multiple columns."
keypoints:
- "OpenRefine provides a way to sort and filter data without affecting the raw data."
---

# Lesson

## Filtering

There are many entries in our data table. We can filter it to work on a subset of the data in the list for the next set of operations. Please ensure you perform this step to save time during the class.

1. Click the down arrow next to `scientificName` > `Text filter`. A `scientificName` facet will appear on the left margin.
2. Type in `bai` and press return. There are 48 matching rows of the original 35549 rows (and these rows are selected for the subsequent steps).
3. At the top, change the view to `Show` 50 `rows`. This way you will see all the matching rows.

> ## Exercise
>
> 1. What scientific names (genus and species) are selected by this procedure?  
> 2. How would you restrict this to one of the species selected?  
> 
> > ## Solution
> > 1. Do `Facet` > `Text facet` on the `scientificName` column after filtering. This will show that
> > two names match your filter criteria. They are `Baiomys taylori` and `Chaetodipus baileyi`.   
> > 2. To restrict to only one of these two species, you could make the search case sensitive or 
> > you could split the `scientificName` column into species and genus before filtering or
> > you could include more letters in your filter.
> > 
> {: .solution}
{: .challenge}

### Excluding entries


In addition to the solutions included above, another way to narrow our filter is to `include` and/or `exclude` entries in a facet. If you still have your facet for `scientificName`, you can use it, or use drop-down menu > `Facet` > `Text facet` to create a new facet. Only the entries with names that agree with your `Text filter` will be included in this facet.

Faceting and filtering look very similar. A good distinction is that faceting gives you an overview description of all of the data that 
is currently selected, while filtering allows you to select a subset of your data for analysis. 


> ## Exercise
>
> Use `include / exclude` to select only entries from one of these two species.
>
> > ## Solution
> > 
> > 1. In the facet (left margin), click on one of the names, such as `Baiomys taylori`. Notice that when you click on the name, or hover
> > over it, there are entries to the right for `edit` and `include`. 
> > 2. Click `include`. This will explicitly include this species, and exclude others that are not expicitly included. Notice that the
> option now changes to `exclude`.
> > 3. Click `include` and `exclude` on the other species (`Chaetodipus baileyi`) and notice how the two entries appear and disappear
> >  from the table.
> > 
> {: .solution}
{: .challenge}

Important: Select both species for your filtered dataset before continuing with the rest of the exercises.

## Sort

You can sort the data in a column by using the drop-down menu available in that column.
There you can sort by `text`, `numbers`, `dates` or `booleans` (`TRUE` or `FALSE` values). You can also specify what order to put `Blanks` and `Errors` in the sorted results.

If this is your first time sorting this table, then the drop-down menu for the selected column shows `Sort...`. Select what you would like to sort by (such as `numbers`). Additional options will then appear for you to fine-tune your sorting.


> ## Exercise
>
> Sort by month. How can you ensure that months are in order?
{: .challenge}

If you try to re-sort a column that you have already used, the drop-down menu changes slightly, to > `Sort` without the `...`, to remind you that you have already used this column. It will give you additional options:

* > `Sort` > `Sort...` - This option enables you to modify your original sort. 
* > `Sort` > `Reverse` - This option allows you to reverse the order of the sort.
* > `Sort` > `Remove sort` - This option allows you to undo your sort.

> ## Exercise
> 
> Sort the data by `plot`. What year(s) were observations recorded for plot 1 in this filtered dataset. 
> 
> > ## Solution
> > In the `plot` column, select `Sort...` > `numbers` and select `smallest first`. The years represented are 1990 and 1995.
> > 
> {: .solution}
{: .challenge}


### Sorting by multiple columns.

You can sort by multiple columns by performing sort on additional columns. The sort will depend on the order in which you select columns to sort. To restart the sorting process with a particular column, check the `sort by this column alone` box in the `Sort` pop-up menu.

> ## Exercise
>
> You might like to look for trends in your data by month of collection across years.     
> 1. How do you sort your data by month?   
> 2. How would you do this differently if you were instead trying to see all of your entries in chronological order?  
> 
> > ## Solution
> > 
> > 1. For the `mo` column, click on `Sort...` and then `numbers`. This will group all entries made in, for example, January,
> > together, regardless of the year that entry was collected.  
> > 2. For the `yr` column, click on `Sort` > `Sort...` > `numbers` and select `sort by this column alone`. This will undo the 
> > sorting by month step. Once you've sorted by `yr` you can then apply another sorting step to sort by month within year. To do this
> > for the `mo` column, click on `Sort` > `numbers` but do not select `sort by this column alone`. To ensure that all entries are shown 
> > chronologically, you will need to add a third sorting step by day within month. 
> > 
> {: .solution}  
{: .challenge}

If you go back to one of the already sorted colunms and select > `Sort` > `Remove sort`, that column is removed from your multiple sort. If it is the only column sorted, then data reverts to its original order.

> ## Exercise
>
> Sort by `year`, `month` and `day` in some order. Be creative: try sorting as `numbers` or `text`, and in reverse order (`largest to smallest` or `z to a`).
>
> Use > `Sort` > `Remove sort` to remove the sort on the second of three columns. Notice how that changes the order.
{: .challenge}

