# referral.getUserReferralsPaginated

Returns a paginated list of users referred by a given user.

## Auth
required (jwt)

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| userId | string | yes | — | Unique identifier of the user whose referrals to retrieve |
| limit | number | no | 50 | Maximum number of referral entries to return |

## Output
Paginated referral list. Response shape varies by server version.

### Fields
- `items` — array — referral entries (present in some versions)
- `nextCursor` — string|null — cursor for the next page
- `referrals` — array — referral entries (alternative key)
- `data` — array — referral entries (alternative key)
- `users` — array — referral entries (alternative key)

## Notes
Requires JWT cookie authentication; API key is not accepted for this endpoint. Response shape may vary — check `items`, `referrals`, `data`, or `users` key for the entry list.

## Example request
```
GET https://api2.warera.io/trpc/referral.getUserReferralsPaginated?input={"userId":"abc123","limit":50}
```
