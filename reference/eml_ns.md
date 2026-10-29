# Get the XML namespace for a version of EML

Utility function for use when filling in `xmlns`, `schemaLocation`, or
`vocab` in various representations of EML. This is a little more
future-proof than keeping a dictionary for each version since this won't
break on the next release.

## Usage

``` r
eml_ns(version = eml_version())
```

## Arguments

- version:

  EML version, currently either eml-2.2.0 (current version) or
  eml-2.1.1. Defaults to current version.

## Value

returns the full XML namespace URI for the specified version of the
schema
