# Change Log

The list below describes the changes that have been made to the School Locator API 
and widget. The changes are grouped by version, with the latest version at the top.
Each version has a release date and a list of major changes that have been made since 
the previous version.

> For users of the widget, changes that require updating your local copy of 
the widget are tagged with `includes new widget version` below. You can ignore the
versions that are not tagged, because they add new functionality or solve problems
without the need to update your copy of the widget.

## v.3.9.10 (2024-03-06)

- Implementation of search by postal code feature.

## v.3.9.9 (2024-03-06)

- Added StreetPerfect postal code lookup feature.
- Change some endpoints to return Unauthorized (401) when API key is missing or invalid.
- Optimized for performance and API response time.

## v.3.9.8 (2024-02-06)

- Fixed issue with wrong notices displayed under some schools.

## v.3.9.7 (2024-01-10) `includes new widget version`

- Hid schools with disabled program types.

## v.3.9.6 (2024-01-09)

- Fixed for mixed program types between tenants.

## v.3.9.5 (2023-12-13) `includes new widget version`

- Fix for missing or null ProgramTypeGroup.

## v.3.9.4 (2023-12-06)

- Optimized query for retrieving schools by address ID.

## v.3.9.3 (2023-12-05)

- Fix mixing of school notices between tenants.

## v.3.9.2 (2023-12-04) `includes new widget version`

- Added grouping and visibility of Program Types from its alias table.
- Fixed polution of override messages between tenants.

## v.3.9.1 (2023-11-29)

- Included tenant cache reset with global one.

## v.3.9.0 (2023-11-27) `includes new widget version`

- Added end-point to retrieve geographic envelope for a tenant.

## v.3.8.2 (2023-11-07)

- Added filtering of program-grades by Start and End year.
- Added Study area filtering to school overrides.
- Removed empty notices from school details.

## v.3.8.1 (2023-10-18)

- Added missing fields from School Assignment Overrides data.
- Added support for querying last batch when it is different than the active one.

## v.3.7.0 (2023-10-11)

- Updated Entity Framework packages

## v.3.6.2 (2023-06-26) `includes new widget version`

- UI improvements for mobile view.
- Fix for duplicate website links.
- Add activity logging for address searches by tenant.
- More improvements.

## v.3.6.1 (2023-05-17) `includes new widget version`

- Include principal, phone number, and website URL to school details.

## v.3.6.0 (2023-05-04) `includes new widget version`

- Remove duplicate notices in widget.
- Add attribute transfer to components.
- Performance improvements.

## v.3.5.0 (2023-04-27) `includes new widget version`

- Add school year as parameter to queries.
- Add proper HTTP responses for failures of API requests.

## v.3.4.0 (2023-03-06) `includes new widget version`

- Added Notices for schools, program types, grades, and study areas.
- Removed unused MessageHtml from school details.
- Filter out grades that are marked as inactive.
- Fixed drop-downs on mobile.
- Many performance improvements.
- Some small bug fixes.

## v.3.3.0 (2023-01-17) `includes new widget version`

- Added "Get Options" button getting the LookupBaseDto content

## v.3.2.3 (2023-01-05)

- Filter out program types with no program group definitions.

## v.3.2.2 (2023-01-05)

- Sort school results by program.
 
## v.3.2.1 (2022-11-30)

- Data caching and optimizations.
- Fix minor bugs.

## v.3.2.0 (2022-11-30) `includes new widget version`

- Add extended end-points for retrieving school list and details.
- Created demo page for direct API calls.
- Removed obsolete API version 1.0.

## v.3.1.2 (2022-10-05) `includes new widget version`

- Update query for schools by an address.

## v.3.1.1 (2022-09-27) `includes new widget version`

- Update query for schools in a study area.

## v.3.1.0 (2022-09-26) `includes new widget version`

- Split school records when different grades cover different study areas

## v.3.0.0 (2022-09-12) `includes new widget version`

- Initial release
