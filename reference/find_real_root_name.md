# Get the real `QName` for the root element, including its prefix

Note that if a default namespace is used, the prefix will be `d1`.

## Usage

``` r
find_real_root_name(doc)
```

## Arguments

- doc:

  An `xml_document`

## Value

A `list` with elements `prefix` and `name`. `prefix` will be `NULL` if
the element has no namespace prefix but `name` will always be a
`character`.
