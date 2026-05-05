# Rearrange the order of creators (authors)

The `set_creator_order()` requires that your metadata contain two or
more creators. The function allows users to rearrange the order of
creators (authors on DataStore) or delete a creator.

## Usage

``` r
set_creator_order(eml_object, new_order = NA, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- new_order:

  List. Defaults to NA for interactively re-ordering the creators.

- force:

  logical. Defaults to false. If set to FALSE, a more interactive
  version of the function requesting user input and feedback. Setting
  force = TRUE facilitates scripting.

- NPS:

  Logical. Defaults to TRUE. **Most NPS users should leave this as the
  default**. Only under specific circumstances should it be set to
  FALSE: if you are **not** publishing with NPS, if you need to set the
  publisher location to some place other than the Fort Collins Office
  (e.g. you are NOT working on a data package) or your product is "for"
  the NPS but not "by" the NPS and you need to specify a different
  agency, set NPS = FALSE. When NPS=TRUE, the function will over-write
  existing publisher info and inject NPS as the publisher along the the
  Central Office in Fort Collins as the location. Additionally, it sets
  the "for or by NPS" field to TRUE and specifies the originating agency
  as NPS.

## Value

eml_object

## Examples

``` r
if (FALSE) { # \dontrun{
# fully interactive route:
meta2 <- set_creator_order(eml_object)

# specify an order in advance (reverse the order of 2 creators):
meta2 <- set_creator_order(eml_object, c(2,1))

# specify an order in advance (remove the second creator):
meta2 <- set_creator_order(eml_object, 1)

# scripting route: turn off all function feedback (you must specify the
# new creator order when you call the function; you cannot do it
# interactively):
meta2 <- set_creator_order(eml_object, c(2,1), force=TRUE)
} # }
```
