# TikTok Shop Scraper: TikTok Scraper API for Python & Node.js (2026)

Scrape TikTok Shop products: price, discount, sold count, rating, reviews, seller, variants, stock and shipping. No login needed. Export JSON, CSV or Excel.

**[▶ Try the TikTok Shop Scraper free on Scrapely](https://scrape.ly/store/shelfbright/tiktok-shop-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape TikTok data with the [TikTok Shop Scraper](https://scrape.ly/store/shelfbright/tiktok-shop-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the tiktok scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this TikTok scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/shelfbright/tiktok-shop-scraper) or from your code with the SDK.
- **Structured tiktok data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $21.25 per 1,000 product results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when TikTok changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What TikTok data can you extract?

Scrape TikTok Shop products: price, discount, sold count, rating, reviews, seller, variants, stock and shipping. No login needed. Export JSON, CSV or Excel.

| Output field |
|---|
| `imageUrl` |
| `productTitle` |
| `productUrl` |
| `salePrice` |
| `listPrice` |
| `discountPercent` |
| `currency` |
| `soldCount` |
| `ratingAverage` |
| `reviewCount` |
| `sellerName` |
| `sellerUrl` |
| `countryCode` |
| `analysisBucket` |
| `sourceMode` |
| `sourceQuery` |

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('shelfbright/tiktok-shop-scraper').call({"keywords": ["wireless earbuds"], "maxResultsPerQuery": 20, "countries": ["US"], "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('shelfbright/tiktok-shop-scraper').call(run_input={ "keywords": [ "wireless earbuds" ], "maxResultsPerQuery": 20, "countries": [ "US" ], "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/shelfbright~tiktok-shop-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "keywords": [
    "wireless earbuds"
  ],
  "maxResultsPerQuery": 20,
  "countries": [
    "US"
  ],
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [TikTok Shop Scraper page](https://scrape.ly/store/shelfbright/tiktok-shop-scraper).

## Pricing

**$21.25 per 1,000 product results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/shelfbright/tiktok-shop-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape TikTok with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape TikTok with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a tiktok scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/shelfbright~tiktok-shop-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping TikTok legal?** This scraper collects publicly available data. Check TikTok's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Related TikTok scrapers

- [TikTok Scraper](https://github.com/alexrosuleks/tiktok-scraper): Scrape public TikTok videos from profiles, hashtags, video URLs, and keyword search, plus comments. Get captions, play,…

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** tiktok shop scraper, tiktok scraper, tiktok scraper api, tiktok scraper python, tiktok scraper node.js,
scrape tiktok, tiktok data extraction, tiktok crawler, tiktok api, export tiktok data to csv, tiktok-shop-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/shelfbright/tiktok-shop-scraper).
