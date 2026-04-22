# ranking.getRanking

Returns a global ranking leaderboard for a specific metric.

## Auth
optional

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `rankingType` | string | yes | The ranking metric. One of: weeklyCountryDamages, weeklyCountryDamagesPerCitizen, countryRegionDiff, countryDevelopment, countryActivePopulation, countryDamages, countryWealth, countryProductionBonus, countryBounty, weeklyUserDamages, userDamages, userWealth, userLevel, userReferrals, userSubscribers, userTerrain, userPremiumMonths, userPremiumGifts, userCasesOpened, userGemsPurchased, userBounty, muWeeklyDamages, muDamages, muTerrain, muWealth, muBounty |
| `limit` | number | no | Max entries to return. |

## Output
- `_id` — string
- `type` — string
- `__v` — number
- `isGlobal` — boolean
- `items` — array of objects
- `items[].country` — string
- `items[].user` — string
- `items[].mu` — string
- `items[].value` — number
- `items[].rank` — number
- `items[].tier` — string
- `items[]._id` — string
- `tierValues` — object
- `tierValues.bronze` — number
- `tierValues.silver` — number
- `tierValues.gold` — number
- `tierValues.platinum` — number
- `tierValues.diamond` — number
- `tierValues.master` — number

## Example request
```
GET https://api2.warera.io/trpc/ranking.getRanking?input={"rankingType": "userDamages","limit": 3}
```

## Example result
```json
{
  "_id": "<rankingId>",
  "type": "userDamages",
  "__v": 0,
  "isGlobal": false,
  "items": [
    {
      "country": "<country>",
      "user": "<user>",
      "mu": "<mu>",
      "value": 143686964,
      "rank": 1,
      "tier": "master",
      "_id": "<rankingId>"
    },
    {
      "country": "<country>",
      "user": "<user>",
      "mu": "<mu>",
      "value": 142351725,
      "rank": 2,
      "tier": "master",
      "_id": "<rankingId>"
    }
  ],
  "tierValues": {
    "bronze": 40,
    "silver": 167544,
    "gold": 484581,
    "platinum": 2518835,
    "diamond": 16377781,
    "master": 46596977
  }
}
```

## Notes
CORRECTION (2026-04-22): The input field name is `rankingType` (not `type`). The enum of valid values changed from user/country/mu to 25 specific metric strings.
