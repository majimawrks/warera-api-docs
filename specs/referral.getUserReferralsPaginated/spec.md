# referral.getUserReferralsPaginated

Returns a paginated user referral list.

## Auth
required

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `userId` | string | yes | User ID. |
| `limit` | number | no | Max results. |

## Output
- `items` — array of objects
- `items[].referredUserId` — string
- `items[].createdAt` — string
- `nextCursor` — string | null

## Example request
```
GET https://api2.warera.io/trpc/referral.getUserReferralsPaginated?input={"userId": "<userId>"}
```

## Example result
```json
{
  "items": [
    {
      "referredUserId": "<referredUserId>",
      "createdAt": "<isoTimestamp>"
    }
  ],
  "nextCursor": null
}
```

## Notes
Requires JWT cookie auth (Cookie: jwt=...). API key is not accepted. No cursor param available.
