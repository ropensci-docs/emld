# emld: Ecological Metadata as Linked Data

This is a utility for transforming Ecological Metadata Language ('EML')
files into 'JSON-LD' and back into 'EML.' Doing so creates a list-based
representation of 'EML' in R, so that 'EML' data can easily be
manipulated using standard 'R' tools. This makes this package an
effective backend for other 'R'-based tools working with 'EML.' By
abstracting away the complexity of 'XML' Schema, developers can build
around native 'R' list objects and not have to worry about satisfying
many of the additional constraints of set by the schema (such as element
ordering, which is handled automatically). Additionally, the 'JSON-LD'
representation enables the use of developer-friendly 'JSON' parsing and
serialization that may facilitate the use of 'EML' in contexts outside
of 'R,' as well as the informatics-friendly serializations such as 'RDF'
and 'SPARQL' queries.

The goal of emld is to provide a way to work with EML metadata in the
JSON-LD format. At it's heart, the package is simply a way to translate
an EML XML document into JSON-LD and be able to reverse this so that any
semantically equivalent JSON-LD file can be serialized into EML-schema
valid XML.

## Details

The package has only three core functions:

- [`as_emld()`](https://docs.ropensci.org/emld/reference/as_emld.md)
  Convert EML's `xml` files (or the `json` version created by this
  package) into a native R object (an S3 class called `emld`,
  essentially just a `list`).

- [`as_xml()`](https://docs.ropensci.org/emld/reference/as_xml.md)
  Convert the native R format, `emld`, back into XML-schema valid EML.

- [`as_json()`](https://docs.ropensci.org/emld/reference/as_json.md)
  Convert the native R format, `emld`, into `json`(LD).

## See also

Useful links:

- <https://docs.ropensci.org/emld/>

- <https://github.com/ropensci/emld>

- Report bugs at <https://github.com/ropensci/emld/issues>

Useful links:

- <https://docs.ropensci.org/emld/>

- <https://github.com/ropensci/emld>

- Report bugs at <https://github.com/ropensci/emld/issues>

## Author

**Maintainer**: Carl Boettiger <cboettig@gmail.com>
([ORCID](https://orcid.org/0000-0002-1642-628X)) \[copyright holder\]

Authors:

- Matthew B. Jones <jones@nceas.ucsb.edu>
  ([ORCID](https://orcid.org/0000-0003-0077-4738)) \[copyright holder\]

- Bryce Mecum <mecum@nceas.ucsb.edu>
  ([ORCID](https://orcid.org/0000-0002-0381-3766)) \[copyright holder\]
