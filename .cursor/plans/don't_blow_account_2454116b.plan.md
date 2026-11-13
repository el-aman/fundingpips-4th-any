---
name: Don't Blow Account
overview: "A single-file browser mini-game: survive four trading rounds without blowing a demo account, then land on a FundingPips 4th-anniversary win screen."
todos:
  - id: build-game
    content: "Write index.html: layout, 4-round Long/Short/Sit logic, blown and win screens, FundingPips wordmark"
    status: completed
  - id: play-check
    content: Open the file in the browser and play a win and a blown-account path
    status: in_progress
isProject: false
---

# Don't Blow the Account

One file, no build step, playable in the browser in under a minute. Open [index.html](index.html) and screen-record it for the X post.

## What the player does

Start with a **$100,000 demo account**. Four rounds, labeled Year 1 through Year 4.

Each round:

1. A short candle hint flashes (mostly honest, sometimes a fakeout).
2. Player taps **Long**, **Short**, or **Sit out**.
3. The move resolves immediately. Right call adds equity, wrong call cuts it, sitting out does nothing.
4. A daily-loss line sits on the equity bar. Cross it and the account is blown.

Clear all four years and the screen flips to the anniversary ending: **4 YEARS. STILL BUILDING.** plus “And we’re just getting started.”

Blown account shows a short joke line and a **Try again** button. Win screen has **Play again**.

## How it looks

Dark page, gold and cream type, green up / red down, matching the site’s trading look. Reuse the wordmark paths already in [fundingpips.html](fundingpips.html) in the header. No images, no fonts from a CDN, no canvas engine. Equity is a CSS bar. The “chart” is four CSS candles. Confetti on the win screen is a handful of animated divs.

Copy stays light and original. A one-line note that this is a fan-made simulated game, not a FundingPips product.

## File

Replace the logo-only page with [index.html](index.html): HTML, CSS, and a short script in one file. [fundingpips.html](fundingpips.html) stays as the logo source to copy from.

Logic is one object: `equity`, `round` (0–3), `alive`. Each choice picks a random move with a bias from the hint, updates equity, then either advances the year or shows blown / win. No loops, no timers beyond a short CSS flash before the buttons unlock.
