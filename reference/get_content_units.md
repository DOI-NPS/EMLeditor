# returns the park unit connections

returns a string with the park unit codes where the data were collected

## Usage

``` r
get_content_units(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

`get_content_units()` accesses the contents of the tags and returns the
contents of the tag that contains the text "NPS Unit Connections". If
there is no , it alerts the user and suggests adding park unit
connections using the set_park_units() function.

## Examples

``` r
if (FALSE) { # \dontrun{
get_content_units(eml_object)
} # }
```
