---
title: Reconciliation of Values
teaching: 20
exercises: 10
---

::::::::::::::::::::::::::::::::::::::: objectives

- Add external reconciliation services.
- Cleanup scientific names by matching them to a taxonomy.
- Identify and correct misspelled or incorrect names for a taxon.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can we reconcile scientific names against a taxonomy?

::::::::::::::::::::::::::::::::::::::::::::::::::

## Reconciliation of names

Reconciliation services allow you to lookup terms from your data in OpenRefine against external services, and use values from the external services in your data. The OpenRefine manual provides [more information about the reconciliation feature](https://docs.openrefine.org/manual/reconciling).

Reconciliation services can be more sophisticated and often quicker than using the method described above to retrieve data from a URL. However, to use the `Reconciliation` function in OpenRefine requires the external resource to support the necessary service for OpenRefine to work with, which means unless the service you wish to use supports such a service you cannot use the `Reconciliation` approach.

There are a few services where you can find an OpenRefine Reconciliation option available. For example Wikidata has a reconciliation service at [https://wikidata.reconci.link/](https://wikidata.reconci.link/).

## Reconcile scientific names with the Encyclopedia of Life (EOL)

We can use the [Encyclopedia of Life](https://eol.org/) Reconciliation service to find the taxonomic matches to the names in the dataset.

1. In the `scientificName` column use the dropdown menu to choose 'Reconcile->Start Reconciling'

2. If this is the first time you've used this particular reconciliation service, you'll need to add the details of the service now
  
  - Click 'Add Standard Service...' and in the dialogue that appears enter:
    - `https://eol.org/api/reconciliation`
      ![](fig/or362-reconcile-add.png){alt='Prompt to add a service URL for reconciliation'}

3. You should now see a heading in the list on the left hand side of the Reconciliation dialogue called "Encyclopedia of Life"

4. Click on this to choose to use this reconciliation service

5. In the middle box in the reconciliation dialogue you may get asked what type of 'entity' you want to reconcile to - that is, what type of thing are you looking for. The list will vary depending on what reconciliation service you are using.
  
  - In this case, the only option is "Taxon"

6. In the box on the righthand side of the reconciliation dialogue you can choose if other columns are used to help the reconciliation service make a match - however it is sometimes hard to tell what use (if any) the reconciliation service makes of these additional columns

7. At the bottom of the reconciliation dialogue there is the option to "Auto-match candidates with high confidence". This can be a time saver, but in this case you are going to uncheck it, so you can see the results before a match is made

8. Now click 'Start Reconciling'
  
  ![](fig/or362-reconcile.png){alt='Reconciliation menu'}

Reconciliation is an operation that can take a little time if you have many values to look up.

Once the reconciliation has completed two Facets should be created automatically:

- scientificName: Judgement
- scientificName: best candidate's score

These are two of several specific reconciliation facets and actions that you can get from the 'Reconcile' menu (from the column drop down menu).

Close the 'scientificName: best candidate's score' facet, but leave the 'scientificName: Judgement' facet open.

If you look at the scientificName column, you should see some cells have found one or more matches - the potential matches are shown in a list in each cell. Next to each potential match there is a 'tick' and a 'double tick'. To accept a reconciliation match you can use the 'tick' options in cells. The 'tick' accepts the match for the single cell, the 'double tick' accepts the match for all identical cells.

1. Create a text facet on the scientificName column
2. Choose *Ammospermophilus harrisii*

- In the scientificName column you should be able to see the various potential matches. Clicking on a match will take you to the EOL page for that entity
  ![](fig/or372-reconcile-results.png){alt='Reconciliation menu for each cell'}

1. Click a 'double tick' in one of the scientificName column cells for the option "*Ammospermophilus harrisii* (Audubon \& Bachman 1854)"
2. This will accept this as a match for all cells with this value - you should see the other options disappear

There are two things that reconciliation can do for you. Firstly it gets a standard form of the name or label for the entity. Secondly it gets an ID for the entity - in this case a page and numeric id for the scientific name in EOL. This is hidden in the default view, but can be extracted:

1. In the scientificName column use the dropdown menu to choose `Reconcile` > `Add entity identifiers column...`
2. Give the column the name "EOL-ID"
3. This will create a new column that contains the EOL ID for the matched entity

![](fig/or362-reconcile-id.png){alt='Column with the identifiers from reconciliation'}

## Reconcile country, state, and counties against Wikidata

The country field contains several alternative ways to indicate the United States of America, including:

- `US`
- `UNITED STATES`
- `United States of America`

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

If Wikidata does not appear in the list of reconciliation services, add the standard service using the URL: `https://wikidata.reconci.link/en/api`

- Reconcile the columns `county`, `state`, and `country` using Wikidata.
  - If a type does not show in the list, search using the `Reconcile against type` box:
    - `country`: `country (Q6256)`
    - `state`: `U.S. state (Q35657)`
    - `county`: `county of the United States (Q47168)`
- Mouseover the options listed to see a preview of the entity suggested
  - For the cells with multiple options, choose one of the suggested values and click the double checkmark button to apply to all cells with the same value
- Click the menu of the `country` column and select `Edit column` > `Add column based on this column...`
- Enter "reconciled\_country" in the field for `New column name`
- In the `Expression` box, enter the following GREL: `cell.recon.best.name`
- Click `OK`

This will create a new column with the reconciled names for the countries. Create a text facet to see that there are a single name for each country.

1. In the cases where OpenRefine did not select a match automatically, are the options relevant?
2. Why do some cells in the `county` column have many options?

:::::::::::::::  solution

## Solution

1. The options may be for the same place, but with different wording, like `Hernando County` for `Hernando`.
2. Several county names exist in multiple states. You can mouseover each option and find the correct one that matches the state.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: keypoints

- OpenRefine can look up existing reconciliation services to enrich data

::::::::::::::::::::::::::::::::::::::::::::::::::


