# Create a template for an EML object

Create a template for an EML object

## Usage

``` r
template(object)
```

## Arguments

- object:

  the name of an eml object to create

## Value

a list with elements named according to the properties of the object.
This can be coerced into EML, see vignettes. NULL-valued elements (~)
can take a data entry directly, while empty list()-valued elements ()
indicate properties that take other eml objects as values.

## Details

Note: while this function can be called in recursions, doing so may be a
bad idea.

## Examples

``` r
template("creator")
#> individualName: {}
#> organizationName: ~
#> positionName: ~
#> address: {}
#> phone: ~
#> electronicMailAddress: ~
#> onlineUrl: ~
#> userId: ~
#> id: ~
#> system: ~
#> scope: ~
```
