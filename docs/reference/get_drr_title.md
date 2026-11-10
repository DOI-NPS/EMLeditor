# returns the title of the associated DRR

get_drr_title returns a text string with the associated Data Release
Report (DRR)'s Title.

## Usage

``` r
get_drr_title(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

get_drr_title accesses useageCitation under dataset and returns the
title element, if it is found. If it is not found, the user is warned
and pointed ot the set_drr function to add the title of the associated
DRR.

## Examples

``` r
if (FALSE) { # \dontrun{
get_drr_title(eml_object)
} # }
```
