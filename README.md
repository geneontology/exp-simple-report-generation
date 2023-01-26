# exp-simple-report-generation

A repo to experiment with reports run through GH.

As it stands now (and this is an early experimental mess) what we have is:

* when a ticket is opened
* it is checked for a label ("REPORTY")
* if it is found, we
  * make a directory in reports in the main repo that corresponds to the issue number
  * run a golr query top get TSVs for all GO terms found in the issue body
  * commit the reports back to the repo

Things to ponder:

- all sorts of fun trigger and actions can be though of here
- cleaning/archiving could be ticket closing
- maybe use gist API (pass secret)
  - allow for (easier-to-access?)raw TSVs
  - could append link comments to ticket once produced
