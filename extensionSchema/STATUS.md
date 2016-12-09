# Status of this Test Case

**Test Case Name:** | subclass
**Current Status:** | :bangbang: open

## Versions and Flavors

### MDCS : master branch, 8 Dec 2016

  * import statement:
    *  schema uploader claims that schemaLocation is required but
       this is not strictly true.  It's not clear what the proper
       value should be in the context of the curator.
    *  when including a schemaLocation element, it fails to validate
       the schema, due to:

         > Not a valid XML schema.
         > complex type ElectronMicroscope, attribute base: The QName value {urn:experiments}Equipment does not resolve to a(n) simple type definition., line 14

    *  When you are alerted about an import statement, the GUI says:

       > Please check that the resource is accessible (not on your local file system, or on a server down).

       I don't understand what this means; some better wording is
       probably in order.

    *  import works when schemaLocation is a file: URL on the server.
    *  if a global element does not exist, it uses xsi:type to for an
       OTF root element based on a global type.
    *  Regardless of the existence of a global element, it does not
       render type model correctly.  
