# Writes attribute tables from an EML object as text files

`write_attribute_tables` is a wrapper around get_attribute_tables(). It
takes an EML object and writes one attribute table for each data table
in the EML file. It writes the attribute tables as .txt files in the
working directory or a specified path. This function is useful for
recreating metadata with EMLassemblyline, when the user doesn't have
access to the original text files.

## Usage

``` r
write_attribute_tables(eml_object, path = here::here())
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EML::read_eml(, from="xml").

- path:

  default to the working directory. This path determines where the txt
  files will be written.

## Examples

``` r
if (FALSE) { # \dontrun{
write_attribute_tables(example_EML)
} # }
```
