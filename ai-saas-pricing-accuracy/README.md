# ChatGPT and Gemini SaaS price answers

**Gemini gave a stale or wrong price in 12.8% of answers about SaaS tools that changed their pricing, ChatGPT in 5.7%.** Most errors are the old price: 83.5% of errors on changed tools (71 of 85 answers) match a price the vendor no longer charges.

Source article: [Why ChatGPT and Gemini Quote Old SaaS Prices](https://organikpi.com/blog/geo-ai-search/ai-answers-saas-pricing-wrong/) (canonical version of this dataset and the full analysis).

## Key numbers

- 116 SaaS tools, 2 prompts, 3 runs per engine: 1,388 answers (US, 12 October 2026)
- Tools that changed pricing: Gemini 12.8% (59 of 462 answers), ChatGPT 5.7% (26 of 460) stale or wrong
- Tools that did not change: 2.6% (12 of 466 answers) wrong
- Removed plans are misquoted most: 11.5% (65 of 563 answers)
- ChatGPT hedges in 51.9% of answers (359 of 692), Gemini in 2.0% (14 of 696)

## Files

| File | Format | Size |
|---|---|---|
| `organikpi-ai-saas-pricing-accuracy-2026-10.json` | JSON | 4.2 MB |
| `organikpi-ai-saas-pricing-accuracy-2026-10.csv` | CSV | 1.6 MB |

One row per price claim. Answers with no price claim have one row with empty claim fields.

## Fields

| Field | Description |
|---|---|
| `tool` | SaaS tool asked about |
| `domain` | the tool's website |
| `group` | `changed` (pricing changed between an archived copy from November 2025 to February 2026 and October 2026, 77 tools) or `control` (unchanged, 39 tools) |
| `change_type` | for changed tools: `price_move`, `plan_removed`, `rename_only`, joined with `+` when a tool has several |
| `engine` | `chatgpt` or `gemini` |
| `run` | run number, 1 to 3 |
| `prompt` | the exact prompt asked |
| `answer_verdict` | worst label in the answer: `wrong`, then `stale`, then `correct`, then `no_price` (no price that could be checked) |
| `answer_hedged` | true if the answer tells the reader to check the vendor's page or says prices may change |
| `claim_index` | position of the claim in the answer |
| `plan` | plan name as the answer stated it |
| `amount` | price as the answer stated it |
| `billing` | billing period as the answer stated it |
| `claim_label` | `correct` (matches a live price in any billing state, within $1 or 2%), `stale` (matches only the old price, or a plan that exists only on the old ladder), `wrong` (live plan, live price visible, matches neither), `unverifiable` (add-ons, usage rates, custom tiers, another product, anything the saved pages cannot settle) |

## Method

Each prompt was asked three times per engine from a US location. Every price was graded against the vendor's live pricing page captured the same day and the archived old page, in three passes with a strict final pass for stale and wrong labels. Error rates are a floor: a price counts as correct if it matches the live page in any billing state captured. Full methodology in the source article.

## License

CC BY 4.0. Use it freely, credit the [source article](https://organikpi.com/blog/geo-ai-search/ai-answers-saas-pricing-wrong/).
