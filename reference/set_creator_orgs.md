# Add an organization as a creator to metadata (author in DataStore)

`set_creator_orgs()` allows a user to add an organization as a creator
to metadata. EMLassemblyline can link an individual person who is a
creator to the organization they are associated with, but currently does
not allow organizations themselves to be listed as creators.
`set_creator_orgs()` takes a list of organizations (and their RORs, if
they have them) and appends them to the end of the creator list. This
allows organizations (such as a Network or a Park) to author data
packages.

## Usage

``` r
set_creator_orgs(
  eml_object,
  creator_orgs = NA,
  park_units = NA,
  RORs = NA,
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- creator_orgs:

  List. Defaults to NA. A list of one or more organizations.

- park_units:

  List. Defaults to NA. A list of park units. If any park units are
  specified, it they will supersede anything listed under creator_orgs.

- RORs:

  List. Defaults to NA. An optional list of one or more ROR IDs (see
  <https://ror.org>) that correspond to the organization in question. If
  an organization does not have a ROR ID (or you don't know it), enter
  "NA".

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

because `set_creator_orgs()` merely appends organizations, it 1) assumes
that there is already one creator (as required by EMLassemblyline) and
2) does not allow the user to change authorship order. To change the
order of the authors, see
[`set_creator_order()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_order.md).
Creator organizations and their RORs need to be supplied in two lists
where the organization and ROR are correctly matched (i.e. the 3rd
organization is associated with the 3rd ROR in a list). If one or more
of your creator organizations does not have a ROR, enter "NA".

You can use the park_units parameter to specify park units. This will
utilize the IRMA units look-up service to fill in the organizationName
element, thus ensuring that there are no spelling errors or deviations
unit names. You can use either park_units or creator_orgs but not both
because if you have specified any park_units, these will over-write the
creator_orgs in your function call. Thus, if you would like to add park
units as creators and some non-park unit organization as a creator you
need to call the function twice. When specifying park_units, they will
be added in the order they occur in the IRMA units list, not necessarily
the order they were supplied to the function. Use
[`set_creator_order()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_order.md)
to re-order them if desired.

## Examples

``` r
 if (FALSE) { # \dontrun{
 #add one organization and it's ROR:
 mymetadata <- set_creator_orgs(mymetadata, "National Park Service", RORs="044zqqy65")

 #add one organization that does not have a ROR:
 mymetadata <- set_creator_orgs(mymetadata, "My Favorite ROR-less Organization")

 #add multiple organizations, some of which do not have RORs:
 my_orgs <- c("National Park Service", "My Favorite ROR-less Organization")
 my_RORs <- c("044zqqy65", "NA")

 mymetadata <- set_creator_orgs(mymetadata, my_orgs, RORs=my_RORs)

 #add multiple park units as organization names:
 park_units <- c("ROMN", "SFCN", "YELL")

 mymetadata <- set_creator_orgs(mymetadata, park_units=park_units)

 } # }
```
