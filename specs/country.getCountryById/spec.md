# country.getCountryById

Returns a full country object including production bonuses, government info, and economy data.

## Auth
none

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| countryId | string | yes | — | Unique identifier of the country |

## Output
Full country object with economy, government, and territorial data.

### Fields
- `_id` — string — country identifier
- `name` — string — country name
- `productionBonuses` — object — production bonus values by resource type
- `government` — object — current government and president info
- `economy` — object — economic statistics
- `regions` — array — list of region IDs belonging to this country

## Notes
No authentication required.

## Example request
```
GET https://api2.warera.io/trpc/country.getCountryById?input={"countryId":"ID"}
```
