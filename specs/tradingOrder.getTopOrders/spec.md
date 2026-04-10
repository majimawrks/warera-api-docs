# tradingOrder.getTopOrders

Returns the top buy and sell orders for a specific tradeable item.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| itemCode | string | yes | — | Item code, e.g. grain, oil, iron |

## Output
Top buy and sell orders for the specified item.

### Fields
- `buy` — array — top buy orders (best bid first)
- `sell` — array — top sell orders (lowest ask first)

### Order object fields
- `price` — number — order price
- `quantity` — number — order quantity
- `userId` — string — user who placed the order

## Notes
Buy orders are sorted descending by price; sell orders are sorted ascending by price.

## Example request
```
GET https://api2.warera.io/trpc/tradingOrder.getTopOrders?input={"itemCode":"grain"}
```
