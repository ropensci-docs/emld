# Set or check the EML version default

Set or check the EML version default

## Usage

``` r
eml_version(version = getOption("emld_db", "eml-2.2.0"))
```

## Arguments

- version:

  EML version, currently either eml-2.2.0 (current version), or
  eml-2.1.1. The 'eml-' prefix can be omitted.

## Value

returns the EML version string. As a side-effect, sets the requested
version as the default version by setting the `emld_db` variable in
[`options()`](https://rdrr.io/r/base/options.html).

## Examples

``` r
eml_version()
#> [1] "eml-2.2.0"
eml_version("2.1.1")
#> [1] "eml-2.1.1"
eml_version("eml-2.1.1")
#> [1] "eml-2.1.1"
```
