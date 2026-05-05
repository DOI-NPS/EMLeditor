# returns a CUI statement

\#' **\[deprecated\]** Deprecated in favor of
[`get_cui_code()`](https://doi-nps.github.io/EMLeditor/reference/get_cui_code.md).
`get_cui()` returns an English-language translation of the CUI codes

## Usage

``` r
get_cui(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

`get_cui()` accesses the contents of the Controlled Unclassified
Information (CUI) tag, and returns an appropriate string of
english-language text based on the properties of the CUI code. If thee
tag is empty or does not exist, get_cui alerts the user and suggests
specifying CUI using the set_cui() funciton.

## Examples

``` r
if (FALSE) { # \dontrun{
get_cui(eml_object)
} # }
```
