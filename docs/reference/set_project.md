# Adds a reference to a DataStore Project housing the data package

The function will add a single project title and URL to the metadata
corresponding to the DataStore Project reference that the data package
should be linked to. Upon EML extraction on DataStore, the data package
will automatically be added/linked to the DataStore project
indicated.EML2.2.0 only supports a single project so `set_project()`will
overwrite/replace an existing project element.

## Usage

``` r
set_project(
  eml_object,
  project_reference_id,
  dev = FALSE,
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- project_reference_id:

  String. The 7-digit number corresponding to the Project reference ID
  that the data package should be linked to.

- dev:

  Logical. Defaults to FALSE, meaning the function will validate user
  input based on the DataStore production server. You can set dev = TRUE
  to test the function on the development server.

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

This function will overwrite existing projects. To add a DataStore
project to your metadata, the project must be publicly available. The
person uploading and extracting the EML must be an owner on both the
data package and project references in order to have the correct
permissions for DataStore to create the desired link. If you have set
NPS = TRUE and force = FALSE (the default settings), the function will
also test whether you have owner-level permissions for the project which
is necessary for DataStore to automatically connect your data package
with the project.

DataStore only add links between data packages and projects. DataStore
cannot not remove data packages from projects. If need to remove a link
between a data package and a project (perhaps you supplied the incorrect
project reference ID at first), you will need to manually remove the
connection using the DataStore web interface.

## Examples

``` r
if (FALSE) { # \dontrun{
eml_object <- set_project(eml_object,
                         1234567)
} # }
```
