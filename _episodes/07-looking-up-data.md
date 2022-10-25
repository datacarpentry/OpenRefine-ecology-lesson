---
title: "Looking Up Data"
teaching: 20
exercises: 10
questions:
- "How do I fetch data from an Application Programming Interface (API) to be used in OpenRefine?"
- "How do I reconcile my data by comparing it to authoritative datasets"
objectives:
- "Use URLs to fetch data from the web based on columns in an OpenRefine project"
- "Add columns to parse JSON data returned by web services"
keypoints:
- "OpenRefine can look up custom URLs to fetch data based on what's in an OpenRefine project"
- "Such API calls can be custom built"
---

## Looking up data from a URL

> http://api.gbif.org/v1/species/match?verbose=true&name="+escape(value,'url')
> value.parseJson().get("family")

OpenRefine can retrieve data from URLs. This can be used in various ways, including looking up additional information from a remote service, based on information in your OpenRefine data.

As an example, you can look up names against the Virtual International Authority File (VIAF), and retrieve additional information such as dates of birth/death and identifiers.

Typically this is a two step process, firstly a step to retrieve data from a remote service, and secondly to extract the relevant information from the data you have retrieved.

To retrieve data from an external source, use the drop down menu at any column heading and select ‘Edit column->Add column by fetching URLs’.

This will prompt you for a GREL expression to create a URL. Usually this would be a URL that uses existing values in your data to build a query. When the query runs OpenRefine will request each URL (for each line) and retrieve whatever data is returned (this may often be structured data, but could be HTML).

The data retrieved will be stored in a cell in the new column that has been added to the project. You can then use OpenRefine transformations to extract relevant information from the data that has been retrieved. Two specific OpenRefine functions used for this are:

* parseHtml()
* parseJson()

The 'parseHtml()' function can also be used to extract data from XML.

The next exercise demonstrates this two stage process in full.

## Retrieving journal details from GBIF
Because retrieving data from external URLs takes time, this exercise targets a single line in the data. In reality you would want to run this over many rows (and probably go and do something else while it ran).

In this case we are going to use the GBIF API: [https://github.com/CrossRef/rest-api-doc)](https://github.com/CrossRef/rest-api-doc). Read more about the CrossRef service: [http://www.crossref.org](http://www.crossref.org). Note that API providers may impose rate limits or have other requirements for using their data, so it's important to check the site's documentation. To comply with API rate limits, use the Throttle Delay setting to specify the number of milliseconds between URL requests. CrossRef, for instance, [asks users](https://github.com/CrossRef/rest-api-doc#etiquette) to "specify a User-Agent header that properly identifies your script or tool and that provides a means of contacting you via email using 'mailto:'." User-agent headers provide administrators with user information that facilitates better administration and moderation of the API, and it is generally good etiquette to include a header with any API request.

To edit your User-Agent header:
* Click 'Show' (next to 'HTTP headers to be used when fetching URLs'). Note that OpenRefine has already populated the 'User-Agent' field with information about the version of OpenRefine you are using; it should look similar to ``` OpenRefine 3... [...]``` (the information following ```OpenRefine``` will depend on the version of OpenRefine you are using).
* At the end of the existing text, add ```; mailto:address@library.edu```, using your own email address. The full User-Agent field should now be similar to ``` OpenRefine 3... [...]; mailto:address@library.edu``` but reflect your version information and email address.

The syntax for requesting journal information from CrossRef is ```https://api.crossref.org/journals/{ISSN}``` where {ISSN} is replaced with the ISSN of the journal

* In the expression box type the GREL ```"http://api.gbif.org/v1/species/match?verbose=true&name="+escape(value,'url')```

At this point, your screen should be similar to this:
![Add column by fetching URLs screen capture](../assets/img/openrefine_add_columns_by_url.png)

* Click 'OK'


You should see a message at the top on the OpenRefine screen indicating it is fetching some data, with progress showing the percentage of the proportion of rows of data successfully being fetched. Wait for this to complete. Fetching data for a single row should take only ten seconds or so, but fetching data for all rows will take longer. You can speed this up by modifying the "Throttle Delay" setting in the 'Add column by fetching URLs' dialog which controls the delay between each URL request made by OpenRefine. This is defaulted to a rather large 5000 milliseconds (5 seconds).

At this point you should have a new cell containing a long text string in a format called 'JSON' (this stands for JavaScript Object Notation, although very rarely spelt out in full).

OpenRefine has a function for extracting data from JSON (sometimes referred to as 'parsing' the JSON). The 'parseJson' function is explained in more detail at [https://docs.openrefine.org/manual/grelfunctions/#format-based-functions-json-html-xml](https://docs.openrefine.org/manual/grelfunctions/#format-based-functions-json-html-xml).

* In the new column you've just added use the dropdown menu to access 'Edit column-Add column based on this column'
* Add a name for the new column e.g. "Journal-Title"
* In the Expression box type the GREL ```value.parseJson().message.title```
* You should see in the Preview the Journal title displays

The reason for using 'Add column based on this column' is that this allows you to retain the full JSON and extract further data from it if you need to. If you only wanted the title and did not need any other information from the JSON you could use 'Edit cells->Transform...' with the same GREL expression.
{: .challenge}
