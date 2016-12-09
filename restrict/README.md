# Support for `xsi:type` and XML Subclasses

This Test Case demonstrates the case when you wants to subclass by
restriction and extension simultaneously.  That is, you might want to
fix the values of some content as well as add some additional
content.  Since XML Schema does not allow one to do both of these in
the same subclass, the solution is to first subclass by restriction
and then again by extension.  You probably don't want to make the
intermediate restricted class available, so you would make that
abstract.  

This Test Case is much like that demonstrated in
[subclass](../subclass).  In this example, an abstract class is
inserted in the inheritance tree to `ElectronMicroscope` that
restricts the type attribute by setting a default value.  

The [`labs.xsd`](labs.xsd) schema defines a base complex type called
`Equipment` containing two child elements.  The `ElectronMicroscope`
extends `Equipment`, adding a third child element, and the
`TunnellingElectronMicrocope` extends `ElectronMicroscope` to further
add a fourth child element.

When MDCS creates a form for this schema as a template, at the point
where a piece of equipment can be described, it should present a
drop-down menu that offers `Equipment`, `ElectronMicroscope`, 
`TunnellingElectronMicrocope`, and `VacuumPump` as choices.  It should
not offer `_ElectronicMicroscope` (the abstract intermediate subclass)
as a choice.  The form for the content elements should update
depending on the choice made. 

The output XML data should make proper use of the `xsi:type` attribute
to identify the subclass of `Equipment` was chosen.

## Run this Test

1. Load [`labs-restr.xsd`](labs-restr.xsd) in as a template.
2. Open up the new document form and inspect the form; ensure all
   non-abstract classes appear in the menu and the form updates
   properly for each type when chosen.
3. Complete the form and inspect the output XML document (click on
   "Download XML"); ensure `xsi:type` is used.
4. Load [`genericlab.xml`](genericlab.xml) and
   [`microlab.xml`](microlab.xml) as a new records; inspect 
   the form and the downloaded output XML. 

