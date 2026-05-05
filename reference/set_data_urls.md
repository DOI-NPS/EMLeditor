# Update (or add) data table URLs

`set_data_urls()` inspects metadata and edits the online distribution
url for each dataTable (data file) to correspond to the reference
indicated by the DOI listed in the metadata. If your data files are
stored on DataStore as part of the same reference as the data package,
you do not need to supply a URL. If your data files will be stored to a
different repository, you can supply that location.

## Usage

``` r
set_data_urls(
  eml_object,
  url = NULL,
  tag = "information",
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- url:

  a string that identifies the online location of the data file (uniform
  resource locator). Defaults to NULL for DataStore references where the
  URL will be automatically generated via the DOI in metadata.

- tag:

  a string. Must take the values of either "information" or "download".
  Defines the nature of the url being set. For direct download links use
  "download". For anything else, use "information". Defaults to
  "information" as this is the value that should be used for all
  DataStore urls.

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

`set_data_urls()` sets the online distribution URL for all dataTables
(data files in a data package) to the same URL. If you do not supply a
URL, your metadata must include a DOI (use
[`set_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_doi.md)
or
[`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
to add a DOI - these will automatically update your data table urls to
match the new DOI). `set_data_urls()` assumes that DOIs refer to digital
objects on DataStore and that the last 7 digits of the DOI correspond to
the DataStore Reference ID.

## Examples

``` r
if (FALSE) { # \dontrun{
# For data packages on DataStore, no url is necessary:
my_metadata <- set_data_urls(my_metadata)

# If data files are NOT on (or going to be on) DataStore, you must supply their location:
my_metadata <- set_data_urls(my_metadata, "https://my_custom_repository.com/data_files")} # }
```
