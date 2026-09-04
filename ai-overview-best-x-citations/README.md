# AI Overview citations on "best X" buyer queries

**77.6% of 1,208 AI Overview citations on "best X" searches point to other ranked lists.** When a buyer asks Google for the best option in a category, the AI Overview almost never evaluates products itself: it aggregates pages that already ranked something. OrganiKPI calls the pattern second-hand visibility.

Source article: [Who Google's AI Overview Cites When Buyers Search "Best X"](https://organikpi.com/blog/geo-ai-search/ai-overview-citations-best-x-queries/) (canonical version of this dataset and the full analysis).

## Key numbers

- 159 of 160 buyer queries triggered an AI Overview (US desktop, September 2026); 158 returned citations
- 77.6% of citations point to a ranked list, roundup, or picks page
- YouTube carries 22.6% of all citations, more than any website
- Source mix: 386 UGC, 276 vendor, 274 editorial, 229 blog, 39 other, 4 unclassified
- Vendors earn citations mostly by publishing their own category ranking

## Files

| File | Format | Size |
|---|---|---|
| `organikpi-aio-best-x-citations-2026-09.json` | JSON (with embedded field docs) | 410 KB |
| `organikpi-aio-best-x-citations-2026-09.csv` | CSV | 215 KB |

## Fields

| Field | Description |
|---|---|
| `query` | the "best X" Google query, US desktop |
| `segment` | query segment: `b2b` (60 software queries), `con` (40 consumer products), `dev` (30 developer tools), `svc` (30 business services) |
| `domain` | registrable domain of the cited URL |
| `url` | the URL cited in the AI Overview |
| `title` | title of the cited page as returned in the AI Overview |
| `source_class` | our classification: `ugc`, `vendor`, `editorial`, `blog`, `other`, or `unknown` (4 rows we could not classify) |
| `is_ranked_list` | true if the cited URL or title marks it as a ranked list, roundup, or picks page |
| `in_organic_top10` | true if the cited domain also appears in the query's top 10 organic results |

## Method

160 commercial "best X" queries across four segments were run against Google US desktop in September 2026 and every AI Overview citation was captured: 1,208 cited URLs. Each citation was classified by source type and checked against the query's top 10 organic results. Full methodology in the source article.

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/ai-overview-citations-best-x-queries/).
