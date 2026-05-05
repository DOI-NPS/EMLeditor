# Set the human language used for metadata

set_language allows the user to specify the language that the metadata
(and data) were constructed in. This field is intended to hold the human
language, i.e. English, Spanish, Cherokee.

## Usage

``` r
set_language(eml_object, lang, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- lang:

  is a string consisting of the language the data and metadata were
  constructed in, for example, "English", "Spanish", "Navajo".
  Capitalization does not matter, but spelling does! The input provided
  here will be converted to 3-digit ISO 639-2 codes.

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

The English words for the language the data and metadata were
constructed in (e.g. "English") is automatically converted to the the
3-letter codes for languages listed in ISO 639-2 (available at
https://www.loc.gov/standards/iso639-2/php/code_list.php) and inserted
into the metadata.

## Examples

``` r
if (FALSE) { # \dontrun{
set_language(eml_object, "english")
set_language(eml_object, "Spanish")
set_language(eml_object, "nAvAjO")
} # }
```
