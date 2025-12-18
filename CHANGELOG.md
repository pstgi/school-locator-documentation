# Change Log

The list below describes the changes that have been made to the School Locator API 
and widget. The changes are grouped by version, with the latest version at the top.
Each version has a release date and a list of major changes that have been made since 
the previous version.

> For users of the widget, changes that require updating your local copy of 
the widget are tagged with `includes new widget version` below. You can ignore the
versions that are not tagged, because they add new functionality or solve problems
without the need to update your copy of the widget.

## ver.3.19.10 (2025-12-18)

- Added protection for tenants with no data to return appropriate responses.
- Include House Number Unit in matching of addresses.

## ver.3.19.9 (2025-12-03)

- Allows search of Out-of-Region addresses based on partial match.

## ver.3.19.8 (2025-11-05)

- Accommodates cloud parsing of reversed house number-unit order.

## ver.3.19.7 (2025-10-27)

- Added Locality to address search conditions.

## ver.3.19.6 (2025-10-02)

- Added handling of Location as alternative to Zone in Bulk Parsing operation.

## ver.3.19.5 (2025-09-09) `includes new widget version`

- Replaced the notices icon with an "Important message" red link.

## ver.3.19.4 (2025-09-01)

- Fixed missing messages for boards where grade IDs are not sequential.

## ver.3.19.3 (2025-08-06) `includes new widget version`

- Fixed for missing school notices in general school list.
- Fixed filtering of schools by program type and grade.

## ver.3.19.2 (2025-07-23) 

- Updated script for assigning Address GUID during Bulk Parsing operation.

## ver.3.19.1 (2025-07-10) `includes new widget version`

- Fixed initial zoom level when widget is hidden during initialization.

## ver.3.19.0 (2025-06-09)

- Added support for StreetPerfect address parsing service.

## ver 3.18.0 (2025-05-21) `includes new widget version`

- Fixed retrieval of addresses When an address is already selected and the school year is changed.

## ver 3.17.1 (2025-04-07)

- Added Postal Code City to the suggested address details, in addition to Zone.
- Added configuration check before executing a request.
- Added automated linking between query versions and seggestion endpoints.

## ver 3.17.0 (2025-04-02)

- Added support for Foreign Table versions relative to search function ones.
- Speed up notice retrieval.
- Added street name qualifier to cloud parsing.

## ver 3.16.11 (2025-03-05)

- Handles missing postal code.
- Increased Address1 size to 150 characters.
- Splits notifications for combined study areas.

## ver 3.16.10 (2025-02-27)

- Filters schools with state different than "Active".

## ver 3.16.9 (2025-02-27)

- Allows search of addresses that include apostrophe.

## ver 3.16.8 (2025-02-26)

- Removed end-dated grades from school list.

## ver 3.16.7 (2025-01-30)

- Added more information to the Ping endpoint.
- Some work on the parsing endpoints.

## ver.3.16.6 (2025-01-13)

- Converts white spaces to a single space during bulk address parsing.

## ver.3.16.6 (2025-01-13)

- Expand Parsed Address DTO to contain necessary field for Pstr fields.
- Added release date and time information to the Ping response.

## ver.3.16.5 (2025-01-06)

- Fix grade ranges when first and last grades are invisible.

## ver.3.16.4 (2024-12-19)

- Fix wrong grade ranges for some schools.

## ver.3.16.3 (2024-12-12)

- Grade low and high values returned in the list of schools show only visible grade.

## ver.3.16.2 (2024-11-19)

- Protect against null official street name values in suggested addresses.

## ver.3.16.1 (2024-11-13)

- Fixed not returning schools when at least one school offers only invisible grades.

## ver.3.16.0 (2024-11-05)

- Added bulk parsing endpoints.

## ver.3.15.0 (2024-10-17)

- Returns array of results even with bad addresses.
- Added endpoint to lookup "Out-of-Zone" addresses.

## ver.3.14.2 (2024-10-01)

- Added endpoint for looking up postal codes.

## ver.3.14.1 (2024-09-30)

- Changed bulk parsing endpoint from GET to POST.

## ver.3.14.0 (2024-09-25)

- Added endpoints for parsing addresses from a single string.
- Modified parsing result to return error message for failed ones.

## ver.3.13.7 (2024-09-20) `includes new widget version`

- Fixed top and bottom filters.

## ver.3.13.6 (2024-08-16) `includes new widget version`

- Program type selector shows if a single program type is preselected.
- Improving database reading performance.
- Optimizing reading school list by address.
- Changed address input placeholder text.

## ver.3.13.5 (2024-08-01)

- Preselect the current school year.

## ver.3.13.4 (2024-07-31)

- Replace invisible school grades with the closest ones.

## ver.3.13.3 (2024-07-30)

- Fix missing schools when one or more grades are marked as invisible.

## ver.3.13.2 (2024-07-29)

- Fixed issue where school list does not appear for some boards.
- Group grades in ranges based on GradeOrder.

## ver.3.13.1 (2024-07-11)

