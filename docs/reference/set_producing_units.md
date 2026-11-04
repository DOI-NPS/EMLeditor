# Sets Producing Units for use in DataStore

set_producing_units inserts the unit code for the producing unit for the
data/metadata into the EML metdata file.

## Usage

``` r
set_producing_units(eml_object, prod_units, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- prod_units:

  A string that is the producing unit Unit Code or a list of unit codes,
  for example "ROMO" or c("ROMN", "SODN")

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

an EML object

## Details

inserts the unit code into the metadataProvider element. Currently
cannot add to existing metadataProvider fields; it will just over-write
them. It also currently only handles a single producing unit. See @param
NPS for details on sub-functions. Additionally, information about the
version of EML editor used will be injected into the metadata.

## Examples

``` r
if (FALSE) { # \dontrun{
prod_units <- c("ABCD", "EFGH")
set_producing_units(eml_object, prod_units)
set_producing_units(eml_object, c("ABCD", "EFGH"))
set_producing_units(eml_object, "ABCD", force = TRUE)
} # }
```
