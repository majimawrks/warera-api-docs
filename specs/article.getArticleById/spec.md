# article.getArticleById

Returns a full article object by ID, including content HTML, votes, and comments.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `articleId` | string | yes | Article ID. |

## Output
- `stats` — object
- `stats.likes` — number
- `stats.dislikes` — number
- `stats.score` — number
- `stats.views` — number
- `stats.comments` — number
- `stats.subs` — number
- `stats.tips` — number
- `stats.gemTips` — number
- `_id` — string
- `title` — string
- `content` — string
- `language` — string
- `category` — string
- `author` — string
- `isPublished` — boolean
- `isDeleted` — boolean
- `isPublic` — boolean
- `createdAt` — string
- `updatedAt` — string
- `__v` — number
- `publishedAt` — string

## Example request
```
GET https://api2.warera.io/trpc/article.getArticleById?input={"articleId": "<articleId>"}
```

## Example result
```json
{
  "stats": {
    "likes": 0,
    "dislikes": 1,
    "score": -1,
    "views": 4,
    "comments": 0,
    "subs": 0,
    "tips": 0,
    "gemTips": 0
  },
  "_id": "<articleId>",
  "title": "TITLE",
  "content": "CONTENT",
  "language": "en",
  "category": "military",
  "author": "<author>",
  "isPublished": true,
  "isDeleted": false,
  "isPublic": true,
  "createdAt": "<isoTimestamp>",
  "updatedAt": "<isoTimestamp>",
  "__v": 0,
  "publishedAt": "<isoTimestamp>"
}
```
