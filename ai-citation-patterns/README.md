# AI citation patterns: 153,425 citations across 6 platforms

**153,425 citations from 5,000 queries across six AI platforms (May 2026), with the exact cited sentence decoded wherever the platform exposed a `#:~:text=` fragment.**

Source article: [Google Killed AI Mode Text Fragments. We Captured 153,425 Citations to Find What Replaced Them](https://organikpi.com/blog/seo-strategy/ai-mode-text-fragments-dead-153425-citations/) (canonical version of this dataset and the full analysis).

## Key numbers

- Google AI Mode 88,392 citations, Grok 30,676, Gemini 13,487, Copilot 8,779, Perplexity 8,562, ChatGPT 3,529
- Google AI Mode dropped text fragment exposure from 70.9% (March 2026) to 0%
- Gemini exposed fragments on 84.1% of its citations: 11,346 decoded cited sentences in this file
- ChatGPT cited URLs overlap Google top-10 organic at just 4.2%
- 44,245 rows are flagged as cited inline in the answer text; the rest are returned as sources

## Files

| File | What it holds |
|---|---|
| `citations.csv.gz` | 153,425 rows, one per citation: platform, query, URL, domain, cited sentence (where decodable), position data |
| `answers.csv` | one row per query/platform answer: word count, sentence count, list/table flags, citation count |

## Main fields (citations.csv)

| Field | Description |
|---|---|
| `platform` | `ai_mode`, `grok`, `gemini`, `copilot`, `perplexity`, or `chatgpt` |
| `query` | the query sent to the platform |
| `citation_url_clean` | cited URL with the text fragment stripped |
| `domain` | registrable domain of the cited URL |
| `cited_flag` | true if the URL is cited inline in the answer text (not just listed as a source) |
| `has_text_fragment` | true if the citation URL carried a `#:~:text=` fragment |
| `cited_sentence` / `cited_passage` | the decoded sentence/passage the platform cited, where a fragment existed |
| `cited_sentence_word_count` | length of the decoded cited sentence |

Full pipeline, notebooks, and charts live in the original study repo: [danishashko/ai-citation-patterns](https://github.com/danishashko/ai-citation-patterns).

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/seo-strategy/ai-mode-text-fragments-dead-153425-citations/).
