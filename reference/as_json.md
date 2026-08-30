# Coerce an emld object into JSON

Coerce an emld object into JSON

## Usage

``` r
as_json(x, file = NULL)
```

## Arguments

- x:

  an emld object

- file:

  optional path to write out to file. Otherwise, defaults to NULL and
  will return a json object.

## Value

a json object. Or if a file path is provided, the metadata is written
out in JSON file and the function returns `NULL` invisibly.

## Details

Note: since emld list object maintains a 1:1 correspondence with JSON,
following the conventions of jsonlite, this function is basically
trivial. The only purpose is to default to auto_unbox = TRUE in
serializing lists to JSON.

## Examples

``` r
f <- system.file("extdata/example.xml", package = "emld")
emld <- as_emld(f)
json <- as_json(emld)
## can also write a json file to disk:
json_file <- tempfile()
as_json(emld, json_file)
```
