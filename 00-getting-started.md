
# Data Carpentry Open Refine Demo

--------------------------------------------------

# Objectives

* Motivate participants to clean, organize, enhance data before insert into a database or merging data with other data files.
* Introduce participants to Open Refine as a powerful data-cleaning tool.
* Encourage dataset exploration; look at the data with the visualization tools in Open Refine.
* Introduce concept of facets
* Show split columns by defined separator
* Show power of include / exclude, sort by name / count
* Show the power of clustering algorithms to reveal data patterns, data snafus
* If time, show call to an API, a web service (JSON example here from a locality georeferencing service)
* If time, show how to parse the JSON returned from the service.
* Refine provides a gentle introduction to SELECT DISTINCT, COUNT, ORDER BY, GROUP BY, and other SQL concepts in a visual way. Covering Refine first provides the SQL instructor with examples to refer back to - giving the students a reference point for understanding SQL. And starting with the "better spreadsheet skills" lesson, before this Open Refine demo, gives the instructor even more analogies to use when leading up to SQL. We experimented with lesson order and this seems to work best for insuring those "aha" moments.
* Show the power of undo / redo.
* Can be used to introduce
 - scripting
 - regular expressions
 - APIs

----------------------------------------------------

# Motivations for the Open Refine Lesson

* It's really important that you know what you did. More journals/grants/etc. are also making it important for them to know what you did. You can capture all steps done to your data in Open Refine to the raw file and share with your publication as supplemental material.
* All steps are easily reversed in Refine.
* You _must_ save your work to a new file; Refine _does not_ modify your original dataset.
* Data is often very messy - and this tool saves a lot of cleaning headaches.
* Data cleaning steps often need repeating with multiple files. Refine is perfect for speeding up repetitive tasks.
* Some concepts like clustering algorithms are quite complex, but Refine makes it easy to introduce them, use them, and show their power.

# Before we get started

* Check that you have Firefox browser installed. Open Refine runs in this browser. It will not run in IE.
* Download software from http://openrefine.org if you have not done this yet.
* Unzip the downloaded file into a directory. Name that directory something like Open-Refine
* Note that "double-clicking" a zipped file on a windows machine sometimes results in a correctly unzipped set of files, other times, this is not successful. Try installing 7-Zip and use 7-Zip to extract all files from the zipped file to the desired directory.
* Go to your newly created Open-Refine directory.
* Click the google-refine.exe file to launch Open Refine.
* Note, this is a Java program that runs on your machine (not in the cloud). It runs inside the Firefox browser, but no web connection is needed.

# Basics of Open Refine

You can find out a lot more about Open Refine at http://openrefine.org and check out some great introductory videos. There is also an Open Refine Google Plus community https://plus.google.com/communities/117280693504889048168 where you can find a lot of help and a lot of folks from the life sciences are members. As with other programs of this type, Open Refine libraries are available too, where you can find a script you need and copy it into your Refine instance to run it on your dataset.

* Open source.
* A large growing community, from novice to expert, ready to help.
* Works with large-ish datasets (100,000 rows). Does not scale to many millions. (yet).

# Demo of Open Refine

Start the program. (Double-click on the google-refine.exe file. Java services will start on your machine, and Refine will open in your Firefox browser).

Note the file types Open Refine handles: TSV, CSF, *SV, Excel (.xls .xlsx), JSON, XML, RDF as XML, Google Data documents. Support for other formats can be added with Google Refine extensions.

In this first step, we'll browse our computer to the sample data file for this lesson. In this case, I've modified the Portal_rodents csv file. I added several columns: scientificName, locality, county, state, country and I generated several more columns in the lesson itself (JSON, decimalLatitude, decimalLongitude). Data in locality, county, country, JSON, decimalLatitude and decimalLongitude are contrived and are in no way related to the original dataset. When doing this demo, the columns: JSON, decimalLatitude, decimalLongitude can be deleted, and then recreated if time, with a call to a locality service, and subsequent parsing of the JSON data returned by the service.

