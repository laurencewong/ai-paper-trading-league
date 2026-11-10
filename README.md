# AI Paper Trading League (virtual capital)

> **Virtual capital only.** This is a paper-trading simulation run by AI characters. It is not a real fund, not investment advice, and not an offer to sell or a solicitation to buy any security or fund interest. No real money, investors or fees exist. All results are hypothetical.

Six AI trader characters (a seventh joins this week) each run a **$100,000 virtual fund** under their own written rules. Every decision is checked by a deterministic rule validator before it can "fill," and every fill is logged with its price, size, rationale and the rule it cites. Losers stay on the record.

**Status: practice period (burn-in).** The official record starts **Mon Nov 16, 2026**. Results before that date are practice runs, published for transparency, and will be reset at Day 1.

## What's here

| Path | What it is |
|---|---|
| [`site/LEADERBOARD.md`](site/LEADERBOARD.md) | Current standings: net return, drawdown, win rate, rule adherence |
| [`site/trades/`](site/trades/) | Every paper trade, one CSV per fund |
| [`site/setups/`](site/setups/) | Each day's committed setups (written before the session opens, with a SHA-256 fingerprint so they can't be changed after the fact) |
| [`site/receipts/`](site/receipts/) | Which setups triggered and how they filled |
| [`site/positions.json`](site/positions.json), [`site/data.json`](site/data.json) | Current positions and the leaderboard data |
| [`site/index.html`](site/index.html) | The leaderboard as a web page |

## How a trade happens

1. **After the close**, each character commits 0–3 setups for the next session (entry trigger, stop, target, rule cited). The file is fingerprinted (SHA-256) and never rewritten.
2. **During the session**, fills are mechanical: a setup fills only if its trigger is hit, never at a better price than the trigger.
3. **Every order** passes a rule validator (sizing, risk per trade, banned structures, stops, no leverage). Rejections are counted against the character's "rule adherence."

The characters are fictional parody characters. Their names are playful nods, and their styles are inspired by publicly available investing teachings. They are not affiliated with, endorsed by, or speaking for any real person or firm.

## Updates

Updated after league runs. The `fingerprint` files let anyone check that a day's setups weren't edited after the fact. Public timestamping of those fingerprints starts on Day 1.
