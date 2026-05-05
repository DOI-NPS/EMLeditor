# Changelog

## EMLeditor v1.2.1 (Development version)

### 2026-05-05

- Updated EML script .rmd to include package names when suggesting
  running `issues()` function.

### 2026-04-22

- Add code.json file and update links, urls, etc in preparation for DGEC
  migration

### 2026-03-05

- Update `set_cross_references` function to put more information in
  additionalMetadata and be more consistent with the way Projects are
  handled.

### 2026-03-03

- Move ISOcodes from Suggests to Imports
- Add `set_cross_references` function

## EMLeditor v1.2.0

### 2026-02-26

- Update author list
- Update DESCRIPTION to new version for API v8

### 2025-12-31

- Updated DataStore APIs to hit v8 API instead of now deprecated v7 API
  endpoints

### 2025-09-15

- Update `set_creator_orgs` to use current Unit API endpoint (and move
  away from legacy/discontinued endpoint) \## 2025-07-25
- bugfix for `set_data_urls` where giving the function a custom url
  caused it to create invalid metadata.

## EMLeditor v1.1.0

### 2025-04-14

- remove all calls to arcticdatautils package; remove arcticdatautils
  from suggests and remotes.

### 2025-04-11

- add `get_eml_simple` function and associated unit test.

### 2025-04-09

- update `set_data_urls` to set dataset urls in addition to dataTable
  urls. `set_data_urls` now adds a function = “information” tag to urls
  because they do not lead to direct file download links. It will
  overwrite all function = “download” tags added by ezEML.
- update `set_data_urls` unit tests; add test for function =
  “information”.
- update `set_data_urls` to allow custom tags only when custom urls are
  also supplied. Added unit tests to cover new code.

### 2025-03-25

- fix bug that prevented `upload_data_package` from uploading some .csv
  files.

### 2025-03-12

- fix typos in skeleton.rmd and a02_EML_creation_script.Rmd
- remove redundant `check_eml` function and update associated
  documentation
- remove `DPchecker` as a dependency from DESCRIPTION
- Update to MIT license which is JOSS, NPS, and R compatible!

### 2025-03-10

- refactor upload_data_package to not depend on
  `DPchecker::load_metadata` \## 2025-03-10
- Updated license to OSI-approved “Zero-Clause BSD” in support of JOSS
  submission.

### 2025-02-25

- Update `CONTRIBUTING.md` file \## 2025-02-22
- Add `CONTRIBUTING.md` file

### 2025-02-06

- Bug fix in `set_int_rights` that was affecting CC0 licenses.

## EMLeditor v1.0.0

### 2025-01-16

- Fix bug in `set_project` and update associated documentation.

### 2024-11-04

- Fix documentation in EMLscript code chunk that can make it
  difficult/confusing to enter user input after running the
  `upload_data_package` function.

### 2024-10-23

- updates and fixes to documentation including spelling, grammar, and
  clarity
- remove non-exported functions from documentation
- move several packages from Imports to Suggests (ISOcodes, sf, gdata)

## EMLeditor v0.1.6

### 2024-09-17

- Update `set_content_units` to have correct east and west GPS
  coordinates for bounding boxes.

### 2024-08-29

- Update readme: add R-CMD-CHECK badge; use pak to install instead of
  devtools
- Update licenseName field on restricted references to read, “Unlicensed
  (not for public dissemination)”
- add github actions: build check
- add `set_project` to the EMLscript template (.Rmd) and the github.io
  documentation pages.
- update `set_project` so that it adds projects instead of replacing
  them.
- update `set_project` to use cli errors/warnings
- add minimal unit test for `set_project`

### 2024-08-21

- add id tag to projects to help DataStore identify DataStore projects
  vs. other projects.

### 2024-08-20

- add helper.R file with a test_path function to facilitate unit tests
- update unit test code to run both interactively and during build
  checks
- add yaml file to conduct github actions: build test

### 2024-07-10