_Once Refine is open, you'll be asked if you want to Create, Open, or Import a Project._

* Click Browse, find Portal_rodents_19772002_scinameUUIDs.csv
* Click next to open Portal_rodents_19772002_scinameUUIDs.csv
* Refine gives you a preview - a chance to show you it understood the file. If, for example, your file was really tab-delimited, the preview might look strange, you would choose the correct separator in the box shown and click "update preview."
* If all looks well, click _Create Project._

## Faceting

* Scroll over to the scientificName column
* Click the down arrow and choose > Facet > Text facet
* In the left margin, you'll see a box containing every unique, distinct value in the scientificName column and Refine shows you how many times that value occurs in the column (a count), and allows you to sort (order) your facets by name or count.
* Edit. Note that at any time, in any cell of the Facet box, or data cell in the Refine window, you have access to "edit" and can fix an error immediately. Refine will even ask you if you'd like to make that same correction to every value it finds like that one (or not).

## Cluster

* One of the most magical bits of Refine, the moment you realize what you've been missing. Refine has several clustering algorithms built in. Experiment with them, and follow the link inside Refine, to learn more about these algorithms and how they work. https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth
* In this example, in the scientificName Text Facet we created in the step above, click the _Cluster_ button.
* In the resulting pop-up window, you can change the algorithm method, and keying function. Try different combinations to see the difference.
* For example, with this dataset, the _nearest neighbor_ method with the _PPM_ keying function shows the power of clustering the best. 
* Intentional errors in these scientific names have been introduced to show how errors (typos) in any position can be found with this method. All errors can then be fixed by simply entering the correct value in the box on the right. Often, the algorithm has guessed correctly. 
* After corrections are made in this window, you can either Merge and Close the Cluster pop-up, or Merge and Re-cluster.


## Split / Leading - Trailing Whitespace / Undo - Redo

* If data in a column needs to be split into multiple columns, and the strings in the cells are separated by a common separator (say a comma, or a space), you can use that separator to divide up the bits into their own columns.
* Go to the drop-down tab at the top of the column that you need to split into multiple columns
* For example, go to the scientificName column > from drop-down choose Edit Column > Split into several columns
* In the pop-up, for separator, remove the comma, put in a space
* Remove the check in the box that says "remove column after splitting"
* You'll get two extra columns called, in this case: scientificName 1, scientificName 2
* This will reveal an error in a few names that have spaces at the beginning (so-called leading white space).
 - These can be easily removed with another Refine feature in the column drop-down choices. See drop-down: Edit cells > Common transforms > Remove leading and trailing whitespace
* To Undo create columns, look just above the scientificName cluster in the left side of the screen. Click where it says Undo / Redo. Click back one step (all steps, all changes are saved here). Just go back to the previous step and click. The extra columns will be gone.

## Call a Service (this example is set up to georeference locality data, but could use any service).

* For this demo, the instructor may find a web service appropriate to demonstrate.

## Scripts

* Refine saves every change, every edit you make to the dataset in a file you can save on your machine.
* IF you had 20 files to clean, and they all had the same type of errors, and all files had the same columns, you could save the script, open a new file to clean, paste in the script and run it. Voila, clean data.
* In the Undo / Redo section, click Extract, save the bits desired using the check boxes. Save the code in a .txt file. To run these steps on a new dataset, import the new dataset into Refine, open the Extract / Apply section, paste in the .txt file, click Apply.

## Export 

* Save your work when you are done by exporting it in the desire format. Save your files with meaningful names, no spaces. Refine does not change your original dataset.

#### Time estimate for this demo.
* Takes about 20 - 30 minutes to do a good demo.
* If students are going to install and then try this tool out on the provided dataset or their own dataset, it will take longer.
* Mac users with the newest operating system will have to allow this to run by "allowing everything" to run. They can change the setting back after the exercise.
* Some students will run into issues with
  - unzipping
  - finding the .exe file once the software has been unzipped
