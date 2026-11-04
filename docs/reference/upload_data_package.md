# Upload a data package to DataStore

`upload_data_package()` inspects a data package and, if a DOI is
supplied in the metadata, uploads the data files and metadata to the
appropriate reference on DataStore. This function requires that you are
logged on to the VPN. `upload_data_package()` will only work if each
individual file in the data package is less than 32Mb. Larger files
still require manual upload via the DataStore web interface.
`upload_data_package()` just uploads files. It does not extract EML
metadata to populate the reference fields on DataStore and it does not
activate the reference - the reference remains fully editable via the
web interface. After using `upload_data_package()` you do not need to
"save" the reference on DataStore; the files are automatically saved to
the reference.

## Usage

``` r
upload_data_package(directory = here::here(), force = FALSE, dev = FALSE)
```

## Arguments

- directory:

  the location (path) to your data package files

- force:

  logical, defaults to FALSE for a verbose interactive version. Set to
  TRUE to suppress interactions and facilitate scripting.

- dev:

  Logical. Defaults to FALSE. When dev = TRUE, all api actions are
  re-routed to the development server (as opposed to when dev = FALSE
  when api actions will target the production server).

## Value

invisible(NULL)

## Details

Currently, only .csv data files and EML metadata files are supported.
All .csvs must end in ".csv". The single metadata file must end in
"\_metadata.xml". If you have included a DOI in your metadata, using
`upload_data_package()` is preferable to using the web interface to
manually upload files because it insures that your files are uploaded to
the correct reference (i.e. the DOI in your metadata corresponds to the
draft reference code on DataStore).

Once uploaded, you are advised to look at the 'Files and Links' tab on
the DataStore web interface to make sure your files are there and you do
not have any duplicates. You can delete files as necessary from the
'Files and Links' tab until the reference is activated.

This function is primarily intended for uploading files to the data
package reference type on DataStore, but will upload .csvs and a single
EML metadata file saved as \*\_metadata.xml file to any reference type,
assuming the metadata has a DOI listed in the expected location and
there is a corresponding draft reference on DataStore.

Due to a known bug in the DataStore API, you can only use this function
to upload files once. If you need to replace files, you must do that
through the DataStore GUI.

\#' If you would like to test out the function without making uploading
to DataStore, set the parameter dev=TRUE. That will re-route all of the
API requests to the development server. You must be logged in to the VPN
to access irmadev and you must have a draft reference on the dev server
(using set_datastore_doi() with dev=TRUE).

## Examples

``` r
 if (FALSE) { # \dontrun{
dir <- here::here("..", "Downloads", "BICY")
upload_data_package(dir)
} # }
```
