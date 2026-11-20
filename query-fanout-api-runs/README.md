# Query fan-out on the API: 439 searches from five models

**Gemini 4 Carbon, Hydrogen, Neon and GPT-6.2 Sol repeated their full set of searches in 0 of 44 reruns, and GPT-6.2 Sol named a vendor the prompt never mentioned in 59 of its 110 searches.**

Source article: [Query Fan-Out Changes Between Runs: 439 AI Searches Captured](https://organikpi.com/blog/geo-ai-search/query-fan-out-study/) (canonical version of this dataset and the full analysis).

## Key numbers

- 12 prompts, each run twice on Gemini 4 Argon, Carbon, Hydrogen and Neon (Gemini API with Google Search grounding) and GPT-6.2 Sol (OpenAI Responses API with web search, search required), 19 and 20 November 2026
- 120 answers, 439 searches; 5 repeated the prompt word for word
- 267 searches carried a year, and all 267 included 2026
- GPT-6.2 Sol shared none of its 110 searches between its two runs

## Files

| File | What it holds |
|---|---|
| `organikpi-query-fanout-api-runs-2026-11.json` | 439 search rows |
| `organikpi-query-fanout-api-runs-2026-11.csv` | same rows as CSV |

## Fields

| Field | Description |
|---|---|
| `model` | gemini-4-argon, gemini-4-carbon, gemini-4-hydrogen, gemini-4-neon or gpt-6.2-sol |
| `prompt_id` / `prompt` | p01 to p12 and the prompt text sent |
| `run` | 1 or 2 |
| `fanout_query` | one search the model ran for that answer |
| `has_year` | true if the search contains a year from 2024 to 2029 |
| `unprompted_vendors` | pipe-joined vendor or product names in the search that the prompt did not name (word-boundary match against a hand-built list, so a floor) |

Answers written without a search have no rows.

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/query-fan-out-study/).
