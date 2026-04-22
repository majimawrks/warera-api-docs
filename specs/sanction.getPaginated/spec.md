# sanction.getPaginated

Returns a paginated list of player sanctions.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `targetUserId` | string | no | Filter by sanctioned user ID. |
| `direction` | string | no | Sort direction: asc or desc. |
| `limit` | number | no | Max results. |
| `cursor` | string | no | Pagination cursor. |

## Output
- `items` — array of objects
- `items[]._id` — string
- `items[].targetUser` — string
- `items[].data` — object
- `items[].data.type` — string
- `items[].data.reason` — string
- `items[].createdAt` — string
- `items[].updatedAt` — string
- `items[].__v` — number
- `nextCursor` — string

## Example request
```
GET https://api2.warera.io/trpc/sanction.getPaginated?input={"limit": 2}
```

## Example result
```json
{
  "items": [
    {
      "_id": "<sanctionId>",
      "targetUser": "<targetUser>",
      "data": {
        "type": "UNBAN",
        "reason": "Reduced ban (Appeal)"
      },
      "createdAt": "<isoTimestamp>",
      "updatedAt": "<isoTimestamp>",
      "__v": 0
    },
    {
      "_id": "<sanctionId>",
      "targetUser": "<targetUser>",
      "data": {
        "type": "MUTE_USER",
        "durationInDays": 7,
        "unMuteAt": "<isoTimestamp>",
        "reason": "Racism."
      },
      "createdAt": "<isoTimestamp>",
      "updatedAt": "<isoTimestamp>",
      "__v": 0
    }
  ],
  "nextCursor": "NEXTCURSOR"
}
```

## Notes
No countryId filter — the API does not support filtering sanctions by country.
