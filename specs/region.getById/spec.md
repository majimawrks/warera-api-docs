# region.getById

Returns a region object by its ID, including ownership, production, and development data.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| regionId | string | yes | — | Unique identifier of the region |

## Output
Region object with ownership, production bonuses, deposits, and development info.

### Fields
- `_id` — string — region identifier
- `name` — string — region name
- `country` — string — countryId of the current owner
- `productionBonuses` — object — production bonus values by resource type
- `deposits` — object — deposit type and amount info
- `occupationStatus` — object — occupation state if the region is under occupation
- `developmentLevel` — number — current development level
- `taxRate` — number — current tax rate for the region

## Notes
A region may be occupied by a country different from its original owner; check `occupationStatus` for details.

## Example request
```
GET https://api2.warera.io/trpc/region.getById?input={"regionId":"abc123"}
```
