# itemTrading.getPrices

Returns current market prices for all tradeable items.

## Auth
optional

## Input
None.

## Output
Object mapping `itemCode` to price information for every tradeable item.

### Fields
- `<itemCode>` — object — price info for the item, including buy price, sell price, and related data

## Notes
The response is a flat map keyed by item code strings (e.g. `grain`, `oil`, `iron`). Each value contains the current market price data for that item.

## Example request
```
GET https://api2.warera.io/trpc/itemTrading.getPrices
```
