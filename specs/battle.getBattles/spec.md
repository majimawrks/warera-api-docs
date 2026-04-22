# battle.getBattles

Returns a paginated list of battles, optionally filtered by country or active status.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `countryId` | string | no | Filter by country ID. |
| `isActive` | boolean | no | If true, return only active battles. |
| `limit` | number | no | Max results. |

## Output
- `items` — array of objects
- `items[].defender` — object
- `items[].defender.region` — string
- `items[].defender.country` — string
- `items[].defender.wonRoundsCount` — number
- `items[].defender.countryOrders` — array
- `items[].defender.muOrders` — array
- `items[].defender.damages` — number
- `items[].defender.hitCount` — number
- `items[].attacker` — object
- `items[].attacker.region` — string
- `items[].attacker.country` — string
- `items[].attacker.wonRoundsCount` — number
- `items[].attacker.countryOrders` — array of strings
- `items[].attacker.muOrders` — array of strings
- `items[].attacker.damages` — number
- `items[].attacker.hitCount` — number
- `items[].stats` — object
- `items[].stats.hitCount` — number
- `items[]._id` — string
- `items[].war` — string
- `items[].type` — string
- `items[].rounds` — array of strings
- `items[].roundsHistory` — array
- `items[].isActive` — boolean
- `items[].roundsToWin` — number
- `items[].createdAt` — string
- `items[].updatedAt` — string
- `items[].__v` — number
- `items[].currentRound` — object
- `items[].currentRound.attacker` — object
- `items[].currentRound.defender` — object
- `items[].currentRound.live` — object
- `items[].currentRound._id` — string
- `items[].currentRound.battle` — string
- `items[].currentRound.number` — number
- `items[].currentRound.isActive` — boolean
- `items[].currentRound.createdAt` — string
- `items[].currentRound.updatedAt` — string
- `items[].currentRound.__v` — number
- `nextCursor` — string

## Example request
```
GET https://api2.warera.io/trpc/battle.getBattles?input={"limit": 2}
```

