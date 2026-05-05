# Edit data package title

Edit data package title

## Usage

``` r
set_title(eml_object, data_package_title, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- data_package_title:

  is a character string that will become the new title for the data
  package. It can be specified directly in the function call or it can
  be a previously defined object that holds a character string.

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

an EML-formatted R object

## Details

The `set_title()` function checks to see if there is an existing title
and then asks the user if they would like to change the title. Some work
is still needed on this function as `get_eml()` automatically returns
all instances of a given tag. Specifying which title will be important
for this function to work well.

## Examples

``` r
if (FALSE) { # \dontrun{
data_package_title <- "New Title. Must match DataStore Reference title."
eml_object <- set_title(eml_object, data_package_title)
} # }
```
