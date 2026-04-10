# country.getAllCountries

Returns an array of all countries and their basic metadata.

## Auth
none

## Input
None.

## Output
Array of country objects.

### Fields
- `[].\_id` — string — country identifier
- `[].name` — string — country name
- `[].meta` — object — additional country metadata

## Notes
No authentication required. Returns all countries in the game world.

## Example request
```
GET https://api2.warera.io/trpc/country.getAllCountries
```
