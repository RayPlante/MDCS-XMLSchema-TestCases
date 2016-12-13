# Support for `elementFormDefault="unqualified"`

This is a variation on the [extensionSchema](../extensionSchema) test
case where the schema's `elementFormDefault` attribute is set to
`unqualified`.  This says that non-global elements do not require
namespace qualification.  (Technically, it means that non-global
elements belong to the no-name namespace.)  In the pattern shown here,
only the root element and `xsi:type` values require namespace
qualifiers.  

This is setting is useful when mixing types from different namespaces
are mixed together.  Instance authors do not have to be cognizant of
which elements in an extended type come from which schema.  XML Paths
are simpler as well for the same reason.  Instance documents become
less error-prone.  

## Test Details

The [`experiments.xsd`](experiments.xsd) file defines the core schema
with a root element, `LabSetup`, that takes a list of equipment
descriptions via the `equipment` element.  It defines a default
complex `Equipment` type that can capture some generic metadata
(`vendor` and `model`).  The [`microscopy.xsd`](microscopy.xsd) file
is the extension schema; it defines an extension of `Equipment` called
`ElectronMicroscope`.  This latter type adds an additional element to
the content (`magnification`).

When loaded into MDCS and the curation form is produced, it should
offer a drop-down menu where a piece of equipment can be
described. The menu should offer the generic `Equipment` base class and
the `ElectronMicroscope` as options.

To make exported documents more human readable, it is recommended that
the default namespace be set to the no-name namespace
(i.e. `xmlns=""`), and the root element is qualified with a defined
namespace prefix.  

## Run this Test

1. Load [`experiments.xsd`](experiments.xsd) in as a template.
2. Load [`microscopy.xsd`](microscopy.xsd) in as a template.  _Not
   sure about this_
2. Open up the new document form and inspect the form; ensure all
   classes appear in the menu and the form updates properly for each
   type when chosen.
3. Complete the form and inspect the output XML document (click on
   "Download XML"); ensure `xsi:type` is used.
4. Load [`genericlab.xml`](genericlab.xml) and
   [`microlab.xml`](microlab.xml) as a new records; inspect 
   the form and the downloaded output XML. 

