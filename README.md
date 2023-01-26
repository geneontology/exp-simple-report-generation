# simple-report-system

## Overview

This is an experimental GH Actions-based report runner.

As it stands now (and this is an early experimental mess) what we have is:

* when a ticket is opened
* multiple workflows are triggered
* if a workflow matches the label on the ticket, it continues (otherwise skipped)
* a matching workflow
  * greps out GO terms
  * makes annotation TSVs for the matched terms
  * puts them into a reports/ directory for the opened issue number
  * commits the reports back into `main`

## Things to ponder

- all sorts of fun trigger and actions can be though of here
- cleaning/archiving could be ticket closing
- maybe use gist API (pass secret)
  - allow for (easier-to-access?)raw TSVs
  - could append link comments to ticket once produced
- act on locks instead of open
- grebe
