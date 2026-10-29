# Guess an appropriate `schemaLocation` value for a given version of the schema

This is a simple helper to make filling in the `schemaLocation`
attribute on documents this package creates. Supports EML 2.1.1 and
newer.

## Usage

``` r
guess_schema_location(version = eml_version())
```

## Arguments

- version:

  Optional. Override the version of the schema. Defaults to the current
  version returned by `eml_version`. See `eml_version` for information
  on how to change the current version.

## Value

Returns a string suitable as a value for `schemaLocation` or `NULL` if a
value wasn't found.

## Examples

``` r
if (FALSE) { # \dontrun{
# Get an appropriate schemaLocation value for the current version fo EML
guess_schema_location()

# Get an appropriate value for EML 2.1.1
guess_schema_location("eml-2.1.1")
} # }
```
