# Which LinkedIn URLs AI engines cite

**Across five AI engines, LinkedIn citations are 46 /pulse/ articles and 32 /posts/ feed posts, and zero /in/ profiles and zero /company/ pages.**

Source article: [Which LinkedIn URLs AI Engines Cite](https://organikpi.com/blog/geo-ai-search/which-linkedin-urls-ai-engines-cite/) (canonical version of this dataset and the full analysis).

## Key numbers

- 100 professional-intent prompts x 5 engines, US, August 2026; 456 valid responses (Perplexity 56 after retries)
- LinkedIn share of the citations field: AI Mode 4.4% (39/896, the #3 domain), Perplexity 1.4%, ChatGPT 1.3%, Copilot 0.9% of its sources field, Gemini 0%
- All 4 ChatGPT LinkedIn URLs carried utm_source=chatgpt.com; no other engine tags URLs
- ChatGPT fired no web search on any of the 100 professional prompts in this run

## Files

| File | What it holds |
|---|---|
| `organikpi-linkedin-ai-citations-2026-08.json` | 4,008 URL rows with embedded field docs |
| `organikpi-linkedin-ai-citations-2026-08.csv` | same rows as CSV |

## Fields

| Field | Description |
|---|---|
| `engine` | ai_mode, chatgpt, copilot, gemini, or perplexity |
| `prompt` | the professional-intent prompt |
| `citation_field` | which response field held the URL (citations, sources, search_sources, ...). Shares depend on which field you count; never blend them |
| `url` / `domain` | the returned URL and its registrable domain |
| `linkedin_url_type` | first path segment for linkedin.com URLs (pulse, posts, in, company, ...) |
| `utm_source` | utm_source query param if the engine tagged the URL |

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/which-linkedin-urls-ai-engines-cite/).