- add in the new function
  [`set_project()`](https://doi-nps.github.io/EMLeditor/reference/set_project.md)
  and attempt to update existing function,
  [`set_protocol()`](https://doi-nps.github.io/EMLeditor/reference/set_protocol.md).
- update license from MIT to CC0.

### 2024-07-02

- updated all API requests to user v6 API instead of v7.

### 2024-07-01

- Updated `.get_park_polygon()` to use the latest version of the API
  rather than a legacy version.

### 2024-06-26

- Added new function,
  [`set_new_creator()`](https://doi-nps.github.io/EMLeditor/reference/set_new_creator.md)
  which can add one or more creators to EML.

### 2024-05-01

- Fix documentation: typo/formatting for the description of
  [`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)
  in the EML Creation Script github.io page.

### 2024-04-29

- Bug fix for
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md)
  deprecation message: now points to the correct updated function
  ([`set_cui_code()`](https://doi-nps.github.io/EMLeditor/reference/set_cui_code.md)).

### 2024-04-08

- Bug fix for
  [`set_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_doi.md),
  which was not always updating dataTable URLs.

## EMLeditor v0.1.5 “Little Bighorn”

### 2024-04-01

- Fix bug in
  [`set_creator_orcids()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orcids.md):
  no longer adds <https://orcid.org/NA> for creators without an orcid.
- Added checks in
  [`set_creator_orcids()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orcids.md)
  such that users must specify NA (not “NA”) and to check that the
  length of the orcid list supplied matches the length of the authors in
  metadata (excluding organizational authors).
- Updated
  [`set_creator_orcids()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orcids.md)
  documentation to specify that the function can also be used to remove
  orcids from authors.
- Updated the EML creation script to reference
  [`set_cui_code()`](https://doi-nps.github.io/EMLeditor/reference/set_cui_code.md)
  as opposed to the (now deprecated)
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md).

### 2024-04-01

- Fix bug in
  [`set_cui_code()`](https://doi-nps.github.io/EMLeditor/reference/set_cui_code.md)
  that was detecting both CUI code and CUI marking.
- Fix bug in
  [`set_cui_marking()`](https://doi-nps.github.io/EMLeditor/reference/set_cui_marking.md).
- Fix bug in
  [`set_creator_order()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_order.md).

### 2024-03-12

- make
  [`write_readme()`](https://doi-nps.github.io/EMLeditor/reference/write_readme.md)
  a non-exported function.

### 2024-02-29

- Add function
  [`get_cui_code()`](https://doi-nps.github.io/EMLeditor/reference/get_cui_code.md).
  Deprecate function
  [`get_cui()`](https://doi-nps.github.io/EMLeditor/reference/get_cui.md).
- Add function
  [`get_cui_marking()`](https://doi-nps.github.io/EMLeditor/reference/get_cui_marking.md).

### 2024-02-22

- Added function
  [`set_missing_data()`](https://doi-nps.github.io/EMLeditor/reference/set_missing_data.md)
  which allows users to add missing data codes and missing data code
  definitions to metadata.
- Added utility functions `.get_user_input()` and `.get_user_input3()`.
  Refactored all set\_ class functions to use these sub-functions rather
  than readLines() to get user input.

### 2024-02-13

- Deprecated
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md)
  in favor of `set_cui_dissem()`, which does the exact same thing as
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md)
  but the function name has been updated to distinguish the action of
  the function from the newly added
  [`set_cui_code()`](https://doi-nps.github.io/EMLeditor/reference/set_cui_code.md)
  function.
- Updated the publisher contact email in `set_npspublisher()` from
  <irma@nps.gov> to <nrss_datastore@nps.gov> to reflect DataStore
  changes in the contact email address.

## EMLeditor v0.1.4 “Mackinac Island”

### 2024-01-18

- Added the function
  [`remove_datastore_files()`](https://doi-nps.github.io/EMLeditor/reference/remove_datastore_files.md),
  which can detach files from a DataStore Reference. In conjunction with
  [`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md)
  this allows a user to update and make changes to the files in a data
  package (for instance, in response to review of the data package)
  prior to activating the data package.

## EMLeditor v0.1.3 “Single Pen”

### 2023-11-07

- Updated EML template script to fix typos, remove the write_readme
  section, and add more explanation of the personnel.txt file.
- Updated
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
  to use the correct doi prefix when dev = TRUE and display the correct
  URL upon draft reference creation.
- Ported over most of the documentation on the EML Creation Script from
  the NPS_EML_Script repo to all be held under this repo.
- Updated documentation on making EML; updated the Readme to reflect the
  fact that all EML creation documentation/instructions are now included
  in the EMLeditor package
- Removed the “Get Started” (EMLeditor.rmd) file as it was pretty
  redundant with the readme.md file.
- Updated the template script in R studio to include package provenance
  for function calls.

## EMLeditor v0.1.2 “Mukooda Trail”

### 06 October 2023

- Updated
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
  and
  [`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md)
  functions to allow them to work with IRMA dev for testing and training
  purposes.
- Updated
  [`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md)
  to prevent file upload if the reference already has files associated
  with it.

## EMLeditor v0.1.1 “Big South Fork”

### 29 August 2023

- Updated all rest API services from v4/v5 to v6. Units services remain
  at v2.

### 15 August 2023

- Fix bugs in `get_authors()`
- Fix bugs in
  [`get_abstract()`](https://doi-nps.github.io/EMLeditor/reference/get_abstract.md)

### 19 July 2023

- Fix examples in
  [`set_creator_orgs()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orgs.md)
- Add function
  [`set_methods()`](https://doi-nps.github.io/EMLeditor/reference/set_methods.md)
  allows user to add or replace existing methods sections.
- Add function
  [`get_methods()`](https://doi-nps.github.io/EMLeditor/reference/get_methods.md)
  returns the methods section (as a list)
- Add function `set_additiona_info()` allows the user to set or replace
  existing addtitionalInfo. AdditionalInfo becomes “Notes” on the
  DataStore landing page.
- Add function
  [`get_additional_info()`](https://doi-nps.github.io/EMLeditor/reference/get_additional_info.md)
  returns the additionalInfo (“notes”) from metadata.

### 12 July 2023

- Add global variable bindings
- Fix how set_creator_orcids handles orcids; now takes a 19-char string
  as input and saves orcid as a 37-char string with
  “<https://orcid.org/>” prefix.

### 10 July 2023

- Fixed minor typos in EML creation script.

### 30 June 2023

- Added a “park_units” parameter to
  [`set_creator_orgs()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orgs.md).
  This takes a park unit (or list of park units) and uses the IRMA units
  service to populate the organizationName with the FullName of the
  park_unit specified. If you specify park_units, you cannot also
  specify “creator_orgs” - non-park unit organizations must be added as
  creators using a separate call to
  [`set_creator_orgs()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orgs.md)
  (and the creators can subsequently be reorganized using
  [`set_creator_order()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_order.md)).

### 22 June 2023

- Bug fix for
  [`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md) -
  previously it only worked if you used
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md),
  exported to .xml and then re-imported to R. Now you can go straight
  from `set_cuio()` to
  [`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md).
- Updated documentation: more information on additional functions
  available and how to use `upload_datapackage()` function
- updated the EML script template: EMLassemblyline::make_eml now does
  not write a .xml by default but instead defaults to generating an R
  object that can subsequently be processed via EMLeditor functions.

## EMLeditor v0.1.0.7 “Clingmans Dome”

### 16 June 2023

- added the function
  [`set_creator_order()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_order.md),
  which allows users to re-order the creators (authors on DataStore) as
  well as remove creators.

### 14 June 2023

- updates to the EML creation script; the make_eml() function stopped
  saving an EML object in R and was just writing a .xml to the working
  directory. Add the the arguments `return.obj = TRUE` and
  `write.file = FALSE` to get it to do the opposite: save an EML object
  to R for further processing and not write the .xml (so as not to
  create confusion later on)
- added the function
  [`set_creator_orgs()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orgs.md)
  which allows users to add organizations as creators (authors on
  DataStore). EMLassemblyline did not appear to support this
  functionality.

### 13 June 2023

- added the function
  [`set_creator_orcids()`](https://doi-nps.github.io/EMLeditor/reference/set_creator_orcids.md)
  which allows users to add or edit ORCiDs for individuals (not
  organizations) listed as creators

### 12 June 2023

- updated error messages in
  [`get_author_list()`](https://doi-nps.github.io/EMLeditor/reference/get_author_list.md)
  and
  [`get_citation()`](https://doi-nps.github.io/EMLeditor/reference/get_citation.md)
  to be more informative, especially when surName is missing from the
  creator/individualName

### 21 April 2023

- updated
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
  so that it does not prompt to use
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
  if there is no previous doi. Fixed readline prompt cursor on the wrong
  line. Now generates draft references with blank fields instead of
  place-holder strings (except for the title).

## EMLeditor v0.1.0.6 “Double Arch”

### 19 April 2023

- updated
  [`set_content_units()`](https://doi-nps.github.io/EMLeditor/reference/set_content_units.md)
  to include the attribute “system = content unit link” as part of the
  geographicCoverage element for each geographicCoverage element that is
  also a park content unit link (the old text in the field, “NPS Content
  Unit Link:” will be retained).

### 18 April 2023

- updated
  [`set_data_urls()`](https://doi-nps.github.io/EMLeditor/reference/set_data_urls.md),
  [`set_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_doi.md),
  and
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
  to handle cases when there is only one dataTable (as well as multiple
  data tables).
- updated
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md)
  to handle cases when there is no previus additionalMetadata element in
  metadata.
- updated
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md)
  and
  [`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)
  such that they can accept parameters in any case, not just upper
  ([`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md))
  or lower
  ([`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)).

### 13 April 2023

- added
  [`set_data_urls()`](https://doi-nps.github.io/EMLeditor/reference/set_data_urls.md)
  function to update dataTable urls in metadata to correspond to the DOI
  in the metadata.
- updated
  [`get_doi()`](https://doi-nps.github.io/EMLeditor/reference/get_doi.md)
  to add a line return to error message.

## EMLeditor v0.1.0.5 “Congaree Boardwalk Loop”

### 12 April 2023

- [`set_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_doi.md)
  and
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
  will now automatically update the online urls listed in the metadata
  for each data file to correspond to the new location. Caution:
  metadata with a DOI generated prior to 12 April 2023 may have
  incorrect online URLs.
- Attempt to add .Rmd template to Rstudio

### 04 April 2023

- [`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md)
  maximum file size increased to 32Mb (from 4Mb)

### 24 March 2023

- Added tryCatch to `.get_park_poygon()` to improve error handling for
  invalid park codes.
- Improved
  [`set_content_units()`](https://doi-nps.github.io/EMLeditor/reference/set_content_units.md)
  error handling to specifically test for invalid park codes prior to
  executing & report list of invalid park codes to user.
- Fixed (yet another) bug in
  [`get_content_units()`](https://doi-nps.github.io/EMLeditor/reference/get_content_units.md).

## EMLeditor v0.1.0.4 “Acadia”

### 21 March 2023

Summary

Added a new function
[`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md)
that will upload data package files to the appropriate draft reference
on DataStore. Individual files must be \< 4Mb.

#### Major changes:

- Added
  [`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md)
  that will upload data package files to the appropriate draft reference
  on DataStore. The function is only compatible with .csv data files and
  requires a single EML metadata file ending in \*\_metadata.xml to all
  be present in a single folder/directory. The metadata file must have a
  DOI specified.
  [`upload_data_package()`](https://doi-nps.github.io/EMLeditor/reference/upload_data_package.md)
  will extract the DOI from metadata and check to see if a corresponding
  reference exists on DataStore. If the reference exists, the function
  will upload each file in the data package (including the metadata
  file).

#### Minor changes

- Minor update to
  [`get_doi()`](https://doi-nps.github.io/EMLeditor/reference/get_doi.md)
  points; if DOI doesn’t exist the function now refers users to both
  [`set_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_doi.md)
  and
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md).
- Minor updates to documentation for consistency and grammar.

## EMLeditor v0.1.0.3 “Hall of Mosses”

### February 24, 2023

Summary

Added a new function,
[`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
that will initiate a draft reference on DataStore and insert the DOI
into metadata

#### Major changes:

- Added a new function, `set_datasore_doi()` that will initiate a draft
  reference on DataStore and insert the DOI into metadata. It requires
  that the user be logged on to the VPN and that the metadata has a
  title for the data package. The function will warn the user if the
  metadata already contains a DOI and will ask it they really want to
  generate a new draft reference and new DOI.

#### Minor changes

- Updated documentation to reflect the new
  [`set_datastore_doi()`](https://doi-nps.github.io/EMLeditor/reference/set_datastore_doi.md)
  function.
- Updated the
  [`get_title()`](https://doi-nps.github.io/EMLeditor/reference/get_title.md)
  and
  [`get_doi()`](https://doi-nps.github.io/EMLeditor/reference/get_doi.md)
  functions to get just the data package title and just the data package
  DOI, respectively. They had been returning multiple titles and dois if
  the
  and fields were used multiple times in the metadata.

## EMLeditor v0.1.0.2 “Devils Tower”

### February 09, 2023

#### Summary

Bug fixes, update
[`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md)
codes, flesh out `set_int_rights`. Update documentation.

#### Major changes

- replaced PUBVER and PUBFUL codes with PUBLIC in
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md).
- removed NPSONLY code from
  [`set_cui()`](https://doi-nps.github.io/EMLeditor/reference/set_cui.md).
- major bug fixes to
  [`set_content_units()`](https://doi-nps.github.io/EMLeditor/reference/set_content_units.md).
- updated
  [`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)
  to also populate licenseName field.

#### Minor changes

- fixed minor typos in documentation
- moved
  [`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)
  from “additional functions” to “minimal workflow”

## EMLeditor v0.1.0.1 “Whitebark Pine”

### January 24, 2023

#### Summary

Added `check_eml()` function.

#### Major changes

`check_eml()` function is a wrapper that calls
`DPchecker::run_congruence_checks()` with `check_metadata-only = TRUE`.
To run all the metadata-specific tests that will be run during a
congruence test.

#### Minor changes

- specify ISO 639-2B in
  [`set_language()`](https://doi-nps.github.io/EMLeditor/reference/set_language.md)
- added documentation for `check_eml()`
- Changed Non-NPS user section to more apt, “Custom Publisher/Producer”
- added a “Additional Functions” section in addition to the Minimal
  Workflow that outlines functions like
  [`set_title()`](https://doi-nps.github.io/EMLeditor/reference/set_title.md),
  [`set_abstract()`](https://doi-nps.github.io/EMLeditor/reference/set_abstract.md)
  and
  [`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md).
- moved
  [`write_readme()`](https://doi-nps.github.io/EMLeditor/reference/write_readme.md)
  and the new `check_eml()` to the file check_eml.R.

------------------------------------------------------------------------

## EMLeditor v0.1.0.0, “Electric Peak”

### December 1, 2022

#### Summary

Added
[`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)
function.

#### Major Changes

[`set_int_rights()`](https://doi-nps.github.io/EMLeditor/reference/set_int_rights.md)
allows users to update the intellectual rights text supplied by 3rd
party EML generators with one of 3 NPS-specific options. Enforces
congruence between CUI and license.

------------------------------------------------------------------------

### November, 2022

#### Summary

Updating to v0.1.0.0 “Electric Peak” is recommended for all users in
order to take full advantage of metadata/DataStore integration included
the most up-to-date locations and specifications for DataStore metadata
elements.

#### Major Changes

1.  The ability to switch “set\_” class functions from a verbose (asks
    user for input, provides feedback) to silent (no feedback, no
    prompts) to enable scripting.

2.  Inclusion of set_publisher function to customize the publisher and
    agencyOriginated options for non-NPS users, for NPS partners and
    contractors.

#### Enhancements

1.  CUI can now be overwritten as well as written

2.  write_readme dynamically populates publisher information

3.  Renamed functions and parameters to conform to tidyverse style
    guides

4.  Removed redundant functions (set_doi)

5.  Added ability to set DRR title and DOI

6.  write_readme now defaults to printing to the screen (but can still
    save to a .txt file)

7.  Update documentation to reflect changes

#### Bug Fixes

Let’s just leave this at “a lot”.

------------------------------------------------------------------------

## EMLeditor 0.0.1.1

- Added a `NEWS.md` file to track changes to the package.
