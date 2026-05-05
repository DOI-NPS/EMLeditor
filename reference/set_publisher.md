# Set Publisher

set_publisher should only be used if the publisher Is **NOT the National
Park Service** or if the contact address for the publisher is NOT the
central office in Fort Collins. All data packages are published by the
Fort Collins office, regardless of where they are collected or uploaded
from. If you are working on metadata for a data package, *Do not use
this function* unless you are very sure you need to (most NPS users will
not want to use this function). If you want the publisher to be anything
other than NPS out of the Fort Collins Office, if you want the
originating agency to be something other than NPS, *or* your product is
*not* for or by the NPS, use this function. It's probably a good idea to
run args(set_publisher) to make sure you have all the arguments,
especially those with defaults, properly specified.

## Usage

``` r
set_publisher(
  eml_object,
  org_name = "NPS",
  street_address,
  city,
  state,
  zip_code,
  country,
  URL,
  email,
  ror_id,
  for_or_by_NPS = TRUE,
  force = FALSE,
  NPS = FALSE
)
```

## Arguments

- eml_object:

  is an EML-formatted R object, either generated in R or imported
  (typically from an EML-formatted .xml file) using EML::read_eml(,
  from="xml").

- org_name:

  String. The organization name that is publishing the digital product.
  Defaults to "NPS".

- street_address:

  String. The street address where the digital product is published

- city:

  String. The city where the digital product is published

- state:

  String. A two-letter code for the state where the digital product is
  being published.

- zip_code:

  String. The postal code for the publishers location.

- country:

  String. The country where the digital product is being published.

- URL:

  String. a URL for the publisher.

- email:

  String. an email for the publisher.

- ror_id:

  String. The ROR id for the publisher (see https://ror.org/ for more
  information).

- for_or_by_NPS:

  Logical. Defaults to TRUE. If your digital product is NOT for or by
  the NPS, set to FALSE.

- force:

  logical. Defaults to false. If set to FALSE, a more interactive
  version of the function requesting user input and feedback. Setting
  force = TRUE facilitates scripting.

- NPS:

  Logical. Defaults to TRUE. Set this to FALSE only if the party
  responsible for data collection and generation is *not* the NPS *or*
  the publisher is *not* the NPS central office in Fort Collins.

## Value

eml_object

## Examples

``` r
if (FALSE) { # \dontrun{
set_publisher(eml_object,
  "BroadLeaf",
  "123 First Street",
  "Second City",
  "CO",
  "12345",
  "USA",
  "https://www.organizationswebsite.com",
  "contact@myorganization.com",
  "https://ror.org/xxxxxxxxx",
  for_or_by_NPS = FALSE,
  NPS = FALSE
)
} # }
```
