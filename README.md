# TikTok Engagement Index — engagement rate by niche

An open dataset of **TikTok engagement rates across 13 content niches**, measured from **4,509 public videos** (each with 10,000+ views) in 2026.

**Headline:** Education content engages hardest (**16.5%** mean engagement rate); Tech trails at **5.9%** — nearly **3× lower**. The median video across all niches sits at **10.6%**.

Engagement rate = **(likes + comments + shares + saves) / views**, computed per video.

📊 Interactive study & chart: **[https://crawlora.net/tiktok-engagement-index](https://crawlora.net/tiktok-engagement-index?utm_source=github&utm_medium=referral&utm_campaign=tiktok-engagement-index)**

## Ranking (mean engagement rate by niche)

| Rank | Niche | Videos (n) | Mean ER | Median ER |
|---|---|---|---|---|
| 1 | Education | 314 | 16.5% | 16.5% |
| 2 | Motivation | 368 | 15.5% | 15.5% |
| 3 | Comedy | 327 | 13.7% | 13.4% |
| 4 | Travel | 374 | 13.5% | 12.8% |
| 5 | Pets | 398 | 13.3% | 11.8% |
| 6 | Relationships | 344 | 13.2% | 12.9% |
| 7 | Fashion | 377 | 12.7% | 12.0% |
| 8 | Beauty | 386 | 10.6% | 9.4% |
| 9 | Fitness | 335 | 9.8% | 8.9% |
| 10 | Finance | 319 | 9.7% | 8.3% |
| 11 | Gaming | 306 | 9.1% | 8.1% |
| 12 | Food | 351 | 8.3% | 7.2% |
| 13 | Tech | 310 | 5.9% | 4.5% |

## Files

- **`data/videos.jsonl`** — one JSON row per video (4,509 rows).
- **`data/niche-summary.csv`** — per-niche aggregates (13 rows).

### `videos.jsonl` schema

| Field | Type | Description |
|---|---|---|
| `niche` | string | Content niche |
| `keyword` | string | Search keyword the video was sampled under |
| `video_id` | string | TikTok video id |
| `author` | string | Creator handle |
| `followers` | number | Creator follower count at capture |
| `views` | number | Play count |
| `likes` | number | Like (digg) count |
| `comments` | number | Comment count |
| `shares` | number | Share count |
| `saves` | number | Save (collect) count |
| `engagement_rate` | number | (likes + comments + shares + saves) / views |
| `created_at` | string | Video publish time (ISO 8601) |

## Methodology

For each niche we sampled TikTok videos via the [Crawlora TikTok API](https://crawlora.net/tiktok-engagement-index?utm_source=github&utm_medium=referral&utm_campaign=tiktok-engagement-index) (three search keywords per niche), kept those with **≥10,000 views**, deduplicated each video to count once, and computed the engagement rate per video. The per-niche figures are the mean and median of those rates. Snapshot: 2026-06-20.

**Caveats.** This is a sample of videos that **already perform** (search-surfaced, 10k+ views) — read it as a benchmark for content that gets traction, not a random slice of all of TikTok. Because **saves** count toward engagement, save-heavy niches (education, motivation) rank higher than a likes-only metric would.

## License

[Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE). Free to use, including commercially, with attribution:

> TikTok Engagement Index by Crawlora — [https://crawlora.net/tiktok-engagement-index](https://crawlora.net/tiktok-engagement-index?utm_source=github&utm_medium=referral&utm_campaign=tiktok-engagement-index)

## How it was built

Every number here came from Crawlora's TikTok endpoints (video search + stats). Pull the same data yourself, or explore the interactive study: **[https://crawlora.net/tiktok-engagement-index](https://crawlora.net/tiktok-engagement-index?utm_source=github&utm_medium=referral&utm_campaign=tiktok-engagement-index)**
