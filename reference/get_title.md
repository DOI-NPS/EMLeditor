# returns the data package title

get_title returns a text string that is the title of the data package

## Usage

``` r
get_title(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

accesses all of the

tags (there can be several, if each file was given a separate title).
Assumes that the first instance of

referes to the entire data package and returns it as a text string,
ignoring the contents of all other

tags.

## Examples

``` r
if (FALSE) { # \dontrun{
get_title(eml_object)
} # }
```
