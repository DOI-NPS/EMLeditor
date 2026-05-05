# Returns the CUI marking

For data with controlled unclassified information (CUI),
`get_cui_marking()` eturns the specific marking and the english language
explanation of the marking. For data without CUI, it informs that there
is no CUI and returns the code "PUBLIC".

## Usage

``` r
get_cui_marking(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

String (invisibly)

## Details

CUI markings are defined by the U.S. National Archives (nara.gov). NPS
users can designate one of three CUI markings, plus the code "PUBLIC"
(essentially, no marking necessary). The three markings are: SP-NPSR,
SP-HISTP or SP-ARCHR. For more information on CUI markings, please visit
the [CUI
Markings](https://www.archives.gov/cui/registry/category-marking-list)
list maintained by the National Archives.

## Examples

``` r
if (FALSE) { # \dontrun{
get_cui_marking(eml_object)
} # }
```
