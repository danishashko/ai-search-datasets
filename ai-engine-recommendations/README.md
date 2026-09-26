# AI engine brand recommendations on "best X" buyer prompts

**Ask the same AI engine the same buying question again and 63.6% of its recommended brands repeat. Ask a different engine and only 43.6% overlap.** 1,920 answers from ChatGPT, Microsoft Copilot, Google Gemini, and Google AI Mode: 160 buyer prompts, each sent three times to each engine. Half of all recommended brands (49.8%) were named by only one of the four engines.

Source article: [AI Engines Recommend Different Brands: 1,920 Answers Compared](https://organikpi.com/blog/geo-ai-search/ai-engines-different-recommendations/) (canonical version of this dataset and the full analysis).

## Key numbers

- Rerun brand overlap: ChatGPT 73.5%, Google AI Mode 73.9%, Gemini 54.5%, Copilot 52.4%
- All four engines led with the same brand on 40 of 160 prompts
- Of 2,733 brand-prompt pairs, 49.8% were named by one engine only and 20.9% by all four
- Engines share about 44% of recommended brands but only 3% to 10% of cited source domains
- AI Mode cites Reddit in 50.4% of answers and YouTube in 52.9%; ChatGPT cited neither
- Shopping or product modules: Copilot 57.5% of answers, Gemini 40.8%, ChatGPT 8.5%, AI Mode 7.5%

## Files

| File | Format | Size |
|---|---|---|
| `organikpi-ai-engine-recommendations-2026-09.json` | JSON (with embedded field docs) | 3.2 MB |
| `organikpi-ai-engine-recommendations-2026-09.csv` | CSV | 1.4 MB |

11,889 rows: one per brand recommended in one answer, plus 5 rows for answers that recommended no brand.

## Fields

| Field | Description |
|---|---|
| `query` | the buyer prompt, sent verbatim to each engine (US) |
| `segment` | prompt segment: `b2b` (60 software prompts), `con` (40 consumer products), `dev` (30 developer tools), `svc` (30 business services) |
| `engine` | `chatgpt`, `copilot`, `gemini`, or `aimode` (Google AI Mode) |
| `run` | `1`, `2`, or `3`: the same prompt was sent three times per engine |
| `position` | order in which the answer recommends the brand (1 = first); empty for an answer that recommended no brand |
| `brand_as_named` | the product or brand exactly as the answer named it |
| `brand` | maker brand after normalization within the prompt (Hoka Clifton 11 becomes Hoka); the unit every overlap number uses |
| `shopping_module` | true if the answer carried a shopping or product module (Copilot product carousel, ChatGPT and AI Mode shopping cards, Gemini product links) |
| `cited_domains` | semicolon-separated root domains the answer cited as sources |

## Method

The 160 prompts are the same "best X" queries as the [ai-overview-best-x-citations](../ai-overview-best-x-citations/) dataset, so the two join on `query`. Each prompt was sent three times to each engine from the US on September 24, 2026. Recommended brands were extracted from every answer and normalized to the maker brand within each prompt. Sponsored ads in AI Mode are excluded from brand counts. Overlap is Jaccard similarity: shared brands divided by all brands either answer named. Full methodology in the source article.

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/ai-engines-different-recommendations/).
