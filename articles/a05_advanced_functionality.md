# Advanced Functionality

The default settings on EMLeditor functions are designed to make the
user experience as simple and transparent as possible. This means
EMLeditor does a lot of things behind the scenes (such as automatically
inserts the version of EMLeditor your used into metadata, automatically
inserts publisher information, and assumes that the data package is
created “by or for” the NPS). Advanced users may want to disable some of
these settings or take advantage of advanced functionality.

## Test functions on irmadev

Several of the EMLeditor functions allow you to write to DataStore
([`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md),
[`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md),
etc). By default these functions will write to the production (i.e
“public”) version of DataStore. However, if you want to test your
scripts, you can set these functions to write to the development version
of DataStore (irmadev):

Test putting a draft reference on irmadev:

``` r

set_datastore_doi(metadata, dev = TRUE)
```

Test uploading your data package to irmadev:

``` r

upload_data_package(dev = TRUE)
```

Note that you must be signed in to the VPN to be able to view your
reference and uploaded files on irmadev.

## Scripting with EMLeditor

The interactive feedback and prompts provided by EMLeditor functions can
be turned off to enable efficient scripting. All “set\_” class functions
have a parameter, force that defaults to force = FALSE. To turn off the
feedback and prompts, set force = TRUE when calling each function. Be
careful using the functions in this way as they may - or may not - make
changes to your metadata and you will not be advised of any change or
lack of change. Inspect your final product carefully.

``` r

metadata <- set_title(metadata, "My new title", force = TRUE)
```

## Custom Publisher/Producer

EMLeditor functions are designed primarily for use by staff at the
National Park Service for publication of data packages to DataStore.
Consequently, all “set\_” class functions silently perform two
operations by default:

1.  They set the publisher to the National Park Service (and the
    location to the Fort Collins office)
2.  They specify the agency that created the data package as NPS and set
    a field “by or for NPS” to TRUE

You can prevent set_class functions from performing these operations by
changing the default status of the parameter NPS = TRUE to NPS = FALSE.
This will leave your publisher information untouched and will not create
an additionalMetadata item for the agency that created the data package.

If you would like to set the publisher to something other than the Fort
Collins Office of the National Park Service or your would like to set
the agency that created the data package to something other than NPS,
use the
[`set_publisher()`](https://doi-nps.github.io/EMLeditor/reference/set_publisher.md)
function. Be sure to specify `NPS = FALSE` or the function will perform
the default operations (set publisher to NPS at the Fort Collins Office
and set the agency to NPS).

Warning:
[`set_publisher()`](https://doi-nps.github.io/EMLeditor/reference/set_publisher.md)
should only be used in a few, likely rare, circumstances:

1.  If the publisher Is NOT the National Park Service
2.  If the contact address for the publisher is NOT the central office
    in Fort Collins (all data packages uploaded to DataStore will be
    published by the Fort Collins Office of NPS)
3.  If the originating agency is NOT the NPS (i.e. a contractor or
    partner organization)
4.  If the data package is NOT created for or by the NPS

It’s probably a good idea to take a look at all the arguments you need
to supply to the
[`set_publisher()`](https://doi-nps.github.io/EMLeditor/reference/set_publisher.md)
function prior to using it:

``` r

args(set_publisher)
#function (eml_object, org_name = "NPS", street_address, 
#    city, state, zip_code, country, URL, email, ror_id, for_or_by_NPS = TRUE, 
#    force = FALSE, NPS = FALSE) 
```

You can then add any custom publisher you would like:

``` r

metadata <- set_publisher(metadata, org_name = "Broadleaf",
                          street_address = "1234 Strasse St.",
                          city = "Metropolis",
                          State = "Denial",
                          zip_code = "12345",
                          country = "The Wild, Wild West",
                          URL = "https://error404.com", 
                          email = "gesundheit@krankenhaus.de",
                          ror_id = "NA",
                          for_or_by_NPS = FALSE,
                          force = FALSE,
                          NPS = FALSE)
```

If you use any “set\_” class functions in their default settings after
setting your custom publisher, they will overwrite your custom
publisher! Make sure to include the parameter `NPS = FALSE` if you
invoke any additional “set\_” functions:

``` r

metadata <- set_additional_info(metadata,
                                "Info for the Notes section on DataStore",
                                NPS = FALSE)
```

## View all functions

A comprehensive list of all available EMLeditor functions can be found
via the
[Reference](https://doi-nps.github.io/EMLeditor/reference/index.md) tab
at the top of the web page. Click on each function to read the
associated documentation.
