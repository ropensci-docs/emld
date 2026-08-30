# Coerce an emld object into XML (EML's standard format)

Coerce an emld object into XML (EML's standard format)

## Usage

``` r
as_xml(x, file = NULL, root = "eml", ns = "eml", schemaLocation = TRUE)
```

## Arguments

- x:

  an emld object

- file:

  optional path to write out to file. Otherwise, defaults to NULL and
  will return an xml_document object.

- root:

  name for the root node; default to 'eml'

- ns:

  namespace abbreviation on root node, default 'eml'

- schemaLocation:

  If not explicitly set on `x`, automatically set `xsi:schemaLocation`
  based upon the root namespace (`TRUE`, default), do not set a
  `xsi:schemaLocation` (`FALSE`), or set a specific `xsi:schemaLocation`
  value (`"Your value here..."`). See Examples.

## Value

a xml_document object. Or if a file path is provided, the metadata is
written out in XML file and the function returns `NULL` invisibly.

## Details

Unlike as_json, this function cannot rely on the existing convention of
serializing a list to xml, eg, as defined by xml2::as_xml_document()
Instead, this relies on a modified version, as_eml_document. In addition
further steps must be taken when working with JSON-LD to deal with
different possible framings and namespaces from the JSON-LD context
element. Thus this `as_xml` function is particular to EML and `emld`
objects alone.

## Examples

``` r
f <- system.file("extdata/example.xml", package = "emld")
emld <- as_emld(f)
xml <- as_xml(emld)

## can also write directly to a file:
xml_file <- tempfile()
as_xml(emld, xml_file)

## if you don't want the `xsi:schemaLocation` attribute set
as_xml(emld, schemaLocation = FALSE)
#> A value for 'schemaLocation' was set in the document but the 'schemaLocation' argument was set to 'FALSE' so the value from the document was retained. To serialize a document without a schemaLocation, remove the 'schemaLocation' element from the document before serializing.
#> {xml_document}
#> <eml packageId="eml.1.1" xsi:schemaLocation="https://eml.ecoinformatics.org/eml-2.2.0/ eml.xsd" system="knb" xmlns:eml="https://eml.ecoinformatics.org/eml-2.2.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:stmml="http://www.xml-cml.org/schema/stmml-1.2">
#> [1] <dataset>\n  <title>Data from Cedar Creek LTER on productivity and specie ...

## or if you want to set your own value
as_xml(emld, schemaLocation = "https://eml.ecoinformatics.org/eml-2.2.0
http://example.com/eml-2.2.0/eml.xsd")
#> {xml_document}
#> <eml packageId="eml.1.1" xsi:schemaLocation="https://eml.ecoinformatics.org/eml-2.2.0/ eml.xsd" system="knb" xmlns:eml="https://eml.ecoinformatics.org/eml-2.2.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:stmml="http://www.xml-cml.org/schema/stmml-1.2">
#> [1] <dataset>\n  <title>Data from Cedar Creek LTER on productivity and specie ...
```
