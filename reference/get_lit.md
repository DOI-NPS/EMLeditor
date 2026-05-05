# Get literature cited

get_lit prints bibtex fromated literature cited to the screen.

## Usage

``` r
get_lit(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

character string

## Details

get_lit currently only supports bibtex formatted references. get_lit
gets items from the tag and prints them to the screen.

## Examples

``` r
if (FALSE) { # \dontrun{
get_lit(eml_object)
} # }
```
