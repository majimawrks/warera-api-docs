# battle.getBattles

Returns a list of battles optionally filtered by active status and country.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| isActive | boolean | no | — | Filter by active or inactive battles |
| limit | number | no | — | Maximum number of battles to return |
| countryId | string | no | — | Filter battles involving a specific country as attacker or defender |

## Output
List of battle summary objects.

### Fields
- `items` — array — list of battle summary objects, each with `_id` and associated metadata

## Notes
Each item is a battle summary. Use `battle.getById` for full detail on a specific battle.

## Example request
```
GET https://api2.warera.io/trpc/battle.getBattles?input={"isActive":true,"limit":20}
```
