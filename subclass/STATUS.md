# Status of this Test Case

**Test Case Name:**  subclass

**Current Status:**  :bangbang: open

**Note:** To include base classes as a choice,
  `PARSER_IMPLICIT_EXTENSION_BASE` must be set to `True` in the
  `settings.py` file.  

## Versions and Flavors

### MDCS : master branch, 8 Dec 2016

*  Subclass of subclass not included (in this case,
   `TunnellingElectronMicroscope` is not included.
*  Sample XML file, `genericlab.xml` loads fine
*  Sample XML file, `microlab.xml` loads fine, apart from giving the
   TEM the wrong type and hiding the voltage.
