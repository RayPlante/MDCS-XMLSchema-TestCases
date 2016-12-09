# Status of this Test Case

**Test Case Name:** | subclass
**Current Status:** | :bangbang: open

## Versions and Flavors

### MDCS : master branch, 8 Dec 2016

*  Only VacuumPump is offered as an option.  

*  The behavior of [subclass](../subclass) and 
   [abstract](../abstract) offer clues as to why only VacuumPump is
   offered as a choice:
   * [subclass](../subclass) shows that base classes are not being
     offered
   * [subclass](../subclass) also shows that subclasses of subclasses
     are not offered
   * while [abstract](../abstract) is ambiguous on its own, this test
     suggests that abstract is being honored, since it is not being
     offered.

