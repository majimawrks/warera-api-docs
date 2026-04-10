# event.getEventsPaginated

Returns a paginated list of game events, optionally filtered by country and event type.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| countryId | string | no | — | Filter events by country |
| limit | number | no | 10 | Maximum number of events to return |
| cursor | string | no | — | Pagination cursor returned by the previous response |
| eventTypes | string[] | no | — | Filter by event type strings (see Notes) |

## Output
Paginated list of event objects and a cursor for the next page.

### Fields
- `items` — array — list of Event objects
- `nextCursor` — string|null — cursor for the next page; null when no more pages

### Event object fields
- `type` — string — event type identifier
- `data` — object — event-specific data payload (shape varies by type)
- `createdAt` — string — ISO 8601 timestamp

## Notes
Valid `eventTypes` values: `warDeclared`, `peace_agreement`, `battleOpened`, `battleEnded`, `newPresident`, `regionTransfer`, `peaceMade`, `countryMoneyTransfer`, `depositDiscovered`, `depositDepleted`, `systemRevolt`, `bankruptcy`, `allianceFormed`, `allianceBroken`, `regionLiberated`, `strategicResourcesReshuffled`, `resistanceIncreased`, `resistanceDecreased`, `revolutionStarted`, `revolutionEnded`, `financedRevolt`.

## Example request
```
GET https://api2.warera.io/trpc/event.getEventsPaginated?input={"countryId":"ID","limit":10,"eventTypes":["battleOpened","battleEnded"]}
```
