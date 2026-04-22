# battleRanking.getRanking

Returns rankings within a specific battle, grouped by entity type and side.

## Auth
optional

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `battleId` | string | yes | Battle ID. |
| `type` | string | yes | Entity type to rank within the battle. Enum: `user` \| `country` \| `mu`. |
| `side` | string | yes | Which side to return. Use 'merged' for combined rankings. Enum: `attacker` \| `defender` \| `merged`. |
| `dataType` | string | no | Metric to rank by. Default: damage. Enum: `damage` \| `points`. |

## Output
- `rankings` — array of objects
- `rankings[].user` — string
- `rankings[].value` — number
- `rankings[].rank` — number
- `rankings[]._id` — string

## Example request
```
GET https://api2.warera.io/trpc/battleRanking.getRanking?input={"battleId": "<battleId>","type": "user","side": "merged","dataType": "damage"}
```

## Example result
```json
{
  "rankings": [
    {
      "user": "<user>",
      "value": 76476,
      "rank": 1,
      "_id": "<rankingId>"
    },
    {
      "user": "<user>",
      "value": 46614,
      "rank": 2,
      "_id": "<rankingId>"
    }
  ]
}
```

## Notes
All three of battleId, type, and side are required. Previous spec was incorrect — type and side were missing.
