# Returns the Producing Units

get_producing_units returns whatever is in the metadataProvider eml
element. Set this to the producing units using the set_producing_units
function.

## Usage

``` r
get_producing_units(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a character sting

## Examples

``` r
if (FALSE) { # \dontrun{
get_producing_units(eml_object)
} # }
```
