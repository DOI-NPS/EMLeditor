# Returns a simple list of eml elements

This function wraps EML::get_eml and returns the requested object in a
much simpler format. It works best with eml elements that do not have
child elements.

## Usage

``` r
get_eml_simple(eml_object, eml_element)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

- eml_element:

  is a string indicating the element within the eml_object that should
  be accessed and returned.

## Value

a list of values

## Examples

``` r
if (FALSE) { # \dontrun{
get_eml_simple(eml_object, "geographicDescription")
} # }
```
