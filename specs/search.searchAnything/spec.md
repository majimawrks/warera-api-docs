# search.searchAnything

Searches across all entity types and returns arrays of matched IDs per type.

## Auth
optional (some result types may require Origin/Referer headers)

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| searchText | string | yes | — | The search query string |

## Output
Arrays of matched entity IDs grouped by entity type.

### Fields
- `userIds` — array — IDs of matching users
- `muIds` — array — IDs of matching military units
- `countryIds` — array — IDs of matching countries

## Notes
`Origin` and `Referer` headers set to `app.warera.io` are required for some result types. Authentication may expand the result set.

## Example request
```
GET https://api2.warera.io/trpc/search.searchAnything?input={"searchText":"Indonesia"}
```
