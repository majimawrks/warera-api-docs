# country.getAllCountries

Returns an array of all countries with full metadata.

## Auth
none

## Input
None.

## Output
- `[].taxes` — object
- `[].taxes.income` — number
- `[].taxes.market` — number
- `[].taxes.selfWork` — number
- `[].unrest` — object
- `[].unrest.bar` — number
- `[].unrest.barMax` — number
- `[].unrest.lastContributionAt` — string
- `[]._id` — string
- `[].name` — string
- `[].code` — string
- `[].money` — number
- `[].orgs` — array of strings
- `[].allies` — array of strings
- `[].warsWith` — array of strings
- `[].scheme` — string
- `[].mapAccent` — string
- `[].__v` — number
- `[].strategicResources` — object
- `[].strategicResources.resources` — object
- `[].strategicResources.resources.diamonds` — array of strings
- `[].strategicResources.bonuses` — object
- `[].strategicResources.bonuses.productionPercent` — number
- `[].strategicResources.bonuses.developmentPercent` — number
- `[].rankings` — object
- `[].rankings.countryRegionDiff` — object
- `[].rankings.countryRegionDiff.value` — number
- `[].rankings.countryRegionDiff.rank` — number
- `[].rankings.countryRegionDiff.tier` — string
- `[].rankings.countryDamages` — object
- `[].rankings.countryDamages.value` — number
- `[].rankings.countryDamages.rank` — number
- `[].rankings.countryDamages.tier` — string
- `[].rankings.weeklyCountryDamages` — object
- `[].rankings.weeklyCountryDamages.value` — number
- `[].rankings.weeklyCountryDamages.rank` — number
- `[].rankings.weeklyCountryDamages.tier` — string
- `[].rankings.weeklyCountryDamagesPerCitizen` — object
- `[].rankings.weeklyCountryDamagesPerCitizen.value` — number
- `[].rankings.weeklyCountryDamagesPerCitizen.rank` — number
- `[].rankings.weeklyCountryDamagesPerCitizen.tier` — string
- `[].rankings.countryDevelopment` — object
- `[].rankings.countryDevelopment.value` — number
- `[].rankings.countryDevelopment.rank` — number
- `[].rankings.countryDevelopment.tier` — string
- `[].rankings.countryActivePopulation` — object
- `[].rankings.countryActivePopulation.value` — number
- `[].rankings.countryActivePopulation.rank` — number
- `[].rankings.countryActivePopulation.tier` — string
- `[].rankings.countryWealth` — object
- `[].rankings.countryWealth.value` — number
- `[].rankings.countryWealth.rank` — number
- `[].rankings.countryWealth.tier` — string
- `[].rankings.countryBounty` — object
- `[].rankings.countryBounty.value` — number
- `[].rankings.countryBounty.rank` — number
- `[].rankings.countryBounty.tier` — string
- `[].rankings.countryProductionBonus` — object
- `[].rankings.countryProductionBonus.value` — number
- `[].rankings.countryProductionBonus.rank` — number
- `[].rankings.countryProductionBonus.tier` — string
- `[].updatedAt` — string
- `[].development` — number
- `[].specializedItem` — string
- `[].enemy` — string
- `[].rulingParty` — string

## Example request
```
GET https://api2.warera.io/trpc/country.getAllCountries
```

## Example result
```json
[
  {
    "taxes": {
      "income": 1,
      "market": 1,
      "selfWork": 1
    },
    "unrest": {
      "bar": 0,
      "barMax": 1070,
      "lastContributionAt": "<isoTimestamp>"
    },
    "_id": "<countryId>",
    "name": "NAME",
    "code": "bo",
    "money": 105.05249999999995,
    "orgs": [
      "<orgId>"
    ],
    "allies": [
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>",
      "<allieId>"
    ],
    "warsWith": [
      "<warsWithId>",
      "<warsWithId>",
      "<warsWithId>",
      "<warsWithId>",
      "<warsWithId>"
    ],
    "scheme": "yellow",
    "mapAccent": "normal",
    "__v": 180,
    "strategicResources": {
      "resources": {
        "diamonds": [
          "<diamondId>"
        ]
      },
      "bonuses": {
        "productionPercent": 5,
        "developmentPercent": 5
      }
    },
    "rankings": {
      "countryRegionDiff": {
        "value": -2,
        "rank": 106,
        "tier": "silver"
      },
      "countryDamages": {
        "value": 553610959,
        "rank": 27,
        "tier": "platinum"
      },
      "weeklyCountryDamages": {
        "value": 18249014,
        "rank": 16,
        "tier": "platinum"
      },
      "weeklyCountryDamagesPerCitizen": {
        "value": 1403770.3076923077,
        "rank": 1,
        "tier": "master"
      },
      "countryDevelopment": {
        "value": 10.7,
        "rank": 65,
        "tier": "gold"
      },
      "countryActivePopulation": {
        "value": 13,
        "rank": 93,
        "tier": "silver"
      },
      "countryWealth": {
        "value": 2413.6161178092025,
        "rank": 79,
        "tier": "silver"
      },
      "countryBounty": {
        "value": 101447.3015601912,
        "rank": 14,
        "tier": "platinum"
      },
      "countryProductionBonus": {
        "value": 5,
        "rank": 28,
        "tier": "platinum"
      }
    },
    "updatedAt": "<isoTimestamp>",
    "development": 21.404795842685417,
    "specializedItem": "limestone",
    "enemy": "<enemy>",
    "rulingParty": "<rulingParty>"
  },
  {
    "taxes": {
      "income": 10,
      "market": 5,
      "selfWork": 10
    },
    "unrest": {
      "barMax": 369,
      "bar": 0,
      "lastContributionAt": "<isoTimestamp>"
    },
    "_id": "<countryId>",
    "name": "NAME",
    "code": "sg",
    "money": 182.8417000000026,
    "orgs": [
      "<orgId>"
    ],
    "allies": [
      "<allieId>",
      "<allieId>"
    ],
    "warsWith": [],
    "scheme": "red",
    "mapAccent": "light",
    "__v": 50,
    "strategicResources": {
      "resources": {
        "diamonds": [
          "<diamondId>"
        ]
      },
      "bonuses": {
        "productionPercent": 5,
        "developmentPercent": 5
      }
    },
    "rankings": {
      "countryRegionDiff": {
        "value": 0,
        "rank": 35,
        "tier": "platinum"
      },
      "countryDamages": {
        "value": 33427729,
        "rank": 116,
        "tier": "bronze"
      },
      "weeklyCountryDamages": {
        "value": 263107,
        "rank": 132,
        "tier": "bronze"
      },
      "countryDevelopment": {
        "value": 7.38,
        "rank": 82,
        "tier": "silver"
      },
      "countryActivePopulation": {
        "value": 9,
        "rank": 128,
        "tier": "bronze"
      },
      "countryWealth": {
        "value": 3778.71561905468,
        "rank": 55,
        "tier": "gold"
      },
      "countryBounty": {
        "value": 4422.523761882662,
        "rank": 94,
        "tier": "silver"
      },
      "countryProductionBonus": {
        "value": 5,
        "rank": 28,
        "tier": "platinum"
      }
    },
    "updatedAt": "<isoTimestamp>",
    "development": 7.381135189927427,
    "rulingParty": "<rulingParty>",
    "discordUrl": "https://discord.gg/hkB3ABeRM",
    "pinnedArticle": "<pinnedArticle>"
  }
]
```

## Notes
No authentication required. Returns all countries in the game world.
