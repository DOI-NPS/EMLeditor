# Creates categorical variable tables from an EML object

`get_catvar_tables` takes an EML object and returns a nested table of
all the categorical variable tables pulled from the metadata, using
EML::get_attributes()

## Usage

``` r
get_catvar_tables(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EML::read_eml(, from="xml").

## Value

a nested table with one catvar table for each data table in the EML file

## Examples

``` r
if (FALSE) { # \dontrun{
get_catvar_tables(example_EML)
} # }
```
