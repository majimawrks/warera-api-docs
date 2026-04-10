# mu.getById

Returns a military unit object by its ID.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| muId | string | yes | — | Unique identifier of the military unit |

## Output
Military unit object with identity and membership data.

### Fields
- `_id` — string — military unit identifier
- `name` — string — military unit name
- `country` — string — countryId the MU belongs to
- `memberCount` — number — number of members
- `meta` — object — additional MU metadata

## Notes
MU stands for military unit. Authentication may expose additional internal fields.

## Example request
```
GET https://api2.warera.io/trpc/mu.getById?input={"muId":"abc123"}
```
