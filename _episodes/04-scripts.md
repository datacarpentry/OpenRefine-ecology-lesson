---
title: "Scripts from OpenRefine"
teaching: 10
exercises: 5
questions:
- "How can we document the data-cleaning steps we've applied to our data?"
- "How can we apply these steps to additional data sets?"
objectives:
- "Describe how OpenRefine generates JSON code."
- "Demonstrate ability to export JSON code from OpenRefine."
- "Save JSON code from an analysis."
- "Apply saved JSON code to an analysis."
keypoints:
- "All changes are being tracked in OpenRefine, and this information can be used for scripts for future analyses or reproducing an analysis."
---

# Lesson

## Scripts

As you conduct your data cleaning and preliminary analysis, OpenRefine saves every change you make to the dataset. These 
changes are saved in a format known as JSON (JavaScript Object Notation). You can export this JSON script and apply it to other data files. If you had 20 files to clean, and they all had the same type of errors (e.g. species name misspellings, leading white spaces), and all
files had the same column names, you could save the JSON script, open a new file to clean in OpenRefine, paste in the script and run it.
This gives you a quick way to clean all of your related data.

1. In the `Undo / Redo` section, click `Extract...`, and select the steps that you want to apply to other datasets by clicking the check boxes. 
2. Copy the code from the right hand panel and paste it into a text editor (like NotePad on Windows or TextEdit on Mac). Make sure it saves as a plain text file. In TextEdit, do this by selecting `Format` > `Make plain text` and save the file as a `txt` file. 

Let's practice running these steps on a new dataset. We'll test this on an uncleaned version of the dataset we've been working with. 

1. Download an uncleaned version of the dataset: [https://ndownloader.figshare.com/files/7823341](https://ndownloader.figshare.com/files/7823341) or use the version of the raw dataset you saved to your computer.  
2. Start a new project in OpenRefine with this file and name it something different from your existing project.  
3. Click the `Undo / Redo` tab > `Apply` and paste in the contents of `txt` file with the JSON code. 
4. Click `Perform operations`. The dataset should now be the same as your other cleaned dataset.

For convenience, we used the same dataset. In reality you could use this process to clean related datasets. For example, data that you had collected over different fieldwork periods or data that was collected by different researchers (provided everyone uses the same column headings). 

