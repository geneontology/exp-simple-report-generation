# simple-report-system

## Overview

This is an experimental GH Actions-based report runner.

As it stands now (and this still a bit of a mess) what we have is:

* when an issue is opened
* multiple GH workflows are triggered
* if a workflow matches the label on the issue, it continues (otherwise skipped)
* a matching workflow
  * greps out GO terms from the issue _body_.
  * makes annotation TSVs for the matched terms
  * puts them into a reports/ directory for the opened issue number
  * commits the reports back into `main`

## Current reports by label

### direct\_ann\_to\_list\_of\_terms

A set of TSVs of the annotations directly annotated the given GO terms.

### reg\_ann\_to\_list\_of\_terms

A set of TSVs of the direct and indirect annotations over the regulates
closure for the given GO terms.

## Things to ponder

- all sorts of fun triggers and actions can be thought of here
- cleaning/archiving could be ticket closing
- maybe use gist API (pass secret)
  - allow for (easier-to-access?)raw TSVs
  - could append link comments to ticket once produced
- act on locks instead of open
- grebe
- more structured runner / delagation
