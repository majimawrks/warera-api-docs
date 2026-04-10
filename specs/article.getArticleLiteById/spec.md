# article.getArticleLiteById

Returns the full raw article object including all internal metadata and vote data by article ID.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| articleId | string | yes | — | Unique identifier of the article |

## Output
Full raw article object including internal metadata fields not exposed by `getArticleById`.

### Fields
- `_id` — string — article identifier
- `title` — string — article title
- `content` — string — full article body
- `author` — string — userId of the author
- `publishedAt` — string — ISO 8601 publication timestamp
- `createdAt` — string — ISO 8601 creation timestamp
- `language` — string — ISO 639-1 language code
- `category` — string — article category
- `votes` — object — raw vote data
- `meta` — object — internal metadata fields

## Notes
Returns the raw server-side document including internal metadata that `getArticleById` omits. Useful when the complete data model is needed rather than the public-facing view.

## Example request
```
GET https://api2.warera.io/trpc/article.getArticleLiteById?input={"articleId":"abc123"}
```
