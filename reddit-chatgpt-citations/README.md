# Reddit was de-defaulted in ChatGPT, not demoted

**When ChatGPT's own fan-out subquery names Reddit, Reddit takes 21.3% of citations; when it does not, 0.1%. Appending "What do real users say about it?" moved Reddit from 0.8% to 14.3% of citations (McNemar exact p = 3.05e-05).**

Source article: [The ChatGPT Reddit Citation Collapse](https://organikpi.com/blog/geo-ai-search/chatgpt-reddit-citation-collapse/) (canonical version of this dataset and the full analysis).

## Key numbers

- 100 consumer prompts x 5 engines, US, August 2026: 550 responses including a 50-record paired A/B on ChatGPT
- Reddit share of the citations field: Perplexity 10.7%, Google AI Mode 8.1%, Gemini 6.9%, ChatGPT 0.9%, Copilot 0.3%
- A/B arms in this file: ab_base 0.8% Reddit, ab_variant 14.3%; 16 of 25 pairs flipped, 0 reversed

## Files

| File | What it holds |
|---|---|
| `organikpi-reddit-chatgpt-citations-2026-08.json` | 10,118 URL rows with embedded field docs |
| `organikpi-reddit-chatgpt-citations-2026-08.csv` | same rows as CSV |

## Fields

| Field | Description |
|---|---|
| `engine` | ai_mode, chatgpt, copilot, gemini, or perplexity |
| `prompt` | the consumer prompt |
| `arm` | main corpus, or ab_base / ab_variant for the paired A/B (ChatGPT only, variant appends "What do real users say about it?") |
| `citation_field` | which response field held the URL. Shares depend on which field you count; never blend them |
| `url` / `domain` | the returned URL and its registrable domain |

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/chatgpt-reddit-citation-collapse/).
