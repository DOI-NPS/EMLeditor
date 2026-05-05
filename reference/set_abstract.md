# adds an abstract

`set_abstract()` adds (or replaces) a simple abstract.

## Usage

``` r
set_abstract(eml_object, abstract, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- abstract:

  is a text string that is your abstract. You can generate this directly
  in R or import a .txt file.

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

Checks for an abstract. If no abstract is found, it inserts the abstract
given in @param abstract. If an existing abstract is found, the user is
asked whether they want to replace it or not and the appropriate action
is taken. Currently set_abstract does not allow for complex formatting
such as bullets, tabs, or multiple spaces. You can add line breaks with
"\n" and a new paragraph (blank line between text) with "\n\n". You are
strongly encouraged to open your abstract in a text editor such as
notepad and make sure there are no stray characters. If you need
multiple paragraphs, you will need to do that via EMLassemblyline (for
now).

## Examples

``` r
if (FALSE) { # \dontrun{
eml_object <- set_abstract(eml_object, "This is a very short abstract")
} # }
```
