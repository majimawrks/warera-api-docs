# referral.getUserReferrals

Returns the non-paginated list of users referred by a given user.

## Auth
required (jwt)

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| userId | string | yes | — | Unique identifier of the user whose referrals to retrieve |

## Output
Array of referred user profile objects.

### Fields
- `[]` — object — resolved user profile for each referred user

## Notes
Requires JWT cookie authentication. May return an array or an object depending on server version. For large referral lists consider using `referral.getUserReferralsPaginated`.

## Example request
```
GET https://api2.warera.io/trpc/referral.getUserReferrals?input={"userId":"abc123"}
```
