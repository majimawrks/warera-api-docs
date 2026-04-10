# article.getArticleById

Returns a full article object including engagement metrics by article ID.

## Auth
optional

## Input
| Parameter | Type | Required | Default | Description |
|---|---|---|---|---|
| articleId | string | yes | — | Unique identifier of the article |

## Output
Full article object with content and engagement metrics.

### Fields
- `_id` — string — article identifier
- `title` — string — article title
- `content` — string — full article body
- `author` — string — userId of the author
- `publishedAt` — string — ISO 8601 publication timestamp
- `createdAt` — string — ISO 8601 creation timestamp
- `language` — string — ISO 639-1 language code
- `category` — string — article category
- `likes` — number — total like count
- `dislikes` — number — total dislike count
- `views` — number — total view count
- `comments` — array — list of comment objects

## Notes
Authentication may reveal additional fields such as the requesting user's vote status on the article.

## Example request
```
GET https://api2.warera.io/trpc/article.getArticleById?input={"articleId":"abc123"}
```
