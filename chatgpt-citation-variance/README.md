# ChatGPT citation variance: 4 same-day runs

**The aggregate is stable, the individual answer is not: pooled credit rates held between 22.0% and 27.9% across four same-day runs, but 55.9% of prompt-domain pairs were cited in only 1 of 4 runs (mean pairwise Jaccard 0.39).**

Source article: [ChatGPT Citation Variance Study](https://organikpi.com/blog/geo-ai-search/chatgpt-citation-variance-study/) (canonical version of this dataset and the full analysis).

## Key numbers

- 58-prompt main run plus three same-day replicates on a 28-prompt subset, US, gpt-5-6, August 2026
- 2,642 consulted sources; per-run credit rate on the 28 shared prompts: 23.1% / 24.9% / 27.9% / 22.0%
- 8 of 28 prompts credited zero sources in one run and several in another

## Files

| File | What it holds |
|---|---|
| `organikpi-chatgpt-citation-variance-2026-08.json` | 2,642 source rows with embedded field docs |
| `organikpi-chatgpt-citation-variance-2026-08.csv` | same rows as CSV |

## Fields

| Field | Description |
|---|---|
| `run` | 1 = main run (58 prompts), 2-4 = same-day replicates (28-prompt subset) |
| `prompt` / `bucket` | the prompt and its category bucket |
| `url` / `domain` | the consulted source URL and its registrable domain |
| `cited` | true if attributed in the answer body, false if consulted and dropped |
| `web_search_triggered` | true if ChatGPT ran a web search for this response |
| `fanout_queries` | pipe-joined subqueries ChatGPT wrote for itself |

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/chatgpt-citation-variance-study/).
