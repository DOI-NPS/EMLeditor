# Adds information about file access permission levels.

These permissions are only for file download access (including the EML
metadata in .xml format). The actual reference landing page will not be
restricted. For more information on CUI markings, please visit the [CUI
Markings](https://www.archives.gov/cui/registry/category-marking-list)
list maintained by the National Archives. For a list of legal
authorities, use
[`NPSdatastore::get_legal_authority`](https://rdrr.io/pkg/NPSdatastore/man/get_legal_authority.html).

## Usage

``` r
set_permissions(
  eml_object,
  access = c("PUBLIC", "RESTRICTED", "INTERNAL"),
  legal_authority_id = NULL,
  contact_email = NULL,
  authority_designator = NULL,
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- access:

  String. one of either "PUBLIC", "RESTRICTED", or "INTERNAL".

- legal_authority_id:

  Integer. Defaults to NULL for PUBLIC access. for RESTRICTED or
  INTERNAL, legal_authority must be set to a number between 1 and 31
  that corresponds to the legal authority in DataStore. Use
  [`NPSdatastore::get_legal_authority`](https://rdrr.io/pkg/NPSdatastore/man/get_legal_authority.html)
  to generate a list along with definitions.

- contact_email:

  String. Defaults to NULL for PUBLIC access. for RESTRICTED or
  INTERNAL, an email address must be supplied. It will be used to
  request more information about a restricted source. It is suggested
  that this be a group email rather than an individual due to potential
  staff turnover.

- authority_designator:

  String. Defaults to NULL for PUBLIC access. for RESTRICTED or
  INTERNAL, the name of the person who is responsible for restricting
  the files attached to the reference.

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

The details for the data package restriction (or public access),
including the reason, the level, and the CUI code and links to relevant
documentation, email addresses for contact and a person responsible for
the decision will all be populated in a dedicated additionalMetadata
element. The access module will be populated with a minimal schema valid
information describing access levels.

## Examples

``` r
if (FALSE) { # \dontrun{
eml_object <- set_permissions(eml_object, "PUBLIC")
} # }
```
