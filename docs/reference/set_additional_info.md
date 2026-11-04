# Set Notes for DataStore landing page

`set_additional_info()` will add information to the additionalInfo
element in EML.

## Usage

``` r
set_additional_info(eml_object, additional_info, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- additional_info:

  String. Will become the "notes" on the DataStore landing page.

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

an EML-formated R object

## Details

The contents of the additionalInformation element are used to populate
the 'notes' field on the DataStore landing page. Users may want to edit
the notes if errors or non-ASCII text characters are discovered because
the notes are prominently displayed on DataStore. To avoid non-standard
characters, users are highly encouraged to generate Notes using a text
editor such as Notepad rather than a word processor such as MS Word.

At this time, `set_additional_info()` does not support complex
formatting such as, bullets, tabs, or multiple spaces. You can add line
breaks with "\n" and a new paragraph (a blank line between text) with
"\n\n".

## Examples

``` r
if (FALSE) { # \dontrun{
eml_object <- set_additional_info(eml_object,
 "Some text for the Notes section on DataStore.")
} # }
```
