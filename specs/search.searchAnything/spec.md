# search.searchAnything

Searches across all entity types: users, MUs, countries, regions, and parties.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `searchText` | string | yes | Search query. NOTE: the param name is `searchText`, not `query`. |

## Output
- `userIds` — array of strings
- `muIds` — array
- `countryIds` — array
- `regionIds` — array
- `partyIds` — array
- `hasData` — boolean

## Example request
```
GET https://api2.warera.io/trpc/search.searchAnything?input={"searchText": "warera"}
```

## Example result
```json
{
  "userIds": [
    "<userIdId>",
    "<userIdId>"
  ],
  "muIds": [],
  "countryIds": [],
  "regionIds": [],
  "partyIds": [],
  "hasData": true
}
```

## Notes
CORRECTION: param name is `searchText` (not `query`). Response has 6 fields — original spec only documented 3.
