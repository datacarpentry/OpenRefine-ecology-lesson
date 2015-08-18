---
layout: lesson
root: .
title: Scripts from OpenRefine
minutes: 
---

# Learning Objectives

* Show how OpenRefine generates JSON code 
* Save JSON code from an analysis
* Use saved JSON code to repeat an analysis 

----------------------------------------------------

# Lesson

## Scripts

* Refine saves every change, every edit you make to the dataset in a file you can save on your machine.
* If you had 20 files to clean, and they all had the same type of errors, and all files had the same columns, you could save the script, open a new file to clean, paste in the script and run it. Voila, clean data.

````
  - In the Undo / Redo section, click Extract, save the bits desired using the check boxes. 
  - Copy the code and paste it into a text editor. Save it as a .txt file. 
````

To run these steps on a new dataset, import the new dataset into Refine, open the Extract / Apply section, paste in the .txt file, click Apply.

Previous: [Working with OpenRefine](01-working-with-openrefine.html)  Next: [Saving and Exporting files and projects](03-save-export.html)
