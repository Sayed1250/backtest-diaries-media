# Our bot's record, locked every night

This folder belongs to QuantitativeTrading (@QuantTradingBot on X, @quantitativetradingbot on Instagram and TikTok).

Since November 2, 2026 our bot runs a **live market test**: real prices, in real time, with **simulated money**.
Real money is planned for January 2027. Nothing here is financial advice and nothing here is a promise of profit.

## What `record.json` is

Every night the bot's record gets one **fingerprint** (a SHA-256 hash) per finished day, and each fingerprint is chained to
the day before:

```
fingerprint(day) = sha256( fingerprint(day before) + sha256(the day's full record) )
```

- A fingerprint shows nothing about the record: no trades, no coins, no amounts.
- If anything in any past day is changed, added or removed, that day's fingerprint and every fingerprint after it changes.
- The fingerprint of the last day of each week is also posted on our social accounts in the weekly results post.

## What it proves, and what it does not

It proves that a record we show later is the same record that existed on the night each fingerprint was published:
no day was edited and no bad week was removed. This file's history on GitHub and the dated weekly posts are the public dates.

It does not show the results by itself, and it does not prove that real money was used (it was not: this is a test with
simulated money). Days before the first publication date in `record.json` were locked on that date, not on their own night.

## How to check a record

Whoever is given the record gets the same small script that made these fingerprints, runs it on the record and compares
the output with `record.json`. Every fingerprint must match.
