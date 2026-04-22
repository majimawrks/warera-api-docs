# party.getById

Returns a political party profile by ID.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `partyId` | string | yes | Party ID. |

## Output
- `ethics` — object
- `ethics.militarism` — number
- `ethics.isolationism` — number
- `ethics.imperialism` — number
- `ethics.industrialism` — number
- `_id` — string
- `name` — string
- `description` — string
- `country` — string
- `region` — string
- `councilMembers` — array of strings
- `members` — array of strings
- `createdAt` — string
- `updatedAt` — string
- `__v` — number
- `avatarUrl` — string
- `primaryWinner` — string
- `treasurer` — string
- `leader` — string

## Example request
```
GET https://api2.warera.io/trpc/party.getById?input={"partyId": "<partyId>"}
```

## Example result
```json
{
  "ethics": {
    "militarism": 2,
    "isolationism": 0,
    "imperialism": -1,
    "industrialism": 0
  },
  "_id": "<partyId>",
  "name": "NAME",
  "description": "DESCRIPTION",
  "country": "<country>",
  "region": "<region>",
  "councilMembers": [
    "<councilMemberId>",
    "<councilMemberId>"
  ],
  "members": [
    "<memberId>",
    "<memberId>"
  ],
  "createdAt": "<isoTimestamp>",
  "updatedAt": "<isoTimestamp>",
  "__v": 0,
  "avatarUrl": "AVATARURL",
  "primaryWinner": "<primaryWinner>",
  "treasurer": "<treasurer>",
  "leader": "<leader>"
}
```
