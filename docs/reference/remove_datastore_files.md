# Remove files from a data package Reference on DataStore

The `remove_datastore_files()` function requires that you are logged in
to the VPN. You must also have permissions to edit the DataStore
Reference in question, and the Reference must not be activated. In that
case, `remove_datastore_files()` detaches all files associated with the
relevant DataStore Reference. Once the files are detached, they cannot
be re-attached. Instead, updated files can be re-uploaded and attached
to the reference via
[`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md).

In the interactive mode (force = FALSE), you will be informed of the
Reference number, Reference title, Reference creation date, and a list
of files currently attached to the Reference. Once the files are
successfully detached, you will be informed of a list of file names that
were detached.

Note that `remove_datastore_files()` is intended to be used with the
data package Reference type on DataStore but in theory will allow you to
remove files from ANY reference type.

## Usage

``` r
remove_datastore_files(data_store_reference, force = FALSE, dev = FALSE)
```

## Arguments

- data_store_reference:

  Integer. the 7-digit DataStore Reference number

- force:

  Logical. Defaults to FALSE. Set to TRUE to avoid interactive
  components and most user feedback.

- dev:

  Logical. Defaults to FALSE. set to TRUE if you want to detete files
  from a DataStore reference on the Development server.

## Examples

``` r
if (FALSE) { # \dontrun{
remove_datastore_files(1234567)
remove_datastore_files(1234567, force = TRUE, dev = TRUE)
} # }
```
