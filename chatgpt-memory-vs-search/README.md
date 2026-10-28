# ChatGPT memory vs search brand recommendations

**ChatGPT kept the same #1 pick in 110 of 158 buyer prompts (70%) with and without web search.** Search swapped about 2 brands in and 1.7 out per prompt, and about half of those swaps appeared in only 1 of 3 runs. 60.4% of recommended brand-prompt pairs appeared in both arms.

Source article: [ChatGPT Keeps Its No-Search Top Pick in 7 of 10 Prompts](https://organikpi.com/blog/geo-ai-search/chatgpt-memory-vs-search-brand-recommendations/) (canonical version of this dataset and the full analysis).

## Key numbers

- #1 pick same in 110 of 158 prompts (modal pick across 3 runs per arm); search flipped it in 48
- Per-run #1 agreement: memory reruns 82.7%, search reruns 74.9%, memory vs search 65.7%
- Within-arm rerun overlap: 75.2%. Cross-arm (memory vs search): 63.7%. Gap: 11.6 pp (p < 1e-21)
- Of 1,493 brand-prompt pairs: both arms 60.4%, search-only 21.5%, memory-only 18.1%
- Per prompt, search added 2.03 and dropped 1.71 brands; 55.8% of search-only and 55.2% of memory-only pairs appeared in just 1 of 3 runs
- Overlap gap by segment: business services 14.1 pp, developer tools 7.6 pp (differences between segments not tested)

"Memory" = the prompt carried the suffix "Answer from what you already know. Do not search the web." "Search" = "Search the web before answering." Arms are analysed as assigned; 200 of 474 search answers showed inline citations.

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
