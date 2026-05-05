# returns the DOI

returns a text string that is the DOI for the data package

## Usage

``` r
get_doi(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

`get_doi()` accesses the contents of the tag and does some text
manipulation to return a string with the DOI including the URL and
prefaced by 'doi: '.

## Examples

``` r
if (FALSE) { # \dontrun{
get_doi(eml_object)
} # }
```
