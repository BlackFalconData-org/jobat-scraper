# Jobat.be Jobs Scraper - Belgium Job Board

Extract structured data from [jobat.be](https://jobat.be) — jobat.be - Belgium's leading job board with 80K+ listings in Dutch and French. Structured salary, 3 description formats, and employer contact data.

**[Jobat.be Jobs Scraper - Belgium Job Board on Apify →](https://apify.com/blackfalcondata/jobat-scraper?fpr=1h3gvi)**

---

## Key features


**Search with filters** — Search by keyword and location. Filter by language, and more.

**Detail enrichment** — Fetch full job descriptions, salary data, employer profiles, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

**Change classification** — Track cross-run repost detection across runs. Build audit trails of how listings evolve over time.

**Compact output** — Emit core fields only (AI-agent / MCP-friendly). Keeps response size small for LLM workflows.

**Description truncation** — Cap description length per listing to control output size and cost.

**Result cap** — Stop after N listings (up to 5.000). Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases


**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from jobat.be on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from jobat.be.

**Change monitoring**
Run daily or hourly in incremental mode to capture only new, updated, or expired listings. Perfect for price-tracking, churn analysis, and alerting pipelines.

**Lead generation**
Extract employer contact details alongside listings to build outreach lists for recruiters, staffing agencies, or B2B sales teams.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
{
  "query": "developer",
  "maxResults": 10,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `query` | string | — | Job search keywords. |
| `location` | string | — | City or region in Belgium. |
| `language` | enum | `"nl"` | Listing language. Dutch (nl) for Flanders, French (fr) for Wallonia/Brussels. |
| `maxResults` | integer | `50` | Maximum total results (0 = unlimited). |
| `includeDetails` | boolean | `true` | Fetch full job details (description, profile, offer, contact info). |
| `descriptionMaxLength` | integer | `0` | Truncate description to N chars. 0 = no truncation. |
| `compact` | boolean | `false` | Core fields only (for AI-agent/MCP workflows). |
| `incrementalMode` | boolean | `false` | Compare against previous run state. |
| `stateKey` | string | — | Stable identifier for tracked universe. |
| `skipReposts` | boolean | `false` | Exclude listings detected as reposts of previously seen jobs. |

---

## Output fields

Every listing returns the same 34-field schema. Missing values are `null` — never omitted.

- `jobId`
- `title`
- `company`
- `companyUrl`
- `location`
- `region`
- `description`
- `descriptionHtml`
- `descriptionMarkdown`
- `profile`
- `offer`
- `contractType`
- `employmentType`
- `salaryText`
- `salaryMin`
- `salaryMax`
- `salaryCurrency`
- `salaryType`
- `benefits`
- `email`
- `phone`
- `applyUrl`
- `companyWebsite`
- `category`
- `subCategory`
- `functionType`
- `sector`
- `postedAt`
- `url`
- `portalUrl`
- `scrapedAt`
- `language`
- `source`
- `changeType`

---

## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "jobId": "0f9a5ed43c85fa149a9a3d4689a4e62f4863f5e744b9453d0925687732fa3e36",
  "title": "REMOTE BUSINESS DEVELOPER – EVENT AGENCY (FLANDERS)",
  "company": "egg Events",
  "companyUrl": "https://www.jobat.be/nl/jobs/bedrijven/egg-events/119208",
  "location": "Brussel",
  "region": "Brussels",
  "description": "Werken bij egg is niet zomaar een job. Het gaat erom sterke en inspirerende ervaringen te creëren voor onze klanten en hun doelgroepen.\n\nWe werken hard om die magie tot stand te br…",
  "descriptionHtml": "Werken bij egg is niet zomaar een job. Het gaat erom sterke en inspirerende ervaringen te creëren voor onze klanten en hun doelgroepen.<br><br>We werken hard om die magie tot stand…",
  "descriptionMarkdown": "Werken bij egg is niet zomaar een job. Het gaat erom sterke en inspirerende ervaringen te creëren voor onze klanten en hun doelgroepen.\n\nWe werken hard om die magie tot stand te br…",
  "profile": "En zo komen we bij jou.\n\nVastberaden en met een groeimindset floreer je in het creëren van nieuwe businesskansen en het sluiten van deals, terwijl je een uitstekende klantervaring …",
  "offer": "Wat wij bieden\n- Een contract van 6 maanden met mogelijkheid tot verlenging of een vaste aanstelling\n- Een dynamische en inclusieve bedrijfscultuur waar we hard werken om de juiste…",
  "contractType": "Bepaalde duur"
}
```

*Truncated — full records contain 34 fields. See Output fields for the complete schema.*

**[Try Jobat.be Jobs Scraper - Belgium Job Board now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/jobat-scraper?fpr=1h3gvi)**

---

## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.005 |
| Result | $0.003 |

See the [actor on Apify](https://apify.com/blackfalcondata/jobat-scraper?fpr=1h3gvi) for current pricing.

---

## FAQ

**How do I scrape jobat.be?**
Use this actor on Apify to extract structured data from jobat.be. Configure your search query and filters in the input, then click Start — no coding required.

**How do I get jobat.be data as JSON, CSV, or Excel?**
The actor writes each listing to Apify's dataset. Download as JSON, CSV, or Excel from the Console, stream via the API, or push to Make, Zapier, Airbyte, or Keboola.

**Is it legal to scrape jobat.be?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check jobat.be's terms of service for your specific use case.

**How much does it cost?**
Pay-per-event pricing — you only pay for listings extracted. Apify's free $5 credit is enough to run thousands of results before you pay anything.

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage. Expired listings can be tracked separately.

**Do I need an API key or credentials?**
No. Just sign up for Apify, paste your input, and click Start. No credit card required.

---

## Related products by Black Falcon Data


- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board
- [Naukri Scraper](https://apify.com/blackfalcondata/naukri-scraper?fpr=1h3gvi) — India's largest job portal

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. Sign up — $5 platform credit included
2. Open [Jobat.be Jobs Scraper - Belgium Job Board](https://apify.com/blackfalcondata/jobat-scraper?fpr=1h3gvi) and configure your input
3. Click **Start** — export results as JSON, CSV, or Excel

Need more later? [See Apify pricing](https://apify.com/pricing?fpr=1h3gvi).

---

## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

*Last updated: 2026 04*
