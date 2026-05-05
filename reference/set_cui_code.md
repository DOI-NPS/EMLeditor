# Adds CUI dissemination codes to metadata

`set_cui_code()` adds Controlled Unclassified Information (CUI)
dissemination codes to EML metadata. These codes determine who can or
cannot have access to the data. Unless you have a specific mandate to
restrict data, all data should be available to the public. if the CUI
dissemination code is PUBLIC, the CUI marking should also be PUBLIC
(`see set_cui_marking()`) and the license should be set to CC0 or public
domain (see
[`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)).
If your data contains CUI and you need to set the CUI dissemination code
to anything other than PUBLIC, please be prepared to provide a legal
justification in the form of the appropriate CUI marking (see
[`set_cui_marking()`](https://doi-nps.github.io/EMLeditor/reference/set_cui_marking.md)).

## Usage

``` r
set_cui_code(
  eml_object,
  cui_code = c("PUBLIC", "NOCON", "DL ONLY", "FEDCON", "FED ONLY"),
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- cui_code:

  a string consisting of one of 7 potential CUI codes: PUBLIC, FED ONLY,
  FEDCON, DL ONLY, or NOCON

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

`set_cui_code()` adds a CUI dissemination code to the tag CUI under
additionalMetadata/metadata. The available choices for CUI dissemination
codes at NPS are (pay attention to the spaces!):

PUBLIC: The data contain no CUI, dissemination is not restricted. FED
ONLY: Contains CUI. Only federal employees should have access (similar
to the "internal only" setting in DataStore) FEDCON: Contains CUI Only
federal employees and federal contractors should have access to the data
(again, very similar to the DataStore "internal only" setting) DL ONLY:
Contains CUI. Should only be available to a named list of individuals.
(where and how to supply that list TBD) NOCON - Contains CUI. Federal,
state, local, or tribal employees may have access, but contractors
cannot.

For a more detailed explanation of the CUI dissemination codes, please
see the national archives [CUI Registry: Limited Dissemination
Controls](https://www.archives.gov/cui/registry/limited-dissemination)
web page.

## Examples

``` r
if (FALSE) { # \dontrun{
set_cui_dissem(eml_object, "PUBLIC")
} # }
```
