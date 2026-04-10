# article.getArticlesPaginated

Returns a paginated list of articles, optionally filtered by type and language.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| type | string | no | last | Article feed type: daily, weekly, top, my, subscriptions, last |
| limit | number | no | 10 | Maximum number of articles to return |
| cursor | string | no | — | Pagination cursor returned by the previous response |
| languages | string[] | no | — | Filter by ISO 639-1 language codes, e.g. ["id","en"] |

## Output
Paginated list of article summaries and a cursor for the next page.

### Fields
- `items` — array — list of Article objects
- `nextCursor` — string|null — cursor to pass as `cursor` for the next page; null when no more pages

### Article object fields
- `_id` — string — article identifier
- `title` — string — article title
- `content` — string — article body
- `author` — string — userId of the author
- `publishedAt` — string — ISO 8601 publication timestamp
- `createdAt` — string — ISO 8601 creation timestamp
- `language` — string — ISO 639-1 language code
- `category` — string — article category

## Notes
The `my` and `subscriptions` types require an authenticated session; unauthenticated requests may return empty results for those types.

## Example request
```
GET https://api2.warera.io/trpc/article.getArticlesPaginated?input={"type":"last","limit":10,"languages":["en"]}
```
