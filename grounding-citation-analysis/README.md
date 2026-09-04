# Grounding citation analysis: 42,971 AI Mode citations decoded

**42,971 Google AI Mode citations from 520 queries (March 2026), with 11,672 exact cited sentences recovered by decoding `#:~:text=` URL fragments.**

Source article: [We Decoded 42,971 AI Citations Using Google's Own Research](https://organikpi.com/blog/geo-ai-search/decoded-42971-ai-citations-google-research/) (canonical version of this dataset and the full analysis).

This is the March 2026 study that first exploited text fragments at scale, when AI Mode still exposed them. Google removed fragment exposure from AI Mode by May 2026, which makes this capture unrepeatable: see the follow-up dataset [ai-citation-patterns](../ai-citation-patterns/).

## Key numbers

- 42,971 citation rows across 520 queries, US, March 2026
- 11,672 rows carry a decoded `#:~:text=` fragment: the exact sentence Google cited
- 34,983 rows are flagged as cited inline in the answer text

## Files

| File | What it holds |
|---|---|
| `citations.csv.gz` | 42,971 rows, one per citation: query, URL, domain, decoded cited sentence and passage, position data |
| `answers.csv` | one row per query answer: word count, sentence count, list/table flags, citation count |

## Main fields (citations.csv)

| Field | Description |
|---|---|
| `query` | the query sent to Google AI Mode |
| `citation_url_clean` | cited URL with the text fragment stripped |
| `domain` | registrable domain of the cited URL |
| `cited_flag` | true if the URL is cited inline in the answer text (not just listed as a source) |
| `has_text_fragment` | true if the citation URL carried a `#:~:text=` fragment |
| `cited_sentence` / `cited_passage` | the decoded sentence/passage Google cited, where a fragment existed |
| `prefix` / `suffix` / `text_end` | raw text fragment components before decoding |

Full pipeline, notebooks, and charts live in the original study repo: [danishashko/grounding-citation-analysis](https://github.com/danishashko/grounding-citation-analysis).

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/decoded-42971-ai-citations-google-research/).
