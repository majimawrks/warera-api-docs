# itemTrading.getPrices

Returns current market prices for all tradeable items as a flat object keyed by item code.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `itemCode` | string | no | IGNORED by the API — always returns all prices regardless of this value. |

## Output
- `cookedFish` — number
- `heavyAmmo` — number
- `steel` — number
- `bread` — number
- `grain` — number
- `limestone` — number
- `coca` — number
- `concrete` — number
- `oil` — number
- `case1` — number
- `lightAmmo` — number
- `steak` — number
- `livestock` — number
- `cocain` — number
- `lead` — number
- `fish` — number
- `petroleum` — number
- `ammo` — number
- `iron` — number
- `scraps` — number
- `case2` — number

## Example request
```
GET https://api2.warera.io/trpc/itemTrading.getPrices
```

## Example result
```json
{
  "cookedFish": 7.077837852593168,
  "heavyAmmo": 2.3640983661782067,
  "steel": 1.6126313592816222,
  "bread": 1.755186987756817,
  "grain": 0.07714463991680388,
  "limestone": 0.07951441294486067,
  "coca": 0.07931266679079008,
  "concrete": 1.6090618646256416,
  "oil": 0.1679584501528126,
  "case1": 3.6163186002222107,
  "lightAmmo": 0.16682856363600979,
  "steak": 3.448326537113794,
  "livestock": 1.4135294765840196,
  "cocain": 32.58553465346535,
  "lead": 0.08158499721510522,
  "fish": 3.324558972362789,
  "petroleum": 0.07806856203943437,
  "ammo": 0.6484043636542525,
  "iron": 0.08093368561790258,
  "scraps": 0.21158253791209947,
  "case2": 32.00784146341462
}
```

## Notes
The itemCode parameter is silently ignored. The API always returns the full price map. Client-side filtering is required to extract a single item.
