# AI Search Datasets

Open datasets behind original AI search research. Every study self-hosts its data on the source article; this repo mirrors the same files for easy access, forking, and citation.

All datasets are CC BY 4.0. Cite the source article when you use one.

## Datasets

| Dataset | Rows | What it covers | Source article |
|---|---|---|---|
| [ai-engine-recommendations](./ai-engine-recommendations/) | 11,889 | Every brand ChatGPT, Copilot, Gemini, and Google AI Mode recommended across 160 "best X" prompts, 3 runs each, with cited domains and shopping modules (September 2026) | [AI Engines Recommend Different Brands: 1,920 Answers Compared](https://organikpi.com/blog/geo-ai-search/ai-engines-different-recommendations/) |
| [ai-overview-best-x-citations](./ai-overview-best-x-citations/) | 1,208 | Every citation Google's AI Overview returned for 160 "best X" buyer queries (US desktop, September 2026) | [Who Google's AI Overview Cites When Buyers Search "Best X"](https://organikpi.com/blog/geo-ai-search/ai-overview-citations-best-x-queries/) |
| [ai-citation-patterns](./ai-citation-patterns/) | 153,425 | Citations from 5,000 queries across 6 AI platforms, cited sentences decoded via text fragments (May 2026) | [Google Killed AI Mode Text Fragments](https://organikpi.com/blog/seo-strategy/ai-mode-text-fragments-dead-153425-citations/) |
| [grounding-citation-analysis](./grounding-citation-analysis/) | 42,971 | Google AI Mode citations with 11,672 exact cited sentences decoded (March 2026, unrepeatable capture) | [We Decoded 42,971 AI Citations](https://organikpi.com/blog/geo-ai-search/decoded-42971-ai-citations-google-research/) |
| [linkedin-ai-citations](./linkedin-ai-citations/) | 4,008 | Every URL five AI engines returned for 100 professional prompts; LinkedIn URL types and utm tags (August 2026) | [Which LinkedIn URLs AI Engines Cite](https://organikpi.com/blog/geo-ai-search/which-linkedin-urls-ai-engines-cite/) |
| [reddit-chatgpt-citations](./reddit-chatgpt-citations/) | 10,118 | Five-engine citations on 100 consumer prompts plus the paired A/B that flipped Reddit back on in ChatGPT (August 2026) | [The ChatGPT Reddit Citation Collapse](https://organikpi.com/blog/geo-ai-search/chatgpt-reddit-citation-collapse/) |
| [chatgpt-citation-variance](./chatgpt-citation-variance/) | 2,642 | Every source ChatGPT consulted across 4 same-day runs, with attributed/dropped flags and fan-out subqueries (August 2026) | [ChatGPT Citation Variance Study](https://organikpi.com/blog/geo-ai-search/chatgpt-citation-variance-study/) |
| [chatgpt-query-fanout](./chatgpt-query-fanout/) | 219 | Every search query ChatGPT wrote for itself across 121 answers, with Keyword Planner status and the brands named before any search ran (August 2026, unrepeatable capture) | [ChatGPT Writes Its Own Search Query First](https://organikpi.com/blog/geo-ai-search/chatgpt-query-fanout-study/) |
| [ai-mode-organic-squeeze](./ai-mode-organic-squeeze/) | 160 | AI Overview presence, cited domains, and first-organic push-down on 160 commercial queries (July 2026) | [Ads Enter Google AI Mode](https://organikpi.com/blog/geo-ai-search/ads-in-google-ai-mode/) |

## Full study repos

The two text-fragment studies also have standalone repos with the complete pipeline (scripts, notebooks, charts); the datasets are mirrored here:

- [ai-citation-patterns](https://github.com/danishashko/ai-citation-patterns)
- [grounding-citation-analysis](https://github.com/danishashko/grounding-citation-analysis)
