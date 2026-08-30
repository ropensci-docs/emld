# Find the root schema module and version

Find the root schema module and version

## Usage

``` r
guess_root_schema(doc)
```

## Arguments

- doc:

  An `xml_document`

## Value

If found, a list with names 'version', 'module', and \`namespace. If not
found, throws an error.
