# ranking.getRanking

Returns the global leaderboard for users, countries, or military units.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| type | string | yes | — | Entity type to rank: user, country, or mu |
| limit | number | no | — | Maximum number of entries to return |

## Output
Ranked list of entities with their scores.

### Fields
- `rankings` — array — list of ranking entries

### Ranking entry fields
- `id` — string — entity identifier
- `name` — string — display name
- `value` — number — score value
- `rank` — number — 1-indexed position in the leaderboard

## Notes
Use `type=user` for player rankings, `type=country` for national rankings, or `type=mu` for military unit rankings.

## Example request
```
GET https://api2.warera.io/trpc/ranking.getRanking?input={"type":"user","limit":50}
```
