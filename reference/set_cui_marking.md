# The function sets the CUI marking for the data package

**\[experimental\]** The Controlled Unclassified Information (CUI)
marking is different from the CUI dissemination code. The CUI
dissemination code (set
[`set_cui_code()`](https://doi-nps.github.io/EMLeditor/reference/set_cui_code.md))
sets who can have access to the data package. The CUI marking set by
`set_cui_marking()` specifies the reason (if any) that the data are
being restricted. If the CUI dissemination code is set to PUBLIC, the
CUI marking must also be PUBLIC. If the CUI dissemination code is set to
anything other than PUBLIC, the CUI marking must be set to SP-NPSR,
SP-HISTP or SP-ARCHR.

## Usage

``` r
set_cui_marking(
  eml_object,
  cui_marking = c("PUBLIC", "SP-NPSR", "SP-HISTP", "SP-ARCHR"),
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- cui_marking:

  String. One of four options, "PUBLIC", "SP-NPSR", "SP-HISTP" or
  "SP-ARCHR" are available.

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

CUI markings are the legal justification for why data are being
restricted from the public. If data contain no CUI, the CUI marking must
be set to PUBLIC (and the CUI dissemination code must be set to PUBLIC
and the license must be set to CC0 or Public Domain). If the data
contain CUI (i.e. the CUI dissemination code is not PUBLIC), you must
use the CUI marking to provide a legal justification for why the data
are restricted. Only one CUI marking can be applied. At NPS, the
following markings are available:

PUBLIC: The data contain no CUI, dissemination is not restricted.
SP-NPSR: "National Park System Resources" - This material contains
information concerning the nature and specific location of a National
Park System resource that is endangered, threatened, rare, or
commercially valuable, of mineral or paleontological objects within
System units, or of objects of cultural patrimony within System units.
SP-HISTP: "Historic Properties" - This material contains information
related to the location, character, or ownership of historic property.
SP-ARCHR: "Archaeological Resources" - This material contains
information related to information about the nature and location of any
archaeological resource for which the excavation or removal requires a
permit or other permission.

For more information on CUI markings, please visit the [CUI
Markings](https://www.archives.gov/cui/registry/category-marking-list)
list maintained by the National Archives.

## Examples

``` r
if (FALSE) { # \dontrun{
eml_object <- set_cui_marking(eml_object, "PUBLIC")
} # }
```
