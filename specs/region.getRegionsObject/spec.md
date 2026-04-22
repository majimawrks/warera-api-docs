# region.getRegionsObject

Returns all regions as a flat object keyed by region ID.

## Auth
none

## Input
None.

## Output
- `6813b7039403bc4170a5d68a` — object
- `6813b7039403bc4170a5d68a.stats` — object
- `6813b7039403bc4170a5d68a.stats.investedMoney` — number
- `6813b7039403bc4170a5d68a.dates` — object
- `6813b7039403bc4170a5d68a.dates.lastOwnershipChangeAt` — string
- `6813b7039403bc4170a5d68a._id` — string
- `6813b7039403bc4170a5d68a.code` — string
- `6813b7039403bc4170a5d68a.country` — string
- `6813b7039403bc4170a5d68a.initialCountry` — string
- `6813b7039403bc4170a5d68a.neighbors` — array of strings
- `6813b7039403bc4170a5d68a.isCapital` — boolean
- `6813b7039403bc4170a5d68a.isLinkedToCapital` — boolean
- `6813b7039403bc4170a5d68a.upgradesV2` — object
- `6813b7039403bc4170a5d68a.upgradesV2.upgrades` — object
- `6813b7039403bc4170a5d68a.upgradesV2.activeConstructionCount` — number
- `6813b7039403bc4170a5d68a.name` — string
- `6813b7039403bc4170a5d68a.mainCity` — string
- `6813b7039403bc4170a5d68a.development` — number
- `6813b7039403bc4170a5d68a.baseDevelopment` — number
- `6813b7039403bc4170a5d68a.countryCode` — string
- `6813b7039403bc4170a5d68a.position` — array
- `6813b7039403bc4170a5d68a.biome` — string
- `6813b7039403bc4170a5d68a.climate` — string
- `6813b7039403bc4170a5d68a.__v` — number
- `6813b7039403bc4170a5d68a.resistance` — number
- `6813b7039403bc4170a5d68a.activeUpgradeLevels` — object
- `6813b7039403bc4170a5d68a.activeUpgradeLevels.bunker` — number
- `6813b7039403bc4170a5d68a.resistanceMax` — number
- `6813b7039403bc4170a5d68a.lastResistanceContributionAt` — string
- `6813b7039403bc4170a5d68a.lastRevoltEndedAt` — string
- `6813b7039403bc4170a5d68a.lastBattleEndedAt` — string
- `6813b7039403bc4170a5d6b7` — object
- `6813b7039403bc4170a5d6b7.stats` — object
- `6813b7039403bc4170a5d6b7.stats.investedMoney` — number
- `6813b7039403bc4170a5d6b7.dates` — object
- `6813b7039403bc4170a5d6b7.dates.lastOwnershipChangeAt` — string
- `6813b7039403bc4170a5d6b7._id` — string
- `6813b7039403bc4170a5d6b7.code` — string
- `6813b7039403bc4170a5d6b7.country` — string
- `6813b7039403bc4170a5d6b7.initialCountry` — string
- `6813b7039403bc4170a5d6b7.neighbors` — array of strings
- `6813b7039403bc4170a5d6b7.isCapital` — boolean
- `6813b7039403bc4170a5d6b7.isLinkedToCapital` — boolean
- `6813b7039403bc4170a5d6b7.upgradesV2` — object
- `6813b7039403bc4170a5d6b7.upgradesV2.upgrades` — object
- `6813b7039403bc4170a5d6b7.upgradesV2.activeConstructionCount` — number
- `6813b7039403bc4170a5d6b7.name` — string
- `6813b7039403bc4170a5d6b7.mainCity` — string
- `6813b7039403bc4170a5d6b7.development` — number
- `6813b7039403bc4170a5d6b7.baseDevelopment` — number
- `6813b7039403bc4170a5d6b7.countryCode` — string
- `6813b7039403bc4170a5d6b7.position` — array
- `6813b7039403bc4170a5d6b7.biome` — string
- `6813b7039403bc4170a5d6b7.climate` — string
- `6813b7039403bc4170a5d6b7.__v` — number
- `6813b7039403bc4170a5d6b7.resistance` — number
- `6813b7039403bc4170a5d6b7.activeUpgradeLevels` — object
- `6813b7039403bc4170a5d6b7.resistanceMax` — number

## Example request
```
GET https://api2.warera.io/trpc/region.getRegionsObject
```

## Example result
```json
{
  "6813b7039403bc4170a5d68a": {
    "stats": {
      "investedMoney": 0
    },
    "dates": {
      "lastOwnershipChangeAt": "<isoTimestamp>"
    },
    "_id": "<regionId>",
    "code": "ch-zurich",
    "country": "<country>",
    "initialCountry": "<initialCountry>",
    "neighbors": [
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>"
    ],
    "isCapital": false,
    "isLinkedToCapital": true,
    "upgradesV2": {
      "upgrades": {
        "base": {
          "level": 2,
          "constructionPoints": 0,
          "investedMoney": 300,
          "constructionStartedAt": "<isoTimestamp>",
          "isUnderConstruction": null,
          "lastConstructions": [],
          "status": "disabled",
          "constructionEndedAt": "<isoTimestamp>",
          "statusChangedAt": "<isoTimestamp>"
        }
      },
      "activeConstructionCount": 0
    },
    "name": "NAME",
    "mainCity": "Zurich",
    "development": 7.95,
    "baseDevelopment": 7.95,
    "countryCode": "ch",
    "position": [
      8.5417,
      47.3769
    ],
    "biome": "forest",
    "climate": "moderate",
    "__v": 29,
    "resistance": 795,
    "activeUpgradeLevels": {
      "bunker": 2
    },
    "resistanceMax": 795,
    "lastResistanceContributionAt": "<isoTimestamp>",
    "lastRevoltEndedAt": "<isoTimestamp>",
    "lastBattleEndedAt": "<isoTimestamp>"
  },
  "6813b7039403bc4170a5d6b7": {
    "stats": {
      "investedMoney": 0
    },
    "dates": {
      "lastOwnershipChangeAt": "<isoTimestamp>"
    },
    "_id": "<regionId>",
    "code": "fr-center",
    "country": "<country>",
    "initialCountry": "<initialCountry>",
    "neighbors": [
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<neighborId>",
      "<regionId>"
    ],
    "isCapital": false,
    "isLinkedToCapital": true,
    "upgradesV2": {
      "upgrades": {
        "base": {
          "level": 2,
          "constructionPoints": 0,
          "investedMoney": 300,
          "constructionStartedAt": "<isoTimestamp>",
          "isUnderConstruction": null,
          "lastConstructions": [],
          "status": "disabled",
          "constructionEndedAt": "<isoTimestamp>",
          "statusChangedAt": "<isoTimestamp>"
        },
        "bunker": {
          "level": 1,
          "constructionPoints": 0,
          "investedMoney": 100,
          "constructionStartedAt": "<isoTimestamp>",
          "isUnderConstruction": null,
          "lastConstructions": [],
          "status": "active",
          "constructionEndedAt": "<isoTimestamp>"
        }
      },
      "activeConstructionCount": 0
    },
    "name": "NAME",
    "mainCity": "Lyon",
    "development": 11.16,
    "baseDevelopment": 11.16,
    "countryCode": "fr",
    "position": [
      4.8357,
      45.764
    ],
    "biome": "plains",
    "climate": "moderate",
    "__v": 29,
    "resistance": 0,
    "activeUpgradeLevels": {},
    "resistanceMax": 1116
  }
}
```

## Notes
No params. Returns a large object (700+ entries). Each value has the same schema as region.getById output.
