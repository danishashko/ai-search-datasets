# The organic squeeze: AI Overviews on 160 commercial queries

**82.5% of commercial Google queries no longer show an organic result first, and 72.5% show an AI Overview (US desktop, July 2026).**

Source article: [Ads Enter Google AI Mode](https://organikpi.com/blog/geo-ai-search/ads-in-google-ai-mode/) (canonical version of this dataset and the full analysis).

## Key numbers

- 160 commercial/transactional queries, 8 verticals x 20 queries, 160/160 valid
- 72.5% of queries show an AI Overview; Retail 100%, SaaS 85%, Legal 45%
- 82.5% of SERPs push the first organic result below at least one feature (mean first-organic rank 2.24)
- Median 9 cited domains per AI Overview; YouTube cited in 58.6% of AI Overviews, Reddit in 41.4%
- 0 ads captured across all 160 fetches: Google withholds ads from datacenter fetches, a methodology limit, not a finding

## Files

| File | What it holds |
|---|---|
| `organikpi-ai-mode-squeeze-2026-07.json` | 160 rows with embedded field docs |
| `organikpi-ai-mode-squeeze-2026-07.csv` | same rows as CSV |

## Fields

| Field | Description |
|---|---|
| `keyword` | the commercial query, Google US desktop |
| `vertical` | one of 8 verticals (Insurance, Retail, SaaS, Legal, Healthcare, Travel, Education, Home) |
| `aio_present` / `aio_content_returned` | AI Overview shown / content loaded |
| `aio_citation_domains_n` / `aio_citation_domains` | count and semicolon-joined list of domains cited in the AI Overview |
| `paid_count` | ads captured in the fetch (0 everywhere, see above) |
| `first_organic_rank` | absolute SERP position of the first organic result |
| `features_above_first_organic` | SERP features rendered above the first organic result |
| `feature_types` | ordered list of SERP feature types on the page |

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/ads-in-google-ai-mode/).
