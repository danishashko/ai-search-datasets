# AI citation accuracy: do the cited pages back the claims?

**85% of AI citations back at least part of the claim they are attached to. 15% back none of it.** 2,664 citation-claim pairs from ChatGPT, Gemini, and Copilot, each checked against the cited page text. ChatGPT has the lowest unsupported rate (7.3%), Gemini the highest (22.8%). Missing feature details cause most partial failures; prices are second.

Source article: [Do AI Citations Actually Back the Claims They Are Attached To? 2,664 Verdicts](https://organikpi.com/blog/geo-ai-search/ai-citation-accuracy-study/) (canonical version of this dataset and the full analysis).

## Key numbers

- Fully supported: 1,409 (53%), partially supported: 855 (32%), not supported: 400 (15%)
- ChatGPT: 7.3% unsupported, Copilot: 15.0%, Gemini: 22.8%
- 64% of partial verdicts miss a feature or spec detail; 16% involve a price that does not appear on the cited page
- Vendor own-pages: 23% unsupported vs. 13% for third-party review sites
- 128 of 160 queries produced at least one unsupported citation
- Inter-rater agreement on supported vs. not: 92% (Cohen's kappa 0.55 overall)

## Files

| File | Format | Size |
|---|---|---|
| `organikpi-ai-citation-accuracy-2026-10.json` | JSON | 1.9 MB |
| `organikpi-ai-citation-accuracy-2026-10.csv` | CSV | 1.4 MB |

2,690 rows: one per citation-claim pair judged (2,664 judgeable plus 26 unreachable).

## Fields

| Field | Description |
|---|---|
| `engine` | `chatgpt`, `gemini`, or `copilot` |
| `query` | the buyer prompt, same 160 queries as the AI engine recommendations and AI Overview datasets |
| `cited_url` | the URL the engine cited |
| `domain` | root domain of the cited URL |
| `claim` | the sentence the citation is attached to |
| `verdict` | `SUPPORTED`, `PARTIAL`, `NOT_SUPPORTED`, or `UNREACHABLE` |
| `evidence_quote` | verbatim substring from the page that backs the claim (max 300 chars; empty for NOT_SUPPORTED and UNREACHABLE) |
| `reason` | one-sentence explanation of the verdict |
| `map_method` | how the citation was mapped to a claim: `html_pill` (ChatGPT inline citations) or `position_text` (positional extraction) |
| `flag` | judge processing flag, if any (e.g., `quote_not_verbatim`) |

## Method

The 160 prompts are the same "best X" queries as the [ai-engine-recommendations](../ai-engine-recommendations/) and [ai-overview-best-x-citations](../ai-overview-best-x-citations/) datasets, so all three join on `query`. Each prompt was sent once to ChatGPT, Gemini, and Copilot on October 1, 2026 via Bright Data's AI scraper endpoints. Google AI Mode was attempted but dropped (collection stalled). Perplexity was excluded (sign-up wall).

Each response was parsed to extract citation-claim pairs. Cited pages were fetched and their text extracted. Each pair was judged by an LLM judge with a verbatim-quote requirement: the judge must return an exact substring from the page as evidence, or the verdict is downgraded. A blind second labelling of 60 random rows produced 73% exact agreement and 92% agreement on the binary "supported vs. not" question. Scraped page bodies are not included in the dataset.

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/ai-citation-accuracy-study/).
