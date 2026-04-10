# sanction.getPaginated

Returns a paginated list of sanctions, optionally filtered by target user.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| targetUserId | string | no | — | Filter sanctions by the sanctioned user's ID |
| limit | number | no | 100 | Maximum number of sanctions to return |
| direction | string | no | — | Pagination direction: forward or backward |

## Output
Paginated list of sanction records and a cursor for the next page.

### Fields
- `items` — array — list of Sanction objects
- `nextCursor` — string|null — cursor for the next page; null when no more pages

### Sanction object fields
- `data` — object — sanction details
  - `type` — string — sanction type (e.g. `"BAN"`)
  - `reason` — string — reason for the sanction
- (additional metadata fields may be present)

## Notes
The `direction` parameter controls cursor traversal order (forward or backward through the result set).

## Example request
```
GET https://api2.warera.io/trpc/sanction.getPaginated?input={"targetUserId":"abc123","limit":100,"direction":"forward"}
```
