# article.getArticleLiteById

Returns a lightweight article object by ID, including internal vote/like data.

## Auth
none

## Input
| Parameter | Type | Required | Description |
|---|---|---|---|
| `articleId` | string | yes | Article ID. |

## Output
- `_id` — string
- `title` — string
- `stats` — object
- `stats.likes` — number
- `stats.dislikes` — number
- `stats.score` — number
- `stats.views` — number
- `stats.comments` — number
- `stats.subs` — number
- `stats.tips` — number
- `stats.gemTips` — number

## Example request
```
GET https://api2.warera.io/trpc/article.getArticleLiteById?input={"articleId": "<articleId>"}
```

## Example result
```json
{
  "_id": "<articleId>",
  "title": "TITLE",
  "stats": {
    "likes": 0,
    "dislikes": 1,
    "score": -1,
    "views": 5,
    "comments": 0,
    "subs": 0,
    "tips": 0,
    "gemTips": 0
  }
}
```

## Notes
Lighter payload than getArticleById but exposes internal fields.
