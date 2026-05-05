# returns the data package citation

returns a Chicago manual of style citation for the data package

## Usage

``` r
get_citation(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

get_citation allows the user to preview the what the citation will look
like. The Harper's Ferry Style Guide recommends using the Chicago Manual
of Style for formatting citations. The citation is formatted according
to to a modified version of the Chicago Manual of Style's Author-Date
journal article format because currently there is no Chicago Manual of
Style format specified for datasets or data packages. In compliance with
DataCite's recommendations regarding including DOIs in citations, the
citation displays the entire DOI as
https://www.doi.org/10.58370/xxxxxx".

## Examples

``` r
if (FALSE) { # \dontrun{
get_citation(eml_object)
} # }
```
