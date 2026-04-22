# tradingOrder.getTopOrders

Returns the top buy and sell orders for a specific tradeable item.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `itemCode` | string | yes | Item code (e.g. grain, oil, iron, steel, bread, lightAmmo). |

## Output
- `buyOrders` — array of objects
- `buyOrders[]._id` — string
- `buyOrders[].user` — string
- `buyOrders[].itemCode` — string
- `buyOrders[].quantity` — number
- `buyOrders[].price` — number
- `buyOrders[].offerAt` — string
- `buyOrders[].type` — string
- `buyOrders[].__v` — number
- `sellOrders` — array of objects
- `sellOrders[]._id` — string
- `sellOrders[].user` — string
- `sellOrders[].itemCode` — string
- `sellOrders[].quantity` — number
- `sellOrders[].price` — number
- `sellOrders[].offerAt` — string
- `sellOrders[].type` — string
- `sellOrders[].__v` — number

## Example request
```
GET https://api2.warera.io/trpc/tradingOrder.getTopOrders?input={"itemCode": "grain"}
```

## Example result
```json
{
  "buyOrders": [
    {
      "_id": "<orderId>",
      "user": "<user>",
      "itemCode": "grain",
      "quantity": 751,
      "price": 0.077,
      "offerAt": "<isoTimestamp>",
      "type": "buy",
      "__v": 0
    },
    {
      "_id": "<orderId>",
      "user": "<user>",
      "itemCode": "grain",
      "quantity": 201,
      "price": 0.076,
      "offerAt": "<isoTimestamp>",
      "type": "buy",
      "__v": 0
    }
  ],
  "sellOrders": [
    {
      "_id": "<orderId>",
      "user": "<user>",
      "itemCode": "grain",
      "quantity": 110,
      "price": 0.079,
      "offerAt": "<isoTimestamp>",
      "type": "sell",
      "__v": 0
    },
    {
      "_id": "<orderId>",
      "user": "<user>",
      "itemCode": "grain",
      "quantity": 2400,
      "price": 0.079,
      "offerAt": "<isoTimestamp>",
      "type": "sell",
      "__v": 0
    }
  ]
}
```

## Notes
CORRECTION: output fields are `buyOrders` and `sellOrders` (original spec documented `buy`/`sell`).
