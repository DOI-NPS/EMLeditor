# Adds a missing value code and definition to EML metadata

Missing data must have a missing data code and missing data code
definition. `set_missing_data()` can add a single missing value code and
single missing value code definition. Missing data should be clearly
indicated in the data with a missing data code (e.g "NA", "NaN",
"Missing", "blank" etc.). It is generally a good idea to not use special
characters for missing data codes (e.g. N/A is not advised). If it is
absolutely necessary to leave a cell empty with no code, that cell still
needs a missing value code and definition in the metadata. Acceptable
codes in this case are "empty" and "blank" with a suitable definition
that states the cells are purposefully left empty.

## Usage

``` r
set_missing_data(
  eml_object,
  files,
  columns,
  codes,
  definitions,
  force = FALSE,
  NPS = TRUE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- files:

  String or List of strings. These are the files that contain
  undocumented missing data, e.g "my_data_file1.csv".

- columns:

  String or List of strings. These are the columns with missing data for
  which you would like to add missing data codes and explanations in to
  the metadata, e.g. "scientificName".

- codes:

  String or list of strings. These are the missing value codes you would
  like associated with the column in question, e.g. "missing" or "NA".

- definitions:

  String or list of strings. These are the missing value code
  definitions associated with the missing value codes, e.g "not
  recorded" or "sample damaged when the lab flooded".

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

The `set_missing_data()` be used on an individual column or can accept
lists of files, column names, codes, and definitions. Make sure that
each missing value has a file, column, single code, and single
definition associated with it (if you need multiple missing value codes
and definitions per column, please use the `set_more_missing()`
function). If you have many missing value codes and definitions, you
might consider constructing (or import) a dataframe to describe them:

Example data frame: df \<- data.frame(files = c("table1.csv",
"table2.csv", "table3.csv", "table4.csv"), columns = c("EventDate",
"scientificName", "eventID", "decimalLatitude"), codes = c("NA", "NA",
"missing", "blank"), definitions = c("not recorded", "not identified",
"not recorded", "intentionally left blank - not recorded"))

meta2 \<- set_missing_data(eml_object = metadata, files = df\$files,
columns = df\$columns, codes = df\$codes, definitions = df\$definitions)

## Examples

``` r
if (FALSE) { # \dontrun{
#For a single column of data in a single file:
meta2 <- set_missing_data(my_metadata,
                          "table1.csv",
                          "scientificName",
                          "NA",
                          "Unable to identify")

#For multiple columns of data, potentially across multiple files:
#(blank cells must have the missing value code of "blank" or "empty")
meta2 <- set_missing_data(my_metadata,
                         files = c("table1.csv", "table1.csv", "table2.csv"),
                         columns = c("date", "time", "scientificName"),
                         codes = c("NA", "missing", "blank"),
                         definitions = c("date not recorded",
                                       "time not recorded",
                                       "intentionally left blank - missing")
                                       )
} # }
```
