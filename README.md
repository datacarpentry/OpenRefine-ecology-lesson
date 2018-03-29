[![Create a Slack Account with us](https://img.shields.io/badge/Create_Slack_Account-The_Carpentries-071159.svg)](https://swc-slack-invite.herokuapp.com/) 
[![Slack Status](https://img.shields.io/badge/Slack_Channel-dc--ecology--openref-E01563.svg)](https://swcarpentry.slack.com/messages/C9Y0RDGPQ) 

# OpenRefine-ecology
Lesson on OpenRefine for ecology

### Data set notes.
* This data set is derived from [The Portal Project Long-term desert ecology](http://portal.weecology.org/) project data. [This data file](http://www.esapubs.org/archive/ecol/E090/118/Portal_rodents_19772002.csv) was downloaded and then modified specifically for use with OpenRefine.
    * Taxon names were put back into the file.
    * Globally Unique Identifiers (in the form of UUIDs) were added.
* These modifications were made in order to illustrate some features of Open Refine.
    - Errors were added to the taxon names (`scientificName` field), to demonstrate OpenRefine's ability to find likely mis-entered data.
    - These errors can be found using clustering algorithms on the `scientificName` column, showing the power of the algorithms to find discrepancies quickly and making it simple to fix all issues found.
    
### Options.
* For someone already familiar with OpenRefine, it would be a very simple matter to substitute a different data set, as desired.
