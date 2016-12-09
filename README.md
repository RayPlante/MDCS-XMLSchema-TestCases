# MDCS XML Schema Test Cases

This repository documents XML Schema test cases for support in
[MDCS](https://github.com/usnistgov/MDCS).  That is, these test cases
represent XML Schema definition patterns that submitters would like
MDCS to understand and interpret correctly: when a schema that employs
such a pattern is loaded into MDCS, MDCS will create curation form
that properly reflect the intent of the pattern.

Each directory contains a different example XML Schema file and one or
more XML instance documents that conform to that schema.  The
`README.md` document describes the pattern and provides any special
instructions for installing it and testing the pattern within MDCS.
The `STATUS.md` file provides a description of the status of the
support of the pattern within the different versions and flavors
(e.g. the registry) of the MDCS application suite.

A summary of the status of all the test cases can be found in the
[STATUS.md](STATUS.md) file in this directory.  This lists which test
cases are considered still open--that is, there are still problems
supporting the pattern in pertinent versions/flavors of MDCS--and
those that are closed (where we are satisfied with the support in the
latest versions).

## Testing a Test Case

Each test case's README.md includes the detailed instructions for
testing it.  The procedure, however, is basically the same:

1. Load the schema file (or files) into MDCS as a template
2. Select the newly created template
3. Attempt to create a new record and viewing the form.
4. If example XML instances are provided, attempt to upload the file
   and view its presentation in the edit form.

## Adding New Test Cases

### Overview

The test cases in the master branch should complete and contain valid
schemas and instances.  New test cases that are not yet in this state
but which benefit from sharing and discussion should appear in the
`proposed` branch or some other branch.  When test cases are complete
and valid, they can be merged into the `master` branch.

### Developing a New Test Case

When developing a new test case...
* You may develop new test cases externally to this repository
* Create a new directory, and include:
  * schemas that demonstrate the pattern of interest; it is
    recommended that you construct these as simply as possible to
    isolate issues of interest.
  * one or more XML instance documents that conform to your schema(s).
  * a README.md file that explains the tests case: what it does, why
    it's important, how to demonstrate it in MDCS, and what the
    resulting support should look like.
  * a STATUS.md file that explains what the actual behavior of the
    different versions of MDCS; follow the pattern shown in, say, the
    [subclass](subclass/STATUS.md) directory.
* Check the validity of your schemas and instance documents as you
  develop.
  * IDE applications (such as Oxygen) will have validation built in.
  * For command line validator, you can use the [junx package's
    validator tool](https://github.com/RayPlante/junx).  This is built
    on the Apache Java XML validating parser, Xerxes. 
  * Apache Xerxes should be considered the reference validator.
* When you wish to share your test case for discussion, create a pull
  request into the `proposed` master (or some other branch than
  `master`).  The test case can continue to evolve after the pull
  request is accepted; just submit additional pull requests.
* When the test is stable and demonstrated to be valid, it can be
  merged into the master branch.  

