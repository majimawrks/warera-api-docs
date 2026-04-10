# party.getById

Returns a political party object by its ID.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| partyId | string | yes | — | Unique identifier of the political party |

## Output
Political party object with identity, country, and membership data.

### Fields
- `_id` — string — party identifier
- `name` — string — party name
- `country` — string — countryId the party belongs to
- `ethicsBonus` — number — ethics bonus provided by the party
- `members` — object — member count and related membership info

## Notes
Authentication may expose additional internal fields.

## Example request
```
GET https://api2.warera.io/trpc/party.getById?input={"partyId":"abc123"}
```
