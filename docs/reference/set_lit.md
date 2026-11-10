# Edit literature cited

**\[experimental\]** set_lit takes a bibtex file (\*.bib) as input and
adds it as a bibtex list to EML under citations

## Usage

``` r
set_lit(eml_object, bibtex_file, force = FALSE, NPS = TRUE)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- bibtex_file:

  is a text file with one or more bib-formatted references with the
  extension .bib. Make sure the .bib file is in your working directory,
  or supply the path to the file.

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

looks for literature cited in the tag and if it finds none, inserts
citations for each entry in the \*.bib file. If literature cited exists
it asks to either do nothing, replace the existing literature cited with
the supplied .bib file, or append additional references from the
supplied .bib file. if force=TRUE, the existing literature cited will be
replaced with the contents of the .bib file.

## Examples

``` r
if (FALSE) { # \dontrun{
eml_object <- litcited2 <- set_lit(eml_object, "bibfile.bib")
} # }
```
