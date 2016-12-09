# Support for `xsi:type` and Extension Schemas

An _extension schema_ refers to an XML schema which includes subclasses
(complex types that use `xs:extension`) that extend types in another
schema and having a different namespace.  Types from both schemas can
be combined into XML instance documents through the use of
`xsi:type`.  This pattern is a powerful form of extension because the
extensions schemas can be created after the base schema (and by
different non-cooperating authors) and using them together does not
require that the base schema be altered in any way.  This is in
contrast to aggregation patterns.

## When to Use This Pattern 

This pattern addresses the problem of schemas changing over time so
that applications can adapt as needed without breaking.  Note that
anytime a schema is updated, its namespace should change; otherwise,
existing applications not aware of the schema change may break when
encoutering more up-to-date documents.  However, once a namespace is
changed, the existing applications should not recognize the new
namespace and should have no reasonable way to expect to process it.

The extension schema pattern gives applications to adapt to changes in
the schema.  It is based on a core schema that does not change; all
interoperating applications understand it.  Changes are handled
through additional extensions schemas, each with its distinct
namespace.  Instance documents use the root element from the base
schema and may draw on types from the extension schemas.  Applications
can recognize and consume the elements from the core schema plus any
of the extensions it recognizes.  Applications can ignore extensions
that they don't recognize (from their namespace).

Extension schemas can be created anytime after the base schema and
require no changes to base schema.  Thus, the core schemas namespace
never needs to change.

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

