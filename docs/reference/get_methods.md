# Get methods

`get_methods()` returns the text stored in the methods element of EML
metadata. The returned text is not manipulated in any way. DataStore
unlists the returned object (get rid of tags such as \$methodStep,
\$methodStep\$description and \$methodStep\$description\$para and remove
the numbers in brackets). the "\n" character combination is interpreted
as a line break (as are blank lines). However, DataStore will not filter
out stray characters such as &#13;. Use the
[`set_methods()`](https://doi-nps.github.io/EMLeditor/reference/set_methods.md)
function to edit and replace the text stored in the methods field.

## Usage

``` r
get_methods(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

List

## Examples

``` r
if (FALSE) { # \dontrun{
get_methods(eml_object)
} # }

```
