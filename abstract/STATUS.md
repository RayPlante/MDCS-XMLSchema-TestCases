# Status of this Test Case

**Test Case Name:** abstract

**Current Status:** :bangbang: open

**Note:** To include base classes as a choice,
  `PARSER_IMPLICIT_EXTENSION_BASE` must be set to `True` in the
  `settings.py` file.  

## Versions and Flavors

### MDCS : version 1.4 release

*  Equipment is included as a choice despite being marked abstract
*  Subclass of subclass not included.
*  Sample XML file loads correctly.

### MDCS : master branch, 8 Dec 2016

same as above.

