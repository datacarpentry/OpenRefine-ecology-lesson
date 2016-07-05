---
layout: lesson
root: .
title: Services in OpenRefine
minutes: 
---

# Learning Objectives

**Optional material, and under development**

* Show call to an API, a web service (JSON example here from a locality georeferencing service)
* If time, show how to parse the JSON returned from the service.


# Lesson

Some of the columns in our dataset refer to geographic localities (`locality`), but these consist of text. We'd like to convert these to latitude / longitude. 

Open Refine is able to call remote _APIs_ (_application programming interfaces_, sometime known as _web services_) to process small pieces of our data, or to do a lookup against a remote dataset. We will send the data in a structured form, and get a structured response back, that we can unpick to add new data to our dataset.

As our dataset has a lot of records, we'll geo-reference a small subset of the data first, to see how this works. We'll do this by faceting on the "locality" column, and picking the a few locality values from the facet

````
  - Click the column header for the column `locality`
  - Click Facet->Text facet
````

Try and end up with a few dozen records displayed, based on the selected facet values.


Google Maps provide a geo-coding API (geo-referencing and geo-coding used synonymously). To use this API, you will need to register for an API key: https://developers.google.com/maps/documentation/geocoding/get-api-key

Now we need to build the call to the API. An API (a web service) is accessed using a URL (a web address). 

````
  - Click on the column header for the column named locality
  - Select "Add columns by fetching URLs". Open Refine will show a pop-up window a bit like the one used to add a new column based on an existing column (and this is what we are doing, but with a remote API).
  - The "expression" box is used to build the URL used to call the web service. Type in the following three lines:
      "https://maps.googleapis.com/maps/api/geocode/json?address="
	+ escape(value,'url')
	+'&key=YOUR_API_KEY_HERE'
 - Next we need to add a name for the new column. We'll call this new column `JSON` 
- Finally, note the "throttle delay" box - this sets how many seconds should pass between each call to the API. If you send thousands of records to the API, you will have to wait at least (this value * your number of records) milliseconds for the process to finish. Different APIs may specify in their terms of servcie how many call you can make in a given time.
- Click "OK"
````

Open Refine should show a progress dialog, and when complete you should have a new column containing a structured data response (in JSON format) from the Google Maps geocoding API. Open Refine can understand JSON data, so we can unpick this data to extract the lat / long for the locality that we supplied. 

````
- Click on the column header for the column named JSON
- Click "Add columns based on this column", and type the following into the expression box:
    parseJson(value).results[0].geometry.location.lat
- Name the new column "latitude" and click OK.
- A longitude column can be added by repeating the steps above but extracting the "lng" property from the JSON response.

````

Now we have extracted all that we need from the JSON column we can delete it, as its no longer needed.

Previous: [Saving and Exporting files and projects](03-save-export.html)
