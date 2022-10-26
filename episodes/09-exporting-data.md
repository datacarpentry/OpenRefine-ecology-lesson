---
title: "Exporting and Saving Data from OpenRefine"
teaching: 10
exercises: 0
questions:
- "How can we save and export our cleaned data from OpenRefine?"
objectives:
- "Export cleaned data from an OpenRefine project."
- "Save an OpenRefine project."
keypoints:
- "OpenRefine can save the clean data to a number of formats."
- "Cleaned data or entire projects can be exported from OpenRefine."
- "Projects can be shared with collaborators, enabling them to see, reproduce and check all data cleaning steps you performed."
---

## Exporting cleaned data

You can also export just your cleaned data, rather than the entire project.

Click `Export` in the top right and select the file type you want to export the data in. `Tab-separated value` (`tsv`) or `Comma-separated value` (`csv`) would be good choices.

That file will be exported to your default `Downloads` directory. That file can then be opened in a spreadsheet program or imported into programs like R or Python.

## Saving and exporting a project

In OpenRefine you can save or export the project. This means you're saving the data and all the
information about the cleaning and data transformation steps you've done. Once you've saved a project, you can open it up again and be just where you stopped before.

### Saving

By default OpenRefine is saving your project. If you close OpenRefine and open it up again,
you'll see a list of your projects. You can click on any one of them to open it up again.

To find the location on your computer where the files are saved, see the OpenRefine manual page for [where the data is stored](https://docs.openrefine.org/manual/installing#set-where-data-is-stored).

### Exporting project files

You can also export a project. This is helpful, for instance, if you wanted to send your raw data and cleaning steps to a collaborator, or share this information as a supplement to a publication.

1. Click the `Export` button in the top right and select `OpenRefine project archive to file`.
1. A `tar.gz` file will download to your default `Download` directory. The `tar.gz` extension tells you that this is a compressed file, which means that this file contains multiple files.
1. If you open the compressed file (if on Windows, you will need a tool like 7-Zip), you should see:
  * A `history` folder which contains several `zip` files. Each of these files itself contains a `change.txt` file.
    * These `change.txt` files are the records of each individual transformation that you did to your data.
  * A `data.zip` file. When expanded, this `zip` file includes a file called `data.txt` which is a copy of your raw data.
  * You may also see other files.

### Importing project files

You can import an existing project into OpenRefine by clicking `Open...` in the upper right, then clicking on `Import Project` on the left-side menu. Click `Choose File` and select the `tar.gz` project file. This project will include all of the raw data and cleaning steps that were part of the original project.
