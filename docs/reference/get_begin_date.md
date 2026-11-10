# returns the first date

get_begin_date returns the date of the earliest data point in the data
package

## Usage

``` r
get_begin_date(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

returns the date from the tag. Although dates should be formatted
according to ISO-8601 (YYYY-MM-DD) it will also check for a few other
common formats and return the date as a text string: "DD Month YYYY"

## Examples

``` r
if (FALSE) { # \dontrun{
get_begin_date(eml_object)
} # }
```
