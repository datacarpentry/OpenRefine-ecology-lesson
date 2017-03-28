---
title: "Examining Numbers in OpenRefine"
teaching: 10
exercises: 0
questions:
- "Examing numerical data"
objectives:
- "Transform a text column in to a number column."
- "Identify and modify non-numeric values in a column using facets."
- "Use scatterplot facet to examine relationships among columns."
keypoints:
- "OpenRefine also provides ways to get overviews of numerical data."
---

# Lesson

## Numbers

When a table is imported into Open Refine, all columns are treated as having text values. We saw earlier how we can sort interpreting column values as numbers, but this did not change the cells in a column from text to numbers.

Be sure to remove an **Text filter** facets from the left margin so that we can examine the whole rodent dataset.

To transform cells in the `recordID` column to numbers, use the column pulldown to **> Edit cells > Common transforms… > To number**. You will notice the `recordID` values change from left-justified to right-justified, and black to green color.

> ## Challenge
>
> - Transform three more columns, including **period**, from text to numbers.
{: .challenge}

### Numeric facet
Sometimes there are non-number values or blanks in a column and we want to find them. We can do that with a **Numeric facet**.

> ## Challenge
>
> - For a column you transformed to numbers, edit one or two cells, replacing the numbers with text (such as `abc`) or blank (no number or text).
> - Use the pulldown to **> Facet > Numeric facet**, which will add a facet to the left margin.
> - Notice that there are several checkboxes in this facet: **Numeric**, **Non-numeric**, **Blank**, **Error**. Below these are counts of the number of cells. You should see checks for **Non-numeric** and **Blank** if you changed some values.
> - Experiment with checking or unchecking these boxes to select subsets of your data.
{: .challenge}

When done examining the numeric data, remove this facet by clicking the **x** in the upper left corner of its panel.

## Scatterplot facet

Now that we have multiple columns as numbers, we can see how they relate to one another using the scatterplot facet. Select a numeric column, say `recordID`, and use the pulldown menu to **> Facet > Scatterplot facet**. A new window called **Scatterplot Matrix** will appear. There are squares for each pair of numeric columns organized in an upper right triangle. Each square has little dots for the cell values from each row.

> ## Challenge
>
> - Examine the scatterplots overall. Do the patterns make sense?
> - If you have **recordID** and **period**, why does it have the pattern it does?
{: .challenge}

## Examine pair of columns in detail

We can examine one pair of columns by clicking on its square in the **Scatterplot Matrix**. A new facet with only that pair will appear in the left margin. 

> ## Challenge
>
> - Click in the scatterplot facet in the margin and drag to highlight a rectangle. This will subset the data to those entries.
{: .challenge}

> ## Challenge
> 
> - Click on the **Scatterplot Matrix** square for **recordID** and **period** to get that as a facet in the left margin.
> - Redo the **> Text filter** on **scientificName** to reduce to **bai**.
> - Notice the change in the scatterplot. It might be easier to see if you click **export plot** to put it on a new browser tab.
{: .challenge}

Previous: [Filtering, Excluding and Sorting](02-filter-exclude-sort/)  Next: [Scripts from OpenRefine](04-scripts/)
