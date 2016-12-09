# xs:token Simple Type Support

This Test Case demonstrates the use of the `xs:token` support.  An
`xs:token` simple type should be handled by MDCS identically to
`xs:string`.

The main distinction between `xs:token` from `xs:string` is one that
concerns consumers of the XML documents; it mostly does not concern
MDCS.  With `xs:token`, consumers are instructed to drop excess white
space from the string before using it.  For example, it would be
important to drop the extra space before comparing it with the same
value from another instance document.  `xs:token` is sometimes
preferred because it can make the XML document a little friendlier to
the human reader because space may be inserted around the value
(separating it from its XMLtags a bit) without affecting the semantics
of the value.

## Run this Test

1. Load mylab.xsd in as a template.
2. Open up the new document form and inspect the form.
3. Complete the form and inspect the output XML document (click on
   "Download XML"). 
4. Load mylab-inst.xml as a new record; inspect the form and the
   downloaded output XML. 

The template has two text fields: `title` and `type`.  They should
appear the same in form.

