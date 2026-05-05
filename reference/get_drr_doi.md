# returns the DOI of the associated DRR

get_drr_doi returns a text string with the associated Data Release
Report (DRR)'s DOI.

## Usage

``` r
get_drr_doi(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

get_drr_doi accesses the tag(s) and searches an alternateIdentifier tag.
If that element is found, the contents of that element are returned. If
the title element is empty or not present, the user is warned and
pointed to the set_drr function to add the DOI of an associated DRR.

## Examples

``` r
if (FALSE) { # \dontrun{
get_drr_doi(eml_object)
} # }
```
