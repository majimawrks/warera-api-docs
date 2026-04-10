# user.getUsersByCountry

Returns a paginated list of users belonging to a specific country.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| countryId | string | yes | — | Unique identifier of the country |
| cursor | string | no | — | Pagination cursor returned by the previous response |
| limit | number | no | — | Maximum number of users to return |

## Output
Paginated list of lite user profiles for users in the specified country.

### Fields
- `items` — array — list of getUserLite-shaped user objects
- `nextCursor` — string|null — cursor for the next page; null when no more pages

## Notes
Each item in `items` has the same shape as the response from `user.getUserLite`.

## Example request
```
GET https://api2.warera.io/trpc/user.getUsersByCountry?input={"countryId":"ID","limit":20}
```
