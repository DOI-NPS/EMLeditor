# Adds a connection to the protocol under which the data were collected

**\[experimental\]** This function is currently under development. If
you use it, it will break your EML. You've been warned.

set_protocol adds a metadata link to the protocol under which the data
being described were collected. It automatically inserts a link to the
DataStore landing page for the protocol as well as the protocol title
and creator.

## Usage

``` r
set_protocol(eml_object, protocol_id, dev = FALSE, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- protocol_id:

  a string. The 7-digit number identifying the DataStore reference
  number for the Project that describes your inventory or monitoring
  project.

- dev:

  Logical. Defaults to FALSE, meaning all API calls will be to the
  production version of DataStore. To test the function, set dev = TRUE
  to use the development environment for DataStore.

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

## Details

Because protocols can be published to DataStore using a number of
different reference types, set_protocol does not check to make sure you
are actually supplying a the reference ID for a protocol (or the correct
protocol).

## Examples

``` r
if (FALSE) { # \dontrun{
set_protocol(eml_object, 2222140)
} # }
```
