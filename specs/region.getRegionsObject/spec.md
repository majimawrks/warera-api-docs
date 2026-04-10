# region.getRegionsObject

Returns all regions as a map keyed by regionId, including production bonuses and country assignments.

## Auth
optional

## Input
None.

## Output
Object keyed by regionId mapping to region data.

### Fields
- `<regionId>` — object — region data including `country` and `productionBonuses` fields

## Notes
Useful for bulk access to region data without individual lookups. Each value has at minimum `country` and `productionBonuses` fields.

## Example request
```
GET https://api2.warera.io/trpc/region.getRegionsObject
```
