# displays file names, sizes, and descriptions

get_file_info returns a plain-text table containing file names, file
sizes, and short descriptions of the files.

## Usage

``` r
get_file_info(eml_object)
```

## Arguments

- eml_object:

  is an R object imported (typically from an EML-formatted .xml file)
  using EmL::read_eml(, from="xml").

## Value

a text string

## Details

get_file_info returns the file names (listed in the tag), the size of
the files (listed in the tag) and converts it from bytes (B) to a more
easily interpretable unit (KB, MB, GB, etc). Technically this uses
powers of 2^10 so that KB is actually a kibibyte (1024 bytes) and not a
kilobyte (1000 bytes). Similarly MB is a mebibyte not a megabyte, GB is
a gibibyte not a gigabyte, etc. But for most practical purposes this is
probably irrelevant. Finally, a short description is provided for each
file (from the tag).

## Examples

``` r
if (FALSE) { # \dontrun{
get_file_info(eml_object)
} # }
```