## Example result
```json
{
  "items": [
    {
      "defender": {
        "region": "<region>",
        "country": "<country>",
        "wonRoundsCount": 0,
        "countryOrders": [],
        "muOrders": [],
        "damages": 0,
        "hitCount": 3
      },
      "attacker": {
        "region": "<region>",
        "country": "<country>",
        "wonRoundsCount": 0,
        "countryOrders": [
          "<countryOrderId>"
        ],
        "muOrders": [
          "<muOrderId>",
          "<muOrderId>"
        ],
        "damages": 0,
        "hitCount": 277
      },
      "stats": {
        "hitCount": 0
      },
      "_id": "<battleId>",
      "war": "<war>",
      "type": "war",
      "rounds": [
        "<roundId>"
      ],
      "roundsHistory": [],
      "isActive": true,
      "roundsToWin": 2,
      "createdAt": "<isoTimestamp>",
      "updatedAt": "<isoTimestamp>",
      "__v": 1,
      "currentRound": {
        "attacker": {
          "country": "<country>",
          "damages": 236339,
          "points": 20,
          "lastHits": [
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 633,
              "mu": "<mu>",
              "isCriticalHit": true,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e6c0790968c69062f838a2",
                "code": "gun",
                "skills": {
                  "attack": 55,
                  "criticalChance": 10
                },
                "state": 79,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-21T00:10:33.377Z"
              },
              "equipments": [
                {
                  "_id": "69a6353c8f2ff1938a3eb5d1",
                  "type": "equipment",
                  "code": "helmet2",
                  "skills": {
                    "criticalDamages": 30
                  },
                  "state": 89,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-03T00:10:58.860Z",
                  "isEquipStatsMigrated": true
                },
                {
                  "_id": "69a6354f27377b19aa6f39a6",
                  "type": "equipment",
                  "code": "chest2",
                  "skills": {
                    "armor": 10
                  },
                  "state": 89,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-02T23:20:35.308Z"
                },
                {
                  "_id": "69a1055577831af4224875ef",
                  "type": "equipment",
                  "code": "pants2",
                  "skills": {
                    "armor": 10
                  },
                  "state": 89,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-02-27T02:45:41.072Z"
                },
                {
                  "_id": "69a635c82cde27ace989e86b",
                  "type": "equipment",
                  "code": "boots2",
                  "skills": {
                    "dodge": 10
                  },
                  "state": 89,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-03T00:11:38.032Z"
                },
                {
                  "_id": "69c6fd3ff66291c9d77a9691",
                  "type": "equipment",
                  "code": "gloves2",
                  "skills": {
                    "precision": 10
                  },
                  "state": 89,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-27T21:07:39.172Z"
                }
              ],
              "ammo": "lightAmmo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 174,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": true,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e5753c05801c7f99f5baa7",
                "code": "rifle",
                "skills": {
                  "attack": 78,
                  "criticalChance": 14
                },
                "state": 77,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-20T00:37:16.013Z"
              },
              "equipments": [
                {
                  "_id": "69e4fe9cc830caae56e37165",
                  "type": "equipment",
                  "code": "helmet2",
                  "skills": {
                    "criticalDamages": 18
                  },
                  "state": 21,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-11T17:41:13.073Z"
                },
                {
                  "_id": "69dd2364e28eff0d475d80ef",
                  "type": "equipment",
                  "code": "chest2",
                  "skills": {
                    "armor": 6
                  },
                  "state": 21,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-12T23:53:46.672Z"
                },
                {
                  "_id": "69e145db10ea2fde23fb24c6",
                  "type": "equipment",
                  "code": "pants2",
                  "skills": {
                    "armor": 9
                  },
                  "state": 21,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-16T20:26:03.594Z"
                },
                {
                  "_id": "69e4fea290bba79f8d295c1c",
                  "type": "equipment",
                  "code": "boots2",
                  "skills": {
                    "dodge": 8
                  },
                  "state": 21,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-17T00:37:45.459Z"
                },
                {
                  "_id": "69df97bbc9e86925c5b64232",
                  "type": "equipment",
                  "code": "gloves2",
                  "skills": {
                    "precision": 9
                  },
                  "state": 21,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-15T13:50:51.782Z"
                }
              ],
              "ammo": "ammo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 352,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e5753c05801c7f99f5baa7",
                "code": "rifle",
                "skills": {
                  "attack": 78,
                  "criticalChance": 14
                },
                "state": 78,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-20T00:37:16.013Z"
              },
              "equipments": [
                {
                  "_id": "69e4fe9cc830caae56e37165",
                  "type": "equipment",
                  "code": "helmet2",
                  "skills": {
                    "criticalDamages": 18
                  },
                  "state": 22,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-11T17:41:13.073Z"
                },
                {
                  "_id": "69dd2364e28eff0d475d80ef",
                  "type": "equipment",
                  "code": "chest2",
                  "skills": {
                    "armor": 6
                  },
                  "state": 22,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-12T23:53:46.672Z"
                },
                {
                  "_id": "69e145db10ea2fde23fb24c6",
                  "type": "equipment",
                  "code": "pants2",
                  "skills": {
                    "armor": 9
                  },
                  "state": 22,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-16T20:26:03.594Z"
                },
                {
                  "_id": "69e4fea290bba79f8d295c1c",
                  "type": "equipment",
                  "code": "boots2",
                  "skills": {
                    "dodge": 8
                  },
                  "state": 22,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-17T00:37:45.459Z"
                },
                {
                  "_id": "69df97bbc9e86925c5b64232",
                  "type": "equipment",
                  "code": "gloves2",
                  "skills": {
                    "precision": 9
                  },
                  "state": 22,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-15T13:50:51.782Z"
                }
              ],
              "ammo": "ammo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 125,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": null,
              "equipments": [],
              "ammo": null
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 105,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": true,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e18dba51ec4b9a06ebddb0",
                "code": "knife",
                "skills": {
                  "attack": 29,
                  "criticalChance": 3
                },
                "state": 15,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-17T01:32:42.433Z"
              },
              "equipments": [
                {
                  "_id": "69e05a9b5ad8e3fd88207817",
                  "type": "equipment",
                  "code": "helmet1",
                  "skills": {
                    "criticalDamages": 13
                  },
                  "state": 4,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-16T03:42:19.887Z"
                },
                {
                  "_id": "69e05a905ad8e3fd882069b7",
                  "type": "equipment",
                  "code": "chest1",
                  "skills": {
                    "armor": 3
                  },
                  "state": 4,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-16T03:42:08.313Z"
                },
                {
                  "_id": "69e592e9fe61f8ad03469301",
                  "type": "equipment",
                  "code": "pants1",
                  "skills": {
                    "armor": 2
                  },
                  "state": 69,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:43:53.047Z"
                },
                {
                  "_id": "69e3013c7acf98d4459f3cb6",
                  "type": "equipment",
                  "code": "boots1",
                  "skills": {
                    "dodge": 3
                  },
                  "state": 60,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-18T03:57:48.378Z"
                },
                {
                  "_id": "69cd2775eb7905eef487f34b",
                  "type": "equipment",
                  "code": "gloves2",
                  "skills": {
                    "precision": 7
                  },
                  "state": 4,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-01T14:11:01.700Z"
                }
              ],
              "ammo": null
            }
          ],
          "hitCount": 277
        },
        "defender": {
          "country": "<country>",
          "damages": 711,
          "points": 0,
          "lastHits": [
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 291,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69df8994a183f7383e6ecf62",
                "code": "gun",
                "skills": {
                  "attack": 60,
                  "criticalChance": 8
                },
                "state": 63,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-15T12:50:28.060Z"
              },
              "equipments": [
                {
                  "_id": "69e0cc7fb59898d9e17c169b",
                  "type": "equipment",
                  "code": "helmet2",
                  "skills": {
                    "criticalDamages": 28
                  },
                  "state": 55,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-16T11:48:15.563Z"
                },
                {
                  "_id": "69e58bc0581404c7c199529a",
                  "type": "equipment",
                  "code": "chest2",
                  "skills": {
                    "armor": 7
                  },
                  "state": 55,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:13:20.732Z"
                },
                {
                  "_id": "69e7202bafa9145f81ff7d6c",
                  "type": "equipment",
                  "code": "pants2",
                  "skills": {
                    "armor": 10
                  },
                  "state": 91,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-21T06:58:51.100Z"
                },
                {
                  "_id": "69e6fe153fe129d7cd14d2b0",
                  "type": "equipment",
                  "code": "boots2",
                  "skills": {
                    "dodge": 8
                  },
                  "state": 83,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-21T04:33:25.640Z"
                },
                {
                  "_id": "69df6b79a03070cad5386c95",
                  "type": "equipment",
                  "code": "gloves2",
                  "skills": {
                    "precision": 9
                  },
                  "state": 55,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-15T10:42:01.062Z"
                }
              ],
              "ammo": "lightAmmo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 270,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69df8994a183f7383e6ecf62",
                "code": "gun",
                "skills": {
                  "attack": 60,
                  "criticalChance": 8
                },
                "state": 64,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-15T12:50:28.060Z"
              },
              "equipments": [
                {
                  "_id": "69e0cc7fb59898d9e17c169b",
                  "type": "equipment",
                  "code": "helmet2",
                  "skills": {
                    "criticalDamages": 28
                  },
                  "state": 56,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-16T11:48:15.563Z"
                },
                {
                  "_id": "69e58bc0581404c7c199529a",
                  "type": "equipment",
                  "code": "chest2",
                  "skills": {
                    "armor": 7
                  },
                  "state": 56,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:13:20.732Z"
                },
                {
                  "_id": "69e7202bafa9145f81ff7d6c",
                  "type": "equipment",
                  "code": "pants2",
                  "skills": {
                    "armor": 10
                  },
                  "state": 92,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-21T06:58:51.100Z"
                },
                {
                  "_id": "69e6fe153fe129d7cd14d2b0",
                  "type": "equipment",
                  "code": "boots2",
                  "skills": {
                    "dodge": 8
                  },
                  "state": 84,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-21T04:33:25.640Z"
                },
                {
                  "_id": "69df6b79a03070cad5386c95",
                  "type": "equipment",
                  "code": "gloves2",
                  "skills": {
                    "precision": 9
                  },
                  "state": 56,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-15T10:42:01.062Z"
                }
              ],
              "ammo": "lightAmmo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 150,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e50d6e5c9d667490edaac0",
                "code": "knife",
                "skills": {
                  "attack": 39,
                  "criticalChance": 2
                },
                "state": 71,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-19T17:14:22.427Z"
              },
              "equipments": [
                {
                  "_id": "69e56f433fe129d7cd9b5eae",
                  "type": "equipment",
                  "code": "helmet1",
                  "skills": {
                    "criticalDamages": 11
                  },
                  "state": 58,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T00:11:47.957Z"
                }
              ],
              "ammo": null
            }
          ],
          "hitCount": 3
        },
        "live": {
          "ticksCount": 20,
          "actualTickPoints": 1,
          "nextTickAt": "<isoTimestamp>"
        },
        "_id": "<battleId>",
        "battle": "<battleId>",
        "number": 1,
        "isActive": true,
        "createdAt": "<isoTimestamp>",
        "updatedAt": "<isoTimestamp>",
        "__v": 0
      }
    },
    {
      "defender": {
        "region": "<region>",
        "country": "<country>",
        "wonRoundsCount": 0,
        "countryOrders": [
          "<countryOrderId>",
          "<countryOrderId>",
          "<countryOrderId>"
        ],
        "muOrders": [
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>"
        ],
        "damages": 0,
        "hitCount": 678,
        "bountyEffectiveAt": "<isoTimestamp>",
        "moneyPer1kDamages": 0.21,
        "moneyPool": 134.74197500000022
      },
      "attacker": {
        "region": "<region>",
        "country": "<country>",
        "wonRoundsCount": 0,
        "countryOrders": [
          "<countryOrderId>",
          "<countryOrderId>",
          "<countryOrderId>"
        ],
        "muOrders": [
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>",
          "<muOrderId>"
        ],
        "damages": 0,
        "hitCount": 789,
        "bountyEffectiveAt": "<isoTimestamp>",
        "moneyPer1kDamages": 0.2,
        "moneyPool": 60.764799999999966
      },
      "stats": {
        "hitCount": 0
      },
      "_id": "<battleId>",
      "war": "<war>",
      "type": "war",
      "rounds": [
        "<roundId>"
      ],
      "roundsHistory": [],
      "isActive": true,
      "roundsToWin": 2,
      "createdAt": "<isoTimestamp>",
      "updatedAt": "<isoTimestamp>",
      "__v": 1,
      "currentRound": {
        "attacker": {
          "country": "<country>",
          "damages": 987006,
          "points": 12,
          "lastHits": [
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 596,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": true,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69d4a8a0cdaedb21eaf0b987",
                "code": "sniper",
                "skills": {
                  "attack": 107,
                  "criticalChance": 19
                },
                "state": 76,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-07T06:48:00.197Z"
              },
              "equipments": [
                {
                  "_id": "69d3c85f15b9af643c4f4dc9",
                  "type": "equipment",
                  "code": "helmet3",
                  "skills": {
                    "criticalDamages": 42
                  },
                  "state": 24,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-06T14:51:11.102Z"
                },
                {
                  "_id": "69ce164f8b8634557391e6b4",
                  "type": "equipment",
                  "code": "chest4",
                  "skills": {
                    "armor": 21
                  },
                  "state": 23,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-02T07:10:07.336Z"
                },
                {
                  "_id": "69e491cec830caae566252ad",
                  "type": "equipment",
                  "code": "pants3",
                  "skills": {
                    "armor": 14
                  },
                  "state": 11,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:26:54.555Z"
                },
                {
                  "_id": "69deb7af120676e01546e609",
                  "type": "equipment",
                  "code": "boots4",
                  "skills": {
                    "dodge": 21
                  },
                  "state": 83,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-14T21:54:55.306Z"
                },
                {
                  "_id": "69e491d7c830caae5662602c",
                  "type": "equipment",
                  "code": "gloves3",
                  "skills": {
                    "precision": 13
                  },
                  "state": 60,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:27:03.114Z"
                }
              ],
              "ammo": "lightAmmo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 3787,
              "mu": "<mu>",
              "isCriticalHit": true,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69d4a8a0cdaedb21eaf0b987",
                "code": "sniper",
                "skills": {
                  "attack": 107,
                  "criticalChance": 19
                },
                "state": 77,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-07T06:48:00.197Z"
              },
              "equipments": [
                {
                  "_id": "69d3c85f15b9af643c4f4dc9",
                  "type": "equipment",
                  "code": "helmet3",
                  "skills": {
                    "criticalDamages": 42
                  },
                  "state": 25,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-06T14:51:11.102Z"
                },
                {
                  "_id": "69ce164f8b8634557391e6b4",
                  "type": "equipment",
                  "code": "chest4",
                  "skills": {
                    "armor": 21
                  },
                  "state": 24,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-02T07:10:07.336Z"
                },
                {
                  "_id": "69e491cec830caae566252ad",
                  "type": "equipment",
                  "code": "pants3",
                  "skills": {
                    "armor": 14
                  },
                  "state": 12,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:26:54.555Z"
                },
                {
                  "_id": "69deb7af120676e01546e609",
                  "type": "equipment",
                  "code": "boots4",
                  "skills": {
                    "dodge": 21
                  },
                  "state": 84,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-14T21:54:55.306Z"
                },
                {
                  "_id": "69e491d7c830caae5662602c",
                  "type": "equipment",
                  "code": "gloves3",
                  "skills": {
                    "precision": 13
                  },
                  "state": 61,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:27:03.114Z"
                }
              ],
              "ammo": "lightAmmo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 1159,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69d4a8a0cdaedb21eaf0b987",
                "code": "sniper",
                "skills": {
                  "attack": 107,
                  "criticalChance": 19
                },
                "state": 78,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-07T06:48:00.197Z"
              },
              "equipments": [
                {
                  "_id": "69d3c85f15b9af643c4f4dc9",
                  "type": "equipment",
                  "code": "helmet3",
                  "skills": {
                    "criticalDamages": 42
                  },
                  "state": 26,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-06T14:51:11.102Z"
                },
                {
                  "_id": "69ce164f8b8634557391e6b4",
                  "type": "equipment",
                  "code": "chest4",
                  "skills": {
                    "armor": 21
                  },
                  "state": 25,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-02T07:10:07.336Z"
                },
                {
                  "_id": "69e491cec830caae566252ad",
                  "type": "equipment",
                  "code": "pants3",
                  "skills": {
                    "armor": 14
                  },
                  "state": 13,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:26:54.555Z"
                },
                {
                  "_id": "69deb7af120676e01546e609",
                  "type": "equipment",
                  "code": "boots4",
                  "skills": {
                    "dodge": 21
                  },
                  "state": 85,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-14T21:54:55.306Z"
                },
                {
                  "_id": "69e491d7c830caae5662602c",
                  "type": "equipment",
                  "code": "gloves3",
                  "skills": {
                    "precision": 13
                  },
                  "state": 62,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:27:03.114Z"
                }
              ],
              "ammo": "lightAmmo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 1021,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69d4a8a0cdaedb21eaf0b987",
                "code": "sniper",
                "skills": {
                  "attack": 107,
                  "criticalChance": 19
                },
                "state": 79,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-07T06:48:00.197Z"
              },
              "equipments": [
                {
                  "_id": "69d3c85f15b9af643c4f4dc9",
                  "type": "equipment",
                  "code": "helmet3",
                  "skills": {
                    "criticalDamages": 42
                  },
                  "state": 27,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-06T14:51:11.102Z"
                },
                {
                  "_id": "69ce164f8b8634557391e6b4",
                  "type": "equipment",
                  "code": "chest4",
                  "skills": {
                    "armor": 21
                  },
                  "state": 26,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-02T07:10:07.336Z"
                },
                {
                  "_id": "69e491cec830caae566252ad",
                  "type": "equipment",
                  "code": "pants3",
                  "skills": {
                    "armor": 14
                  },
                  "state": 14,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:26:54.555Z"
                },
                {
                  "_id": "69deb7af120676e01546e609",
                  "type": "equipment",
                  "code": "boots4",
                  "skills": {
                    "dodge": 21
                  },
                  "state": 86,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-14T21:54:55.306Z"
                },
                {
                  "_id": "69e491d7c830caae5662602c",
                  "type": "equipment",
                  "code": "gloves3",
                  "skills": {
                    "precision": 13
                  },
                  "state": 63,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:27:03.114Z"
                }
              ],
              "ammo": "lightAmmo"
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 1148,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69d4a8a0cdaedb21eaf0b987",
                "code": "sniper",
                "skills": {
                  "attack": 107,
                  "criticalChance": 19
                },
                "state": 80,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-04-07T06:48:00.197Z"
              },
              "equipments": [
                {
                  "_id": "69d3c85f15b9af643c4f4dc9",
                  "type": "equipment",
                  "code": "helmet3",
                  "skills": {
                    "criticalDamages": 42
                  },
                  "state": 28,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-06T14:51:11.102Z"
                },
                {
                  "_id": "69ce164f8b8634557391e6b4",
                  "type": "equipment",
                  "code": "chest4",
                  "skills": {
                    "armor": 21
                  },
                  "state": 27,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-02T07:10:07.336Z"
                },
                {
                  "_id": "69e491cec830caae566252ad",
                  "type": "equipment",
                  "code": "pants3",
                  "skills": {
                    "armor": 14
                  },
                  "state": 15,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:26:54.555Z"
                },
                {
                  "_id": "69deb7af120676e01546e609",
                  "type": "equipment",
                  "code": "boots4",
                  "skills": {
                    "dodge": 21
                  },
                  "state": 87,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-14T21:54:55.306Z"
                },
                {
                  "_id": "69e491d7c830caae5662602c",
                  "type": "equipment",
                  "code": "gloves3",
                  "skills": {
                    "precision": 13
                  },
                  "state": 64,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T08:27:03.114Z"
                }
              ],
              "ammo": "lightAmmo"
            }
          ],
          "hitCount": 789
        },
        "defender": {
          "country": "<country>",
          "damages": 609743,
          "points": 13,
          "lastHits": [
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 183,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e67ade05801c7f9929cba9",
                "code": "knife",
                "skills": {
                  "attack": 27,
                  "criticalChance": 4
                },
                "state": 94,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-02-27T21:57:16.544Z",
                "isEquipStatsMigrated": true
              },
              "equipments": [
                {
                  "_id": "69e67adc78af10c9622699b7",
                  "type": "equipment",
                  "code": "helmet1",
                  "skills": {
                    "criticalDamages": 9
                  },
                  "state": 97,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T23:41:58.427Z"
                },
                {
                  "_id": "69e507bc78af10c9627812d1",
                  "type": "equipment",
                  "code": "chest1",
                  "skills": {
                    "armor": 3
                  },
                  "state": 52,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-24T13:11:43.570Z"
                },
                {
                  "_id": "69e59cc30a4ca07a2e984b08",
                  "type": "equipment",
                  "code": "pants1",
                  "skills": {
                    "armor": 4
                  },
                  "state": 77,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T00:07:46.657Z"
                },
                {
                  "_id": "69e59cb55c9d6674908ae699",
                  "type": "equipment",
                  "code": "boots1",
                  "skills": {
                    "dodge": 5
                  },
                  "state": 77,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:40:58.996Z"
                },
                {
                  "_id": "69e2dd1a00e0981e81d8571b",
                  "type": "equipment",
                  "code": "gloves1",
                  "skills": {
                    "precision": 1
                  },
                  "state": 68,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-18T01:23:38.796Z"
                }
              ],
              "ammo": null
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 170,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e67ade05801c7f9929cba9",
                "code": "knife",
                "skills": {
                  "attack": 27,
                  "criticalChance": 4
                },
                "state": 95,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-02-27T21:57:16.544Z",
                "isEquipStatsMigrated": true
              },
              "equipments": [
                {
                  "_id": "69e67adc78af10c9622699b7",
                  "type": "equipment",
                  "code": "helmet1",
                  "skills": {
                    "criticalDamages": 9
                  },
                  "state": 97,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T23:41:58.427Z"
                },
                {
                  "_id": "69e507bc78af10c9627812d1",
                  "type": "equipment",
                  "code": "chest1",
                  "skills": {
                    "armor": 3
                  },
                  "state": 52,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-24T13:11:43.570Z"
                },
                {
                  "_id": "69e59cc30a4ca07a2e984b08",
                  "type": "equipment",
                  "code": "pants1",
                  "skills": {
                    "armor": 4
                  },
                  "state": 77,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T00:07:46.657Z"
                },
                {
                  "_id": "69e59cb55c9d6674908ae699",
                  "type": "equipment",
                  "code": "boots1",
                  "skills": {
                    "dodge": 5
                  },
                  "state": 77,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:40:58.996Z"
                },
                {
                  "_id": "69e2dd1a00e0981e81d8571b",
                  "type": "equipment",
                  "code": "gloves1",
                  "skills": {
                    "precision": 1
                  },
                  "state": 68,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-18T01:23:38.796Z"
                }
              ],
              "ammo": null
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 477,
              "mu": "<mu>",
              "isCriticalHit": true,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e67ade05801c7f9929cba9",
                "code": "knife",
                "skills": {
                  "attack": 27,
                  "criticalChance": 4
                },
                "state": 96,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-02-27T21:57:16.544Z",
                "isEquipStatsMigrated": true
              },
              "equipments": [
                {
                  "_id": "69e67adc78af10c9622699b7",
                  "type": "equipment",
                  "code": "helmet1",
                  "skills": {
                    "criticalDamages": 9
                  },
                  "state": 97,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T23:41:58.427Z"
                },
                {
                  "_id": "69e507bc78af10c9627812d1",
                  "type": "equipment",
                  "code": "chest1",
                  "skills": {
                    "armor": 3
                  },
                  "state": 52,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-24T13:11:43.570Z"
                },
                {
                  "_id": "69e59cc30a4ca07a2e984b08",
                  "type": "equipment",
                  "code": "pants1",
                  "skills": {
                    "armor": 4
                  },
                  "state": 77,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T00:07:46.657Z"
                },
                {
                  "_id": "69e59cb55c9d6674908ae699",
                  "type": "equipment",
                  "code": "boots1",
                  "skills": {
                    "dodge": 5
                  },
                  "state": 77,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:40:58.996Z"
                },
                {
                  "_id": "69e2dd1a00e0981e81d8571b",
                  "type": "equipment",
                  "code": "gloves1",
                  "skills": {
                    "precision": 1
                  },
                  "state": 68,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-18T01:23:38.796Z"
                }
              ],
              "ammo": null
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 561,
              "mu": "<mu>",
              "isCriticalHit": true,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e67ade05801c7f9929cba9",
                "code": "knife",
                "skills": {
                  "attack": 27,
                  "criticalChance": 4
                },
                "state": 97,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-02-27T21:57:16.544Z",
                "isEquipStatsMigrated": true
              },
              "equipments": [
                {
                  "_id": "69e67adc78af10c9622699b7",
                  "type": "equipment",
                  "code": "helmet1",
                  "skills": {
                    "criticalDamages": 9
                  },
                  "state": 98,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T23:41:58.427Z"
                },
                {
                  "_id": "69e507bc78af10c9627812d1",
                  "type": "equipment",
                  "code": "chest1",
                  "skills": {
                    "armor": 3
                  },
                  "state": 53,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-24T13:11:43.570Z"
                },
                {
                  "_id": "69e59cc30a4ca07a2e984b08",
                  "type": "equipment",
                  "code": "pants1",
                  "skills": {
                    "armor": 4
                  },
                  "state": 78,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T00:07:46.657Z"
                },
                {
                  "_id": "69e59cb55c9d6674908ae699",
                  "type": "equipment",
                  "code": "boots1",
                  "skills": {
                    "dodge": 5
                  },
                  "state": 78,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:40:58.996Z"
                },
                {
                  "_id": "69e2dd1a00e0981e81d8571b",
                  "type": "equipment",
                  "code": "gloves1",
                  "skills": {
                    "precision": 1
                  },
                  "state": 69,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-18T01:23:38.796Z"
                }
              ],
              "ammo": null
            },
            {
              "_id": "<battleId>",
              "user": "<user>",
              "damages": 190,
              "mu": "<mu>",
              "isCriticalHit": false,
              "isMissed": false,
              "hitAt": "<isoTimestamp>",
              "weapon": {
                "_id": "69e67ade05801c7f9929cba9",
                "code": "knife",
                "skills": {
                  "attack": 27,
                  "criticalChance": 4
                },
                "state": 98,
                "maxState": 100,
                "quantity": 1,
                "lastAcquisitionAt": "2026-02-27T21:57:16.544Z",
                "isEquipStatsMigrated": true
              },
              "equipments": [
                {
                  "_id": "69e67adc78af10c9622699b7",
                  "type": "equipment",
                  "code": "helmet1",
                  "skills": {
                    "criticalDamages": 9
                  },
                  "state": 98,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-19T23:41:58.427Z"
                },
                {
                  "_id": "69e507bc78af10c9627812d1",
                  "type": "equipment",
                  "code": "chest1",
                  "skills": {
                    "armor": 3
                  },
                  "state": 53,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-03-24T13:11:43.570Z"
                },
                {
                  "_id": "69e59cc30a4ca07a2e984b08",
                  "type": "equipment",
                  "code": "pants1",
                  "skills": {
                    "armor": 4
                  },
                  "state": 78,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T00:07:46.657Z"
                },
                {
                  "_id": "69e59cb55c9d6674908ae699",
                  "type": "equipment",
                  "code": "boots1",
                  "skills": {
                    "dodge": 5
                  },
                  "state": 78,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-20T02:40:58.996Z"
                },
                {
                  "_id": "69e2dd1a00e0981e81d8571b",
                  "type": "equipment",
                  "code": "gloves1",
                  "skills": {
                    "precision": 1
                  },
                  "state": 69,
                  "maxState": 100,
                  "quantity": 1,
                  "lastAcquisitionAt": "2026-04-18T01:23:38.796Z"
                }
              ],
              "ammo": null
            }
          ],
          "hitCount": 678
        },
        "live": {
          "ticksCount": 25,
          "actualTickPoints": 1,
          "nextTickAt": "<isoTimestamp>"
        },
        "_id": "<battleId>",
        "battle": "<battle>",
        "number": 1,
        "isActive": true,
        "createdAt": "<isoTimestamp>",
        "updatedAt": "<isoTimestamp>",
        "__v": 0
      }
    }
  ],
  "nextCursor": "NEXTCURSOR"
}
```

## Notes
Response has `items` but no `nextCursor` — cursor pagination is not available on this endpoint.
