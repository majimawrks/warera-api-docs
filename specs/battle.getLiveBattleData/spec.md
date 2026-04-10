# battle.getLiveBattleData

Returns live damage, points, and timer data for a specific round of an active battle.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| battleId | string | yes | — | Unique identifier of the battle |
| roundNumber | number | yes | — | 1-indexed round number to retrieve live data for |

## Output
Live round state including damages, points, and next tick time.

### Fields
- `round` — object — live round data

### Round object fields
- `isActive` — boolean — whether the round is currently active
- `attackerDamages` — number — total damage dealt by the attacker side
- `defenderDamages` — number — total damage dealt by the defender side
- `attackerPoints` — number — attacker's current point count
- `defenderPoints` — number — defender's current point count
- `nextTickAt` — string — ISO 8601 timestamp of the next scoring tick

## Notes
Poll this endpoint to track real-time battle progress. `roundNumber` is 1-indexed.

## Example request
```
GET https://api2.warera.io/trpc/battle.getLiveBattleData?input={"battleId":"abc123","roundNumber":1}
```
