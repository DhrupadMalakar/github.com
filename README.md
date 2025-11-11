# github.com
# FanPulse EPL — AI Agent for Sports Sentiment Analytics

An autonomous AI agent that reads 72 hours of Reddit discussion for all 20 Premier League clubs, classifies fan sentiment, extracts most-discussed players, and generates a consulting-style insight table.

**Tech:** Python · Reddit API (PRAW) · OpenAI GPT · pandas

---

## What it does (in plain English)
- **Collects data** from club subreddits + r/PremierLeague  
- **Understands emotion** (positive / negative, neutral minimized)  
- **Explains why** fans feel that way (tactics, players, injuries, refs)  
- **Finds top 3 players** actually discussed (names only)  
- **Shows quotes** (top 3 by score) and a **clear outlook** line  
- **Captures recent result** from post-match threads (Win/Draw/Loss + score)

---

## Architecture
```mermaid
flowchart LR
  A[Reddit Subreddits] --> B[Ingestion (PRAW)]
  B --> C[Cleaning & Emotion-Biased Classifier]
  C --> D[OpenAI: players-only filter + reasons + outlook]
  D --> E[Results Table (CSV)]
  D --> F[Report & Chart (README/PNG)]

