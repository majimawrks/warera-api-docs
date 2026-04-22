# user.getUsersByCountry

Returns a paginated list of users in a given country.

## Auth
optional

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `countryId` | string | yes | Country ID. |
| `limit` | number | no | Max results. |
| `cursor` | string | no | Pagination cursor. |

## Output
- `items` — array of objects
- `items[]._id` — string
- `items[].createdAt` — string
- `nextCursor` — string

## Example request
```
GET https://api2.warera.io/trpc/user.getUsersByCountry?input={"countryId": "<countryId>","limit": 2}
```

## Example result
```json
{
  "items": [
    {
      "_id": "<userId>",
      "createdAt": "<isoTimestamp>"
    },
    {
      "_id": "<userId>",
      "createdAt": "<isoTimestamp>"
    }
  ],
  "nextCursor": "NEXTCURSOR"
}
```

## Notes
Returns `items` array and `nextCursor` for pagination.