- Fixed issue when grade aliases do not exist for all grades.

## ver.3.13.0 (2024-07-10)

- Added settings for geographical envelope of the map at initial load.

## ver.3.12.0 (2024-07-04)

- Added support for Azure Maps

## ver.3.11.0 (2024-07-01)

- Allow authorization header parameter 'X-API-Key' as an optional name to adhere to OpenAPI 3.0.

## ver.3.10.3 (2024-07-01)

- Added original Grade Name and Grade Code to lookups, in case an alias replaces their values.

## ver.3.10.2 (2024-06-27)

- Filter school list to display only schools with study area polygons.
- Removed duplicate school years when current and next year are set the same.
- Replaced Grade Code with the Grade Alias, in addition to Grade Name.

## ver.3.10.1 (2024-06-17)

- Added study area notices to query for school list by address.

## ver.3.10.0 (2024-06-12) `includes new widget version`

- Returns only school programs in the selected scenario.
- Added grade ranges to school list end-point.
- Added endpoint to serve boundary for a given school-program-grade.
- Optimized widget code for building the distributable.
- Added school list component related functions into separate file.
- Added search for mixes addresses and schools.
- Included school location when zooming into boundary.
- Fixed program name display in school mode.
- Fixed wrong grade ranges in school list.
- Modified map behaviour for better user experience.
- Optimized widget for better performance.
- Optimized server cache.
- Added childcare phone number and website url to School Info response.

## ver.3.9.10 (2024-03-06)

- Implementation of search by postal code feature.

## ver.3.9.9 (2024-03-06)

- Added StreetPerfect postal code lookup feature.
- Change some endpoints to return Unauthorized (401) when API key is missing or invalid.
- Optimized for performance and API response time.

## ver.3.9.8 (2024-02-06)

- Fixed issue with wrong notices displayed under some schools.

## ver.3.9.7 (2024-01-10) `includes new widget version`

- Hid schools with disabled program types.

## ver.3.9.6 (2024-01-09)

- Fixed for mixed program types between tenants.

## ver.3.9.5 (2023-12-13) `includes new widget version`

- Fix for missing or null ProgramTypeGroup.

## ver.3.9.4 (2023-12-06)

- Optimized query for retrieving schools by address ID.

## ver.3.9.3 (2023-12-05)

- Fix mixing of school notices between tenants.

## ver.3.9.2 (2023-12-04) `includes new widget version`

- Added grouping and visibility of Program Types from its alias table.
- Fixed polution of override messages between tenants.

## ver.3.9.1 (2023-11-29)

- Included tenant cache reset with global one.

## ver.3.9.0 (2023-11-27) `includes new widget version`

- Added end-point to retrieve geographic envelope for a tenant.

## ver.3.8.2 (2023-11-07)

- Added filtering of program-grades by Start and End year.
- Added Study area filtering to school overrides.
- Removed empty notices from school details.

## ver.3.8.1 (2023-10-18)

- Added missing fields from School Assignment Overrides data.
- Added support for querying last batch when it is different than the active one.

## ver.3.7.0 (2023-10-11)

- Updated Entity Framework packages

## ver.3.6.2 (2023-06-26) `includes new widget version`

- UI improvements for mobile view.
- Fix for duplicate website links.
- Add activity logging for address searches by tenant.
- More improvements.

## ver.3.6.1 (2023-05-17) `includes new widget version`

- Include principal, phone number, and website URL to school details.

## ver.3.6.0 (2023-05-04) `includes new widget version`

- Remove duplicate notices in widget.
- Add attribute transfer to components.
- Performance improvements.

## ver.3.5.0 (2023-04-27) `includes new widget version`

- Add school year as parameter to queries.
- Add proper HTTP responses for failures of API requests.

## ver.3.4.0 (2023-03-06) `includes new widget version`

- Added Notices for schools, program types, grades, and study areas.
- Removed unused MessageHtml from school details.
- Filter out grades that are marked as inactive.
- Fixed drop-downs on mobile.
- Many performance improvements.
- Some small bug fixes.

## ver.3.3.0 (2023-01-17) `includes new widget version`

- Added "Get Options" button getting the LookupBaseDto content

## ver.3.2.3 (2023-01-05)

- Filter out program types with no program group definitions.

## ver.3.2.2 (2023-01-05)

- Sort school results by program.
 
## ver.3.2.1 (2022-11-30)

- Data caching and optimizations.
- Fix minor bugs.

## ver.3.2.0 (2022-11-30) `includes new widget version`

- Add extended end-points for retrieving school list and details.
- Created demo page for direct API calls.
- Removed obsolete API version 1.0.

## ver.3.1.2 (2022-10-05) `includes new widget version`

- Update query for schools by an address.

## ver.3.1.1 (2022-09-27) `includes new widget version`

- Update query for schools in a study area.

## ver.3.1.0 (2022-09-26) `includes new widget version`

- Split school records when different grades cover different study areas

## ver.3.0.0 (2022-09-12) `includes new widget version`

- Initial release
