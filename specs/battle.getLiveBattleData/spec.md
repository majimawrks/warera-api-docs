# battle.getLiveBattleData

Returns live battle data including round scores and fighter rankings.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `battleId` | string | yes | Battle ID. |

## Output
- `battle` — object
- `battle.isActive` — boolean
- `battle.attackerCountryOrders` — array of strings
- `battle.defenderCountryOrders` — array
- `battle.roundIds` — array of strings
- `battle.roundHistory` — array
- `round` — object
- `round.roundId` — string
- `round.attackerDamages` — number
- `round.defenderDamages` — number
- `round.isActive` — boolean
- `round.actualTickPoints` — number
- `round.attackerPoints` — number
- `round.nextTickAt` — string
- `round.defenderPoints` — number

## Example request
```
GET https://api2.warera.io/trpc/battle.getLiveBattleData?input={"battleId": "<battleId>"}
```

## Example result
```json
{
  "battle": {
    "isActive": true,
    "attackerCountryOrders": [
      "<attackerCountryOrderId>"
    ],
    "defenderCountryOrders": [],
    "roundIds": [
      "<roundIdId>"
    ],
    "roundHistory": []
  },
  "round": {
    "roundId": "<roundId>",
    "attackerDamages": 236339,
    "defenderDamages": 711,
    "isActive": true,
    "actualTickPoints": 1,
    "attackerPoints": 20,
    "nextTickAt": "<isoTimestamp>",
    "defenderPoints": 0
  }
}
```

## Notes
Combine with battle.getById to build a full battle dossier.
