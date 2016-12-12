# xs:token Simple Type Support

This Test Case demonstrates the use of the `xs:fixed` constraint.
An element or attribute that includes this constraint should be
rendered just as it would be without it, except:
* the value of fixed would be filled in or selected in the input
widget, and 
* the input widget would be disabled.  




## Run this Test

1. Load labs-fixed.xsd in as a template.
2. Open up the new document form and inspect the form.
3. Complete the form and inspect the output XML document (click on
   "Download XML"). 
4. Load real.xml as a new record; inspect the form and the
   downloaded output XML. 

The template has two text fields: `title` and `type`.  The `type`
field should contain the value "real" and should be un-editable.



