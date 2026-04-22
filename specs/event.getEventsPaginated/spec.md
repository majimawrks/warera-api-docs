# event.getEventsPaginated

Returns a paginated feed of in-game events.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `countryId` | string | no | Filter events by country. |
| `eventTypes` | array of strings | no | Filter by event type(s). Valid values: warDeclared, battleOpened, battleEnded, peaceMade, newPresident, regionTransfer, countryMoneyTransfer, depositDiscovered, depositDepleted, systemRevolt, bankruptcy, allianceFormed, allianceBroken, regionLiberated, strategicResourcesReshuffled, resistanceIncreased, resistanceDecreased, revolutionStarted, revolutionEnded, financedRevolt |
| `limit` | number | no | Max events per page. |
| `cursor` | string | no | Pagination cursor. |

## Output
- `items` — array of objects
- `items[]._id` — string
- `items[].countries` — array of strings
- `items[].priority` — string
- `items[].data` — object
- `items[].data.type` — string
- `items[].data.regions` — array of strings
- `items[].data.countries` — array of strings
- `items[].data.amount` — number
- `items[].createdAt` — string
- `items[].updatedAt` — string
- `items[].__v` — number
- `nextCursor` — string

## Example request
```
GET https://api2.warera.io/trpc/event.getEventsPaginated?input={"limit": 2}
```

## Example result
```json
{
  "items": [
    {
      "_id": "<eventId>",
      "countries": [
        "<countrieId>",
        "<countrieId>"
      ],
      "priority": "2",
      "data": {
        "type": "regionTransfer",
        "regions": [
          "<regionId>"
        ],
        "countries": [
          "<countrieId>",
          "<countrieId>"
        ],
        "amount": 50
      },
      "createdAt": "<isoTimestamp>",
      "updatedAt": "<isoTimestamp>",
      "__v": 0
    },
    {
      "_id": "<eventId>",
      "countries": [
        "<countrieId>",
        "<countrieId>"
      ],
      "priority": "2",
      "data": {
        "type": "allianceFormed",
        "countries": [
          "<countrieId>",
          "<countrieId>"
        ]
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
Returns `items` array and `nextCursor` for pagination.
