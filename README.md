# News Dashboard

A personal daily news briefing dashboard, auto-generated and published to GitHub Pages every weekday morning at 7 AM (HKT).

**Live →** [mhigasi-design.github.io/news-dashboard](https://mhigasi-design.github.io/news-dashboard/)

---

## What it does

Each morning, an AI agent (Andy) fetches the latest stories from a curated set of major outlets, compiles them into a structured HTML briefing, and pushes it here. The root URL always redirects to the current day's brief.

**Coverage includes:**
- Global headlines & geopolitics
- Markets & economy (S&P 500, Nasdaq, Hang Seng, rates)
- Asia-Pacific & Greater China
- Technology & AI
- Science, health, and environment

**Sources:** BBC, Reuters, Bloomberg, AP, SCMP, FT, The Guardian, CNN, NYT, WSJ, Al Jazeera

---

## How it works

```
Agent wakes at 07:00 HKT (weekdays)
  → Fetches news from mainstream outlets
  → Deduplicates against 7-day archive
  → Generates news-brief-YYYY-MM-DD.html
  → Pushes to this repo via GitHub API
  → index.html redirects to today's brief
  → GitHub Pages serves it live
```

Each brief file is retained permanently, so historical dates remain accessible at their dated URL (e.g. `news-brief-2026-05-21.html`).

---

## Tech

- **Agent:** Claude (Anthropic) via NanoClaw agent harness
- **Hosting:** GitHub Pages (static, no build step)
- **Delivery:** GitHub Contents API (file create/update via `PUT`)
- **Deduplication:** Local `news_archive.json` tracks story hashes for 7 days

---

## Brief archive

Briefs are stored as individual HTML files named `news-brief-YYYY-MM-DD.html`. Browse the [repository file list](../../) to access past dates.

---

*Personal project — not affiliated with any news organisation.*
