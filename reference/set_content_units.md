# Add Park Unit Connections to metadata

`set_content_units()` adds all specified park units and their N, E, S, W
bounding boxes to . This information will be used to fill in the Content
Unit Links field in DataStore. Invalid park unit codes will return an
error and the function will terminate. If you don't know a park unit
code, see
[`get_park_code()`](https://nationalparkservice.github.io/NPSutils/reference/get_park_code.html)
from the
[NPSutils](https://nationalparkservice.github.io/NPSutils/index.html)
package\].

## Usage

``` r
set_content_units(eml_object, park_units, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- park_units:

  a list of comma-separated strings where each string is a park unit
  code.

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

Adds the Content Unit Link(s) to a geographicCoverage. Content Unit
Links(s) are the (typically) four-letter codes describing the park
unit(s) where data were collected (e.g. ROMO, not ROMN). Each park unit
is given a separate geographicCoverage element. For each content unit
link, the unit name will be listed under geographicDescription and
prefaced with "NPS Content Unit Link:". The geographicCoverage element
will be given the attribute "system = content unit link". Required child
elements (bounding coordinates) are auto populated to produce a
rectangle that encompasses the park unit in question. If the default
force=FALSE option is retained, the user will be shown existing content
unit links (if any exist) and asked to 1) retain them 2) add to them or
3) replace them. If the force is set to TRUE, the interactive components
will be skipped and the existing content unit links will be replaced.

## Examples

``` r
if (FALSE) { # \dontrun{
park_units <- c("ROMO", "YELL")
set_content_units(eml_object, park_units)
} # }
```
