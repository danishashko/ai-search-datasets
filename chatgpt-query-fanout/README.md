# ChatGPT Query Fan-Out (219 queries, August 2026)

**207 of 209 unique queries ChatGPT wrote for itself return no search volume in Google's Keyword Planner. 70 of them Google Ads refuses outright for exceeding its keyword length cap.**

When ChatGPT decides to search the web, it does not pass your question through. It writes its own query first. This dataset is 219 of those queries, captured alongside the 121 user prompts that produced them.

Article: https://organikpi.com/blog/geo-ai-search/chatgpt-query-fanout-study/

## Files

| File | Rows | Unit |
|---|---|---|
| `fanout_queries.csv` | 219 | one fan-out query |
| `fanout_captures.csv` | 121 | one captured answer |

### `fanout_queries.csv`

| Field | Meaning |
|---|---|
| `capture_id` | joins to `fanout_captures.csv` |
| `user_prompt` | what the person typed |
| `fanout_query` | what ChatGPT typed into the search box |
| `word_count`, `char_count` | length of the fan-out query |
| `has_year_token` | 1 if the query carries a four-digit year |
| `has_site_operator` | 1 if the query uses `site:` |
| `has_official` | 1 if the query contains the word "official" |
| `has_quoted_phrase` | 1 if the query uses a quoted exact phrase |
| `entities_not_in_prompt` | pipe-separated companies, products or publications named in the query but absent from the prompt |
| `entity_count` | count of the above |
| `keyword_planner_status` | `has_volume`, `no_volume_record`, or `rejected_over_length_cap` |
| `google_ads_search_volume` | monthly US volume where one exists; `0` where the keyword was accepted but has no record; blank where rejected |

### `fanout_captures.csv`

| Field | Meaning |
|---|---|
| `capture_id` | join key |
| `user_prompt` | the prompt |
| `user_prompt_words` | its length |
| `fanout_query_count` | how many searches that one question produced |
| `distinct_entities_injected` | entities across all of that capture's queries |
| `entities_injected` | pipe-separated list |
| `source_file` | which capture run the row came from |

## Method

Captured 2026-08-16 through Bright Data's ChatGPT scraper, US exit, logged out. The
scraper's `web_search_query` field holds the searches the model issues; 121 of the
captures fired a web search and carried one or more.

Keyword Planner status was pulled 2026-09-16 from Google Ads through DataForSEO,
location 2840 (United States), language `en`. Google Ads accepts a keyword of at
most 80 characters and 10 words; anything longer is rejected rather than returned
with a zero.

Entity matching runs on word boundaries against a hand-built list of companies,
products and publications. Generic tokens that appear inside product names (CMS,
GEO, Ultra, Detect) are excluded, so `entity_count` is a floor.

## Limits

- One engine. ChatGPT only. Google AI Mode exposes no equivalent field.
- Logged out, US, single session window. No personalization arm.
- The two queries with volume are worth reading before quoting the headline.
  `how to remove a stripped screw` is the one case where the model did not rewrite
  the prompt at all. `site:zoho.com crm pricing` only registers because Google Ads
  strips the operator and matches the remaining words.
- 121 captures is enough for the shape of a fan-out query and not enough for a
  stable per-category rate. The shortlist-shaped split (18 of 27) is reported with
  its raw counts for that reason.
- **The capture is not repeatable.** `web_search_query` returned data on
  2026-08-16 and returns `null` as of 2026-09-15, on the same code path, with
  `web_search_triggered` still true. That is why this dataset exists and why a
  fresh pull cannot extend it.

## Relationship to the citation-variance dataset

The raw `fanout_query` strings also appear as a `fanout_queries` column in
[`chatgpt-citation-variance`](../chatgpt-citation-variance/), published August 2026
alongside a study about which sources survive repeat runs. This folder is the
query-level cut of the same captures: one row per query rather than per cited URL,
with Keyword Planner status, length, operator use and entity injection added.

## License

CC BY 4.0. Attribution: OrganiKPI.
