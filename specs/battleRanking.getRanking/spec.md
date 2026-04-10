# battleRanking.getRanking

Returns a ranked list of users by damage or points for one side of a battle.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| battleId | string | yes | — | Unique identifier of the battle |
| dataType | string | no | — | Metric to rank by: damage or points |
| type | string | no | — | Entity type to rank: user |
| side | string | no | — | Side to retrieve: attacker or defender |

## Output
Ranked list of users with their metric value.

### Fields
- `rankings` — array — list of ranking entries

### Ranking entry fields
- `user` — string — userId
- `value` — number — metric value for that user

## Notes
Rankings are ordered descending by value. Currently only `type=user` is supported.

## Example request
```
GET https://api2.warera.io/trpc/battleRanking.getRanking?input={"battleId":"abc123","dataType":"damage","type":"user","side":"attacker"}
```
