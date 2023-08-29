[![Create a Slack Account with us](https://img.shields.io/badge/Create_Slack_Account-The_Carpentries-071159.svg)](https://slack-invite.carpentries.org/)
[![Slack Status](https://img.shields.io/badge/Slack_Channel-dc--ecology--openref-E01563.svg)](https://carpentries.slack.com/messages/C9Y0RDGPQ)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.570048.svg)](https://doi.org/10.5281/zenodo.570048)

# OpenRefine-ecology

**Data Cleaning with OpenRefine for Ecologists** Lesson for [Data Carpentry](https://datacarpentry.org/lessons/#ecology-workshop)

## OpenRefine Version

The current version has been tested with OpenRefine 3.7.2 on May 2023.

## Data set notes

- This data set is derived from [The Portal Project Long-term desert ecology](https://portal.weecology.org/) project data. [This data file](https://www.esapubs.org/archive/ecol/E090/118/Portal_rodents_19772002.csv) was downloaded and then modified specifically for use with OpenRefine.
  - Taxon names were put back into the file.
  - The number of rows was reduced to simplify the reconciliation and URL parsing exercises.
  - These modifications were made in order to illustrate some features of Open Refine.
    - Errors were added to the taxon names (`scientificName` field), to demonstrate OpenRefine's ability to find likely mis-entered data.
    - These errors can be found using clustering algorithms on the `scientificName` column, showing the power of the algorithms to find discrepancies quickly and making it simple to fix all issues found.

## Contributing

We welcome all contributions to improve the lesson! Maintainers will do their best to help you if you have any questions, concerns, or experience any difficulties along the way.
We'd like to ask you to familiarize yourself with our [Contribution Guide](CONTRIBUTING.md).

Please see the current list of [issues](https://github.com/datacarpentry/OpenRefine-ecology-lesson/issues) for ideas for contributing to this repository. For making your contribution, we use the GitHub flow, which is nicely explained in the chapter [Contributing to a Project](https://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project) in Pro Git by Scott Chacon.

Look for the tag ![good\_first\_issue](https://img.shields.io/badge/-good%20first%20issue-gold.svg). This indicates that the maintainers will welcome a pull request fixing this issue.

## Maintainers

### Current Maintainers

- Luis J. Villanueva ([villanueval@si.edu](mailto:villanueval@si.edu))

### Past Authors and Maintainers

- Abigail Cabunoc
- Aleksandra Nenadic
- April M. Wright
- Betty Rozum
- Bill Mills
- Brian Yandell
- C. Titus Brown
- Cam Macdonell
- Dan Mazur
- Debbie Paul
- Erin Becker
- Francois Michonneau
- Gabriel A. Devenyi
- Greg Wilson
- Hilmar Lapp
- Hugo Tavares
- Ian Carroll
- James Allen
- James Mickley
- Jeffrey W. Hollister
- Jon Pipitone
- Jonah Duckles
- Kari L. Jordan
- Lisa Zilinski
- Maxim Belkin
- Michael Hansen
- Nick Young
- Piotr Banaszkiewicz
- Raniere Silva
- Ross Dickson
- Ryan E. Johnson
- Rémi Emonet
- Timothée Poisot
- Tracy Teal
- W. Trevor King
- Zack Brym
- dlstrong
- evanwill
- trelogan

See the [Authors](AUTHORS) page for details.


