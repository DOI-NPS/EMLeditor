# returns the DataStore Reference ID

get_ds_id returns the DataStore Reference ID as a string of text.

## Usage

``` r
get_ds_id(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

accesses the DOI listed in the tag and trims to to the last 7 digits,
which should be identical to the DataStore Reference ID. If the tag is
empty, it notifies the user that there is no DOI associate with the
metadata and suggests adding one using set_doi() (edit_doi() would also
work).

## Examples

``` r
if (FALSE) { # \dontrun{
get_ds_id(eml_object)
} # }
```
