# Proposal Email Scorer

A single file, dependency free tool that scores a sales proposal email out of 100 before you send it.

**Live demo:** https://leaderr-io.github.io/proposal-email-scorer/

Paste a subject line and body, and it returns a score plus eight checks. Everything runs in the browser. No build step, no framework, no network request, nothing leaves the page.

## What it checks

| # | Check | Weight | Passing range |
|---|---|---|---|
| 1 | Subject length | 15 | 28 to 55 characters |
| 2 | Subject shouting | 10 | No all caps words, no exclamation marks |
| 3 | Spam trigger phrases | 20 | Zero matches against a 67 phrase list |
| 4 | Body length | 15 | 50 to 150 words |
| 5 | Reading grade | 10 | Flesch Kincaid grade 8 or below |
| 6 | Call to action | 15 | A specific ask the reader can answer |
| 7 | Personalisation | 10 | Prospect company named in the body |
| 8 | You to us ratio | 5 | Second person mentions at least match first person |

Score bands: 80 and above reads as ready to send, 60 to 79 as fixable, below 60 as do not send.

## Why these thresholds

The subject band comes from mobile clients truncating around 40 to 55 characters. The 50 to 150 word body band is where first touch reply rates hold up before length starts costing them. Reading grade uses the standard Flesch Kincaid formula with a syllable heuristic, so it is an estimate, not a certified readability score. The spam list is the common filter phrase set, not any one provider's rules. Each check is deterministic, so the same email always produces the same score.

## Use it

Open `index.html` in a browser. That is the whole install.

```
git clone https://github.com/leaderr-io/proposal-email-scorer.git
open proposal-email-scorer/index.html
```

Or copy `index.html` into your own site. It has no dependencies and no external assets.

## Writing the email in the first place

This tool grades an email you already wrote. If you want the draft generated from your site and your prospect's site, the [leaderr.io proposal generator](https://www.leaderr.io/proposal-generator) writes a personalised proposal email with subject line, body and CTA. For the company research that makes the personalisation check pass, the [leaderr.io dossier generator](https://www.leaderr.io/dossier-generator) builds a research brief from a company URL.

## Licence

MIT
