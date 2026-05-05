# returns the authors

`get_author_list()` returns a text string with all of the authors listed
under the tag.

## Usage

``` r
get_author_list(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

`get_author_list()` assumes every author has at least 1 first name
(either givenName or givenName1) and only one last name (surName).
Middle names (givenName2) are optional. The author List is formatted
with the last name, comma, first name for the first author and the fist
name, last name for all subsequent authors. The last author's name is
preceded by an 'and'.

## Examples

``` r
if (FALSE) { # \dontrun{
get_author_list(eml_object)
} # }
```
