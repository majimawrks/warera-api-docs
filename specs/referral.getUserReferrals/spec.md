# referral.getUserReferrals

Returns a user's complete referral list (non-paginated).

## Auth
required

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `userId` | string | yes | User ID. |

## Output
- `items` — array of objects
- `items[].referredUserId` — string
- `items[].createdAt` — string
- `nextCursor` — string | null

## Example request
```
GET https://api2.warera.io/trpc/referral.getUserReferrals?input={"userId": "<userId>"}
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
Requires JWT cookie auth (Cookie: jwt=...). API key is not accepted. Returns an array of referred user objects.
