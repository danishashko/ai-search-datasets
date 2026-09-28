# Vendor self-ranking lists in AI answers

**AI engines cite vendors' own "best X" lists, then leave the vendor out of the answer 46.2% of the time.** 8,272 citations from 1,920 answers by ChatGPT, Microsoft Copilot, Google Gemini, and Google AI Mode, with every cited page typed by who published it and, for list pages, where the publisher ranks itself.

Source article: [Self-Promotional Listicles in AI Search: 8,272 Citations Analyzed](https://organikpi.com/blog/geo-ai-search/self-promotional-listicles-ai-search/) (canonical version of this dataset and the full analysis).

## Key numbers

- Vendors ranked themselves #1 on 378 of the 462 vendor-written list pages the engines cited (81.8%)
- 518 of 1,920 answers (27.0%) cited at least one such list; Gemini 43.8% of its answers, Copilot 16.5%
- When an answer cited a vendor's self-ranked list, it recommended the vendor 53.8% of the time and picked it first 10.9% of the time
- A #1 spot on another site's list: recommended 85.7%, first pick 35.2%
- Same engine and prompt across reruns, niche brands: own list 4.5% to 26.1% inclusion; third-party #1 list 21.3% to 66.9%

## Files

| File | Format | Size |
|---|---|---|
| `organikpi-vendor-self-ranking-lists-2026-09.json` | JSON (with embedded field docs) | 4.5 MB |
| `organikpi-vendor-self-ranking-lists-2026-09.csv` | CSV | 1.6 MB |

8,272 rows: one per cited URL in one answer.

## Fields

| Field | Description |
|---|---|
| `query` | the buyer prompt, sent verbatim to each engine (US) |
| `segment` | `b2b` (60 software prompts), `con` (40 consumer products), `dev` (30 developer tools), `svc` (30 business services) |
| `engine` | `chatgpt`, `copilot`, `gemini`, or `aimode` (Google AI Mode) |
| `run` | `1`, `2`, or `3`: each prompt was sent three times per engine on September 24, 2026 |
| `citation_order` | order of the URL among the answer's cited sources |
| `url` | cited URL, tracking parameters removed |
| `domain` | host of the cited URL |
| `page_title` | the page's HTML title (or the engine's title when the page was not fetched) |
| `page_type` | `vendor_list`, `third_party_list`, `vendor_page`, `other`, `ugc` (YouTube, Reddit and similar, typed by domain), `not_fetched` |
| `publisher_brand` | the category brand that publishes the page, when there is one |
| `publisher_in_any_answer` | true if at least one of the 1,920 answers recommended the publisher for this prompt |
| `list_first_brand` | for list pages: the first brand of the category the list presents |
| `publisher_rank_in_own_list` | for `vendor_list` pages: where the publisher places itself (1 = first); empty if absent |
| `publisher_recommended_in_this_answer` | whether this answer recommended the page's publisher |
| `publisher_position_in_this_answer` | the publisher's position in this answer's recommendations (1 = first) |

## Method

The answers are the ones in the [ai-engine-recommendations](../ai-engine-recommendations/) dataset, so the two join on `query`, `engine`, and `run`. Cited pages were fetched on September 28, 2026. A page counts as a list when its headings name at least three brands from the prompt's category; its ranking is the order those headings name them. Vendor lists are lists published by a company that sells a product in the category; publishers no engine recommended were checked by hand. Full methodology in the source article.

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/self-promotional-listicles-ai-search/).
