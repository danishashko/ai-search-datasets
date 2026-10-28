# ChatGPT memory vs search brand recommendations

**ChatGPT's training-data memory still picks the winner 70% of the time.** The #1 recommendation matched in 110 of 158 buyer prompts whether search was on or off. Search added about 2 brands per prompt but rarely changed the top pick. 60.4% of all recommended brands appeared in both arms.

Source article: [ChatGPT Memory Still Decides 7 in 10 Top Picks](https://organikpi.com/blog/geo-ai-search/chatgpt-memory-vs-search-brand-recommendations/) (canonical version of this dataset and the full analysis).

## Key numbers

- #1 pick same in 110 of 158 prompts (70%) with or without web search
- Within-arm rerun overlap: 75.2%. Cross-arm (memory vs search): 63.7%. Gap: 11.6 pp (p < 10e-21)
- Of 1,493 brand-prompt pairs: both arms 60.4%, search-only 21.5%, memory-only 18.1%
- Memory favourites slipped from position 1.92 to 2.29 under search; 14 of 425 dropped out
- Business services shifted most (14.1 pp gap), developer tools least (7.6 pp)
- Citations in search answers made no difference to brand selection (p = 0.91)

## Files

| File | Format | Size |
|---|---|---|
| `memory-vs-search-2026-10.json` | JSON | 1.4 MB |
| `memory-vs-search-2026-10.csv` | CSV | 339 KB |

5,734 rows: one per brand recommended in one answer.

## Fields

| Field | Description |
|---|---|
| `qid` | prompt ID (0-158), joining key with the [ai-engine-recommendations](../ai-engine-recommendations/) dataset |
| `query` | the buyer prompt, sent verbatim to ChatGPT (US) |
| `segment` | prompt segment: `b2b` (60 software), `dev` (28 developer tools), `con` (40 consumer products), `svc` (30 business services) |
| `arm` | `off` (memory: "Answer from what you already know") or `on` (search: "Search the web before answering") |
| `run` | `1`, `2`, or `3`: each prompt was sent three times per arm |
| `position` | order in which the answer recommends the brand (1 = first) |
| `brand_as_named` | the product or brand exactly as the answer named it |
| `brand` | maker brand after normalization within the prompt; the unit every overlap number uses |
| `answer_has_citations` | whether this answer contained inline citations |

## Method

The 158 prompts are "best X" buyer queries, the same set used in the [ai-engine-recommendations](../ai-engine-recommendations/) dataset. Each prompt was sent to ChatGPT's web interface, US, logged-out, three times with each suffix, on October 27, 2026. Brands were extracted from each answer and normalized to the maker brand within each prompt. Overlap is Jaccard similarity. Full methodology in the source article.

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/chatgpt-memory-vs-search-brand-recommendations/).
