# Support for `xsi:type` and XML Subclasses

This Test Case is just like that demonstrated in
[subclass](../subclass) except that the base class is declared
abstract.  It not only prevents an element from being instantiated
with the type, but it also forces the use of `xsi:type`.  

The [`labs.xsd`](labs.xsd) schema defines a base complex type called
`Equipment` containing two child elements, _and which is declared
abstract_.  The `ElectronMicroscope` extends `Equipment`, adding a
third child element, and the `TunnellingElectronMicrocope` extends
`ElectronMicroscope` to further add a fourth child element.

When MDCS creates a form for this schema as a template, at the point
where a piece of equipment can be described, it should present a
drop-down menu that offers only `ElectronMicroscope`, and
`TunnellingElectronMicrocope` as choices; `Equipment` should not be
offered as option (since it is abstract).  The form for the content
elements should update depending on the choice made.

The output XML data should make proper use of the `xsi:type` attribute
to identify the subclass of `Equipment` was chosen.

The abstract feature is helpful when one wants to provide a subclass
that both restricts the inherited content but also extends it with new
ones.  See [restrict](../restrict) for an example.

## Run this Test

1. Load [`labs-abseq.xsd`](labs-abseq.xsd) in as a template.
2. Open up the new document form and inspect the form; ensure all
   classes appear in the menu and the form updates properly for each
   type when chosen.
3. Complete the form and inspect the output XML document (click on
   "Download XML"); ensure `xsi:type` is used.
4. Load [`microlab.xml`](microlab.xml) as a new records; inspect 
   the form and the downloaded output XML. 

