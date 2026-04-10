# user.getUserLite

Returns a lite user profile object by user ID.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| userId | string | yes | — | Unique identifier of the user |

## Output
Lite user profile with identity, country, level, and account status.

### Fields
- `_id` — string — user identifier
- `username` — string — display name (also present as `login`)
- `login` — string — login name (alias for `username`)
- `country` — string — countryId the user belongs to
- `level` — number — user level
- `xp` — number — experience points (also present as `experience`)
- `experience` — number — experience points (alias for `xp`)
- `createdAt` — string — ISO 8601 account creation timestamp
- `infos` — object — nested account status info

## Notes
`username` and `login` are both present and hold the same value. `xp` and `experience` are both present and hold the same value. The `infos` object contains account status flags.

## Example request
```
GET https://api2.warera.io/trpc/user.getUserLite?input={"userId":"abc123"}
```
