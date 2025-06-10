
# Reddit Stock Subreddits Dataset (Hot Posts)

This project collects and stores hot Reddit posts and their top-level comments from the following stock-related subreddits:

- r/wallstreetbets
- r/stocks
- r/investing

The data is saved in JSON format and can be used for research in NLP, financial analysis, or sentiment tracking.

---

## Dataset Description

Each record in the JSON file represents a Reddit post, including metadata and comments.

### 🔹 Example Structure

```json
{
  "subreddit": "wallstreetbets",
  "post_id": "abc123",
  "title": "Stock ABC is flying today!",
  "score": 1234,
  "flair": "Discussion",
  "created_utc": "2025-05-27T12:00:00Z",
  "num_comments": 100,
  "url": "https://reddit.com/r/wallstreetbets/comments/abc123",
  "comments": [
    {
      "comment_body": "Going to the moon!",
      "comment_score": 500,
      "comment_created_utc": "2025-05-27T12:10:00Z"
    }
  ]
}
```
---

## Data Dictionary

The output `.json` file contains a list of post objects. Each post has the following fields:

| Field         | Description                                         |
|---------------|-----------------------------------------------------|
| `subreddit`   | Name of the subreddit (e.g., wallstreetbets)       |
| `post_id`     | Unique ID of the post                              |
| `title`       | Title of the post                                  |
| `score`       | Number of upvotes the post received                |
| `flair`       | Post category (may be `null` if no flair is set)   |
| `created_utc` | Timestamp when the post was created                |
| `num_comments`| Total number of comments on the post               |
| `url`         | URL link to the Reddit post                        |
| `comments`    | List of top-level comments (each with body, score, created_utc) |

Each comment includes:
- `comment_body`: Text of the comment  
- `comment_score`: Number of upvotes on the comment  
- `comment_created_utc`: Timestamp of when the comment was posted 
---

## How to reproduce This Dataset

### Requirements

Install required packages:

```bash
pip install praw python-dotenv
```

### .env File (Required)

Create a `.env` file with your Reddit API credentials:

```
REDDIT_CLIENT_ID=your_client_id
REDDIT_CLIENT_SECRET=your_client_secret
REDDIT_USER_AGENT=your_user_agent
```

### Run the Scraper

Open the Jupyter notebook `511project(final).ipynb` and run all the cells. This will collect hot posts and their top-level comments from selected subreddits and save the data into a `.json` file.

---

## Data Policy

- This dataset is generated from Reddit’s official API in compliance with their [API Terms of Use](https://redditinc.com/policies/data-api-terms).
- Raw data should not be shared publicly. Instead, share the code to allow others to recreate the dataset on their own machine.

---
