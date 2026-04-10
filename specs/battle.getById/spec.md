# battle.getById

Returns full battle details including round history and participant data by battle ID.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| battleId | string | yes | — | Unique identifier of the battle |

## Output
Full battle object with participant details, round history, and region information.

### Fields
- `_id` — string — battle identifier
- `type` — string — battle type
- `isBigBattle` — boolean — whether this is a big battle
- `isActive` — boolean — whether the battle is currently active
- `war` — string — associated war ID
- `roundsToWin` — number — rounds needed to win the battle
- `rounds` — array — list of round IDs
- `roundsHistory` — array — sequence of "attacker" or "defender" indicating round winners
- `attacker` — object — attacker side data
- `defender` — object — defender side data
- `region` — string — regionId being contested

### Attacker / Defender object fields
- `country` — string — countryId
- `countryOrders` — number — damage bonus from country orders
- `muOrders` — number — damage bonus from MU orders
- `moneyPer1kDamages` — number — reward per 1000 damage dealt
- `moneyPool` — number — total money pool for the side

## Notes
Both `attacker` and `defender` share the same shape.

## Example request
```
GET https://api2.warera.io/trpc/battle.getById?input={"battleId":"abc123"}
```
