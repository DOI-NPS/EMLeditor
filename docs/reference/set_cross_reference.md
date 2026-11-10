# Add DataStore cross references to EML

This function will take one or more DataStore reference IDs, check that
each of the IDs is valid and (a real reference on DataStore) and add
them to the EML metadata object under additionalMetadata.

## Usage

``` r
set_cross_reference(
  eml_object,
  cross_ref_id,
  dev = FALSE,
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- cross_ref_id:

  String. Integer. List. One or more DataStore reference IDs to be added
  to metadata as cross-references.

- dev:

  Logical. Defaults to FALSE, meaning the function will validate user
  input based on the DataStore production server. You can set dev = TRUE
  to test the function on the development server.

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

the eml object

## Examples

``` r
if (FALSE) { # \dontrun{
set_cross_reference (eml_object = metadata, cross_ref_id = 1234567)
set_cross_reference (eml_object = metadata, cross_ref_id = c(1234567,
                                                             7654321))} # }
```
