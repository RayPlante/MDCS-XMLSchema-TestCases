# Support for `xsi:type` and XML Subclasses

This Test Case demonstrates the use `xsi:type` to invoke XML
by-extension subclasses (that is, `xs:complexType` definitions that
use `xs:extension`).  In this particular case the base class and
subclasses are all defined in the same schema, with the same XML
namespace. 

The [`labs.xsd`](labs.xsd) schema defines a base complex type called
`Equipment` containing two child elements.  The `ElectronMicroscope`
extends `Equipment`, adding a third child element, and the
`TunnellingElectronMicrocope` extends `ElectronMicroscope` to further
add a fourth child element.

When MDCS creates a form for this schema as a template, at the point
where a piece of equipment can be described, it should present a
drop-down menu that offers `Equipment`, `ElectronMicroscope`, and
`TunnellingElectronMicrocope` as choices.  The form for the content
elements should update depending on the choice made.

The output XML data should make proper use of the `xsi:type` attribute
to identify the subclass of `Equipment` was chosen.

Use of the `xsi:type` in this example demonstrates a type of
polymorphism.  Subclassing can group similar kinds of descriptions,
providing them with common metadata but still allow variations with
additional metadata.  The `xsi:type` attribute allows instance authors
to choose which variety of an object they are describing.  (This
technique is more powerful than aggregation patterns when the
subclasses are imported from different schemas; see
[extensionSchema](../extensionSchema).)

## Run this Test

1. Load [`labs.xsd`](labs.xsd) in as a template.
2. Open up the new document form and inspect the form; ensure all
   classes appear in the menu and the form updates properly for each
   type when chosen.
3. Complete the form and inspect the output XML document (click on
   "Download XML"); ensure `xsi:type` is used.
4. Load [`genericlab.xml`](genericlab.xml) and
   [`microlab.xml`](microlab.xml) as a new records; inspect 
   the form and the downloaded output XML. 

