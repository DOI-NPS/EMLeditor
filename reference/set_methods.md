# Sets the Methods in metadata

`set_methods()` will check for and add/replace methods in the metadata

## Usage

``` r
set_methods(eml_object, method, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- method:

  String. A string of text describing the study methods.

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

An EML-formatted object

## Details

Users may want to edit the methods if errors or non-ASCII text
characters are discovered because the methods are prominently displayed
on DataStore. To avoid non-standard characters, users are highly
encouraged to generate methods using a text editor such as Notepad
rather than a word processor such as MS Word.

At this time, `set_methods()` does not support complex formatting such
as, bullets, tabs, or multiple spaces. All text will be included in a
description element (which is itself a child element of a single
methodStep element within the methods element). Additional child elments
of methods or methodStep such as subStep, software, instrumentation,
citation, sampling, etc are not supported at this time. All of this
information may be added as text. You can add line breaks with "\n" and
a new paragraph (a blank line between text) with "\n\n".

## Examples

``` r
if (FALSE) { # \dontrun{
eml_object <- set_methods(eml_object, "Here are some methods we performed.")
} # }
```
