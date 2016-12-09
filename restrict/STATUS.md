# Status of this Test Case

**Test Case Name:** | subclass
**Current Status:** | :bangbang: open

## Versions and Flavors

### MDCS : master branch, 8 Dec 2016

*  Only `Equipment` and `VacuumPump` is offered as an option.  Given
   that [abstract](../abstract) also fails and subclasses of
   subclasses are not supported, this is not surprising.

*  `genericlab.xml` loads fine; `microlab.xml` does not since needed
   subclasses are not available.

