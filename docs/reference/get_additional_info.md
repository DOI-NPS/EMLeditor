# Get additional information (Notes on DataStore)

`get_additional_info()` returns the text in the additionalInformation
element of EML. This text will be used to populate the "Notes" sectionon
the DataStore reference page. There is no strict limit on what can and
cannot go in to the additionalInformation/Notes section. However,
DataStore will not filter out stray characters such as &#13;. Use the
[`set_additional_info()`](https://doi-nps.github.io/EMLeditor/reference/set_additional_info.md)
function to edit and replace the text stored in the
additionalInformation (notes) field.

## Usage

``` r
get_additional_info(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

String

## Examples

``` r
if (FALSE) { # \dontrun{
get_additional_info(eml_object)
} # }
```
