---
title: "Exporting Data Cleaning Steps"
teaching: 10
exercises: 5
questions:
- "How can we document the cleaning steps we've applied to our data?"
- "How can we apply these steps to additional data sets?"
objectives:
- "Demonstrate ability to export cleaning steps as JSON code from OpenRefine"
- "Apply the saved cleaning steps to a different dataset to repeat the cleaning process"
keypoints:
- "All changes are being tracked in OpenRefine (apart from individual cell changes and sorting!), and this information can be used for scripts for future analyses or reproducing an analysis"
- "Scripts can (and should) be published together with the dataset as part of the digital appendix of the research output"
---

## Scripts

We have seen that from the section on `Undo / Redo` that OpenRefine saves every change you make to the dataset. You can
export this information so that you can apply the same process to other datasets without having to go through each of
the individual steps. This saves a lot of time, because you frequently will apply the same data cleaning steps to a
number of datasets over time. The files must all had the same structure, the same 
type of errors (e.g. species name misspellings, leading white spaces) and the same column names.

The information about the transformations that have taken place are stored in OpenRefine using a format
known as [JSON (JavaScript Object Notation)](https://en.wikipedia.org/wiki/JSON). This is a popular, open standard  for
data interchange that benefits from also being human readable (you may not believe this, but it's certainly more readable
than most).

You're going to need a tool to save the JSON during this next exercise. Any text editor will work (like NotePad on
Windows or TextEdit on Mac). Do not use a Word Processor (e.g. Word) for this step, because they have a tendency to
automatically change text for perceived grammatical or spelling mistakes. This will, of course, render the JSON useless. 

1. In the `Undo / Redo` section, click `Extract...` in the top left corner of the screen
2. A pop up will open which includes two columns: one lists the steps you have taken to transform your data with tick
   boxes next to each step, and the other lists same information in the JSON format (this is a text file peppered with
   lots of `{`, `:`, `,` and `"`)
3. As you check and uncheck the tick boxes, the JSON will change appropriately. For now, ensure that all tick boxes are
   ticked so that all the steps are selected.
4. Highlight all of the JSON from the right hand panel and then copy it.
5. Paste the JSON into your text editor (see above for details), then save it as a plain text file, i.e. `.txt`. In
   TextEdit, do this by selecting `Format` > `Make plain text` and save the file as a `my_analysis.txt`. 

In practice, you would re-run the steps on a new dataset, but to keep things simple, in the next example we will re-run
the steps on the original dataset.  

1. Start a new project in OpenRefine: click the "OpenRefine" name in the top-left hand corner of the screen to be taken
   back to the main interface. Create a project using the same dataset as last time (if you've misplaced it, you can
   download a [new copy](https://ndownloader.figshare.com/files/7823341))  
1. Once the dataset has loaded, click the `Undo / Redo` tab then the `Apply` button.
1. A pop-up will open with a blank text filed into which you can paste the JSON contents of your `my_analysis.txt` file. 
1. Click `Perform operations`. The pop up will close, and all of the transformations you applied to the previous dataset
   will be re-applied to your current dataset to produce a new cleaned dataset.

Although this process only involved the re-application of 5 or 6 steps, with real research data you could be reapplying
hundreds of transformations - and you might have to re-apply those steps to tens of datasets. This is why there is such
potential for saving time with the export/apply functionality of OpenRefine. 

## Reproducible science

Now, that you know how scripts work, you may wonder how to use them in your own scientific research. For inspiration,
you can read more about the successful application of the reproducible science principles in archaeology or marine
ecology:
1. Marwick et al. (2017) [Computational Reproducibility in Archaeological Research: Basic Principles and a Case Study of Their Implementation](https://link.springer.com/article/10.1007/s10816-015-9272-9)
2. Stewart Lowndes et al. (2017) [Our path to better science in less time using open data science tools](https://www.nature.com/articles/s41559-017-0160)