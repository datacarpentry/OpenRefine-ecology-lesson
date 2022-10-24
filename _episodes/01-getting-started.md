---
title: "Introduction"
teaching: 10
exercises: 0
questions:
- "How is OpenRefine useful?"
objectives:
- "Describe OpenRefine’s uses and applications."
- "Differentiate data cleaning from data organization."
- "Experiment with OpenRefine’s user interface."
- "Locate helpful resources to learn more about OpenRefine."
keypoints:
- "OpenRefine is a powerful, free and open source tool that can be used for data cleaning."
- "OpenRefine will automatically track any steps you take in working with your data."
---

# Lesson

## Motivations for the OpenRefine Lesson

- Data is often very messy, and this tool saves a lot of time on cleaning
  headaches.
- Data cleaning steps often need repeating with multiple files. It is important to know what you did to your data. This makes it easy for you to repeat these steps again with similarly structured data. OpenRefine is
  perfect for speeding up repetitive tasks by replaying previous actions on
  multiple datasets.
-  Additionally, journals, granting agencies, and other institutions are requiring documentation of the
  steps you took when working with your data. With OpenRefine, you can capture
  all actions applied to your raw data and share them with your publication as
  supplemental material.
- Any operation that changes the data in OpenRefine can be easily reversed or
  undone.
- Some concepts such as clustering algorithms are quite complex, but OpenRefine
  makes it easy to introduce them, use them, and show their power.

## What is OpenRefine?

 - OpenRefine is a Java program that runs on your machine (not in the cloud): it is a desktop application that uses your web browser as a graphical interface. No internet connection is needed, and none of the data or commands you enter in OpenRefine are sent to a remote server.
 - OpenRefine does not modify your original dataset. All actions are easily reversed in OpenRefine and you can capture all the actions applied to your data and share this documentation with your publication as supplemental material.
 - OpenRefine saves as you go. You can return to the project at any time to pick up where you left off or export your data to a new file.
 - OpenRefine can be used to standardise and clean data across your file.

### It can also help you

- Get an overview of a data set
- Resolve inconsistencies in a data set
- Help you split data up into more granular parts
- Match local data up to other data sets
- Enhance a data set with data from other sources
- Save a set of data cleaning steps to replay on multiple files

### Common scenarios

* You have a list of dates which are formatted in different ways, and want to change all the dates in the list to a single common date format. For example:

  | Data you have   | Desired data |
  |-----------------|:-------------|
  | 1st January 2014| 2014-01-01   |
  | 01/01/2014      | 2014-01-01   |
  | Jan 1 2014      | 2014-01-01   |
  | 2014-01-01      | 2014-01-01   |

* Your data file has a list of names or terms that differ from each other but refer to the same people, places or concepts. For example:

  | Data you have   | Desired data |
  |-----------------|:-------------|
  | London          | London       |
  | London]         | London       |
  | London,]        | London       |
  | london          | London       |

* There are several bits of data combined together in a single column, and you want to separate them out into individual bits of data with one column for each bit of the data. For example going from a single address field (in the first column), to each part of the address in a separate field:

  | Address in single field | Institution  | Library name  | Address 1 | Address 2 | Town/City | Region | Country | Postcode |
  |-------------------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------|:-------------|
  | University of Wales, Llyfrgell Thomas Parry Library, Llanbadarn Fawr, ABERYSTWYTH, Ceredigion, SY23 3AS, United Kingdom | University of Wales | Llyfrgell Thomas Parry Library | Llanbadarn Fawr | | Aberystwyth | Ceredigion | United Kingdom | SY23 3AS |
  | University of Aberdeen, Queen Mother Library, Meston Walk, ABERDEEN, AB24 3UE, United Kingdom | University of Abderdeen | Queen Mother Library | Meston Walk | | Aberdeen | | United Kingdom | AB24 3UE |
  | University of Birmingham, Barnes Library, Medical School, Edgbaston, BIRMINGHAM, West Midlands, B15 2TT, United Kingdom | University of Birmingham | Barnes Library | Medical School | Edgbaston | Birmingham | West Midlands | United Kingdom | B15 2TT |
  | University of Warwick, Library, Gibbett Hill Road, COVENTRY, CV4 7AL, United Kingdom | University of Warwick | Library | Gibbett Hill Road | | Coventry | | United Kingdom | CV4 7AL |

* Datasets where you want to add data and identifiers from an external data source:

  | Data you have   | Date of Birth from VIAF* | Date of Death from VIAF * |
  |-----------------|:-------------|:-------------|
  | Braddon, M. E. (Mary Elizabeth) | 1835 | 1915 |
  | Rossetti, William Michael       | 1829 | 1919 |
  | Prest, Thomas Peckett           | 1810 | 1879 |

`* Virtual International Authority File`

### Features

* Open source ([source on GitHub](https://github.com/OpenRefine/OpenRefine)).
* A large growing community, from novice to expert, ready to help.

### More Information on OpenRefine

You can find out a lot more about OpenRefine at the official user manual [docs.openrefine.org](https://docs.openrefine.org/). There is a [Google Group](https://groups.google.com/g/openrefine) that can answer a lot of beginner questions and problems. [Recipes](https://github.com/OpenRefine/OpenRefine/wiki/Recipes), scripts, projects, and extensions are available to add functionality to OpenRefine. These can be copied into your OpenRefine instance to run on your dataset.
