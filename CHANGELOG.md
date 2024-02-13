# Change Log

These are the changes that are parts of each version that has been released.

## v.3.9.5 (2024-02-13)

- Fix issue with duplicate school notices.

## v.3.9.4 (2023-12-06)

- Optimized query for retrieving schools by address ID.

## v.3.9.3 (2023-12-05)

- Fix mixing of school notices between tenants.

## v.3.9.2 (2023-12-04)

- Added grouping and visibility of Program Types from its alias table.
- Fixed polution of override messages between tenants.

## v.3.9.1 (2023-11-29)

- Included tenant cache reset with global one.

## v.3.9.0 (2023-11-27)

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

## v.3.6.2 (2023-06-26)

- UI improvements for mobile view.
- Fix for duplicate website links.
- Add activity logging for address searches by tenant.
- More improvements.

## v.3.6.1 (2023-05-17)

- Include principal, phone number, and website URL to school details.

## v.3.6.0 (2023-05-04)

- Remove duplicate notices in widget.
- Add attribute transfer to components.
- Performance improvements.

## v.3.5.0 (2023-04-27)

- Add school year as parameter to queries.
- Add proper HTTP responses for failures of API requests.

## v.3.4.0 (2023-03-06)

- Added Notices for schools, program types, grades, and study areas.
- Removed unused MessageHtml from school details.
- Filter out grades that are marked as inactive.
- Fixed drop-downs on mobile.
- Many performance improvements.
- Some small bug fixes.

## v.3.3.0 (2023-01-17)

- Added "Get Options" button getting the LookupBaseDto content

## v.3.2.3 (2023-01-05)

- Filter out program types with no program group definitions.

## v.3.2.2 (2023-01-05)

- Sort school results by program.

## v.3.2.1 (2022-11-30)

- Data caching and optimizations.
- Fix minor bugs.

## v.3.2.0 (2022-11-30)

- Add extended end-points for retrieving school list and details.
- Created demo page for direct API calls.
- Removed obsolete API version 1.0.

## v.3.1.2 (2022-10-05)

- Update query for schools by an address.

## v.3.1.1 (2022-09-27)

- Update query for schools in a study area.

## v.3.1.0 (2022-09-26)

- Split school records when different grades cover different study areas

## v.3.0.0 (2022-09-12)

- Initial release
