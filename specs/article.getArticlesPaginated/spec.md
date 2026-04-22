# article.getArticlesPaginated

Returns a paginated list of articles.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `type` | string | yes | Feed type. REQUIRED — omitting causes 400. Enum: `daily` \| `weekly` \| `top` \| `my` \| `subscriptions` \| `last`. |
| `limit` | number | no | Max articles per page. |
| `cursor` | string | no | Pagination cursor. |
| `languages` | array of strings | no | ISO 639-1 language codes to filter by (e.g. id, en). |

## Output
- `items` — array of objects
- `items[].stats` — object
- `items[].stats.likes` — number
- `items[].stats.dislikes` — number
- `items[].stats.score` — number
- `items[].stats.views` — number
- `items[].stats.comments` — number
- `items[].stats.subs` — number
- `items[].stats.tips` — number
- `items[].stats.gemTips` — number
- `items[]._id` — string
- `items[].title` — string
- `items[].content` — string
- `items[].language` — string
- `items[].category` — string
- `items[].author` — string
- `items[].isPublished` — boolean
- `items[].isDeleted` — boolean
- `items[].isPublic` — boolean
- `items[].createdAt` — string
- `items[].updatedAt` — string
- `items[].__v` — number
- `items[].publishedAt` — string
- `nextCursor` — string

## Example request
```
GET https://api2.warera.io/trpc/article.getArticlesPaginated?input={"type": "last","limit": 2}
```

## Example result
```json
{
  "items": [
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
    },
    {
      "stats": {
        "likes": 1,
        "dislikes": 0,
        "score": 1,
        "views": 10,
        "comments": 0,
        "subs": 0,
        "tips": 0,
        "gemTips": 0
      },
      "_id": "<articleId>",
      "title": "TITLE",
      "content": "CONTENT",
      "language": "ar",
      "category": "news",
      "author": "<author>",
      "isPublished": true,
      "isDeleted": false,
      "isPublic": true,
      "createdAt": "<isoTimestamp>",
      "updatedAt": "<isoTimestamp>",
      "__v": 0,
      "publishedAt": "<isoTimestamp>"
    }
  ],
  "nextCursor": "NEXTCURSOR"
}
```

## Notes
`type` is required in practice — the API returns 400 if omitted despite the spec marking it optional.
