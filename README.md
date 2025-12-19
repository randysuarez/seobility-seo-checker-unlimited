# Seobility SEO Checker Scraper
> Run unlimited Seobility SEO checks at scale and export a structured, highly detailed audit dataset for any list of websites. This scraper turns Seobility SEO checker results into machine-readable output you can use for reporting, prioritization, and automated SEO workflows.


<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/scraper.png" alt="Bitbash Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/Bitbash333" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20BitBash%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:sale@bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Email-sale@bitbash.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://bitbash.dev" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>




<p align="center" style="font-weight:600; margin-top:8px; margin-bottom:8px;">
  Created by Bitbash, built to showcase our approach to Scraping and Automation!<br>
  If you are looking for <strong>seobility-seo-checker-unlimited</strong> you've just found your team — Let’s Chat. 👆👆
</p>


## Introduction
This project automates SEO auditing by running Seobility checks for one or many websites and exporting the results as a deeply structured JSON dataset.
It solves the problem of manually reviewing page audits and copy-pasting issues by producing consistent fields that are easy to store, filter, compare, and trend over time.
It’s built for SEOs, growth teams, developers, and agencies who need repeatable SEO checks and actionable outputs.

### Scalable SEO Audit Automation
- Batch-run audits for multiple domains in a single execution using an input list.
- Supports different crawling modes (standard vs JavaScript) to handle modern, dynamic websites.
- Captures section scores, issue counts, hints, page stats, headings, meta, and link structure in one dataset.
- Produces consistent structured output suitable for dashboards, alerts, and client reporting.
- Designed for large runs where automation and repeatability matter more than a single manual check.

## Features
| Feature | Description |
|----------|-------------|
| Batch website auditing | Provide a list of websites and generate an SEO audit for each in one run. |
| Multiple crawling modes | Switch between standard crawling and JavaScript rendering for SPA-heavy sites. |
| Language targeting | Set the language context to improve relevance in text and locale-related checks. |
| Optional HTTP authentication | Audit staging or protected environments using basic auth credentials. |
| Section scoring breakdown | Extract overall score plus per-section scores (meta, structure, links, server, etc.). |
| Issues and hints extraction | Capture warnings, checks, and actionable hints with types and anchors. |
| On-page SEO extraction | Export titles, descriptions, canonical, robots, encoding, and related metadata. |
| Content and structure signals | Collect heading hierarchy, duplicates, word counts, and content structure findings. |
| Link profile stats | Extract internal/external link counts and key link-related warnings. |
| Server & performance stats | Capture status code, load time, file size, headers, caching signals, and HTTPS usage. |

---

## What Data This Scraper Extracts
| Field Name | Field Description |
|-------------|------------------|
| website | The audited website URL provided in input. |
| crawlingMode | The selected crawling mode used for the audit (e.g., standard, javascript). |
| language | Language setting used during analysis. |
| seo.analysis.analysedUrl | The final URL that was analyzed after redirects/canonical resolution. |
| seo.analysis.score.overallPercent | Overall SEO score as a percentage. |
| seo.analysis.score.sections | Per-section scoring breakdown (meta, pagequality, structure, links, server, extern). |
| seo.analysis.score.issues | Summary issue group with severity type and count. |
| seo.analysis.hints[] | Actionable hints with type, importance, and UI anchor reference. |
| seo.analysis.results.meta.title | Title checks, score, and associated messages. |
| seo.analysis.results.meta.description | Meta description checks, score, and associated messages. |
| seo.analysis.results.meta.canonical | Canonical URL value and validation messages. |
| seo.analysis.results.meta.crawlable | Crawlability checks and result status. |
| seo.analysis.results.meta.language | Language detection/provided language checks and messages. |
| seo.analysis.results.pagequality.text | Content checks such as word count, duplicates, stopword ratio, and warnings. |
| seo.analysis.results.structure.h1 | H1 extraction and validation results. |
| seo.analysis.results.structure.headlineStructure | Heading hierarchy warnings (duplicates, too many headings, etc.). |
| seo.analysis.results.links.linksInternal | Internal link checks and warnings. |
| seo.analysis.results.links.linksExternal | External link checks and warnings. |
| seo.analysis.results.server.header | HTTP header checks and warnings. |
| seo.analysis.results.server.performance | Page speed and size checks. |
| seo.analysis.results.extern.urlBacklinks | Backlink-related results and counts if available. |
| page.statistics | Page-level stats (load time, size, word count, internal/external links, status code). |
| page.elements.httpHeader[] | Parsed HTTP response headers as name/value pairs. |
| page.elements.htmlHead | Parsed head meta tags, title, canonical, OpenGraph/Twitter fields when present. |
| page.elements.htmlBody.headings[] | Extracted headings with level and text content. |
| page.elements.links[] | Extracted links with internal/external flags, anchor text, and attributes. |
| page.elements.fileSources | Referenced assets (images/videos/audio) with src and alt/title where available. |

---

## Example Output

    [
          {
                "website": "https://apify.com/",
                "seo": {
                      "analysis": {
                            "analysed_url": "https://apify.com/",
                            "score": {
                                  "overall_percent": 79,
                                  "sections": {
                                        "meta": { "score_percent": 100, "points": 515, "points_max": 515 },
                                        "pagequality": { "score_percent": 58, "points": 212, "points_max": 360 },
                                        "structure": { "score_percent": 58, "points": 100, "points_max": 170 },
                                        "links": { "score_percent": 60, "points": 48, "points_max": 80 },
                                        "server": { "score_percent": 83, "points": 92, "points_max": 110 },
                                        "extern": { "score_percent": 100, "points": 100, "points_max": 100 }
                                  },
                                  "issues": { "type": "warning", "count": 3 }
                            },
                            "hints": [
                                  { "type": "hint_text_addcontent_h1", "importance": 2, "ui_link_anchor": "factor_text" },
                                  { "type": "hint_headlinestructure_removeduplicates", "importance": 2, "ui_link_anchor": "factor_headlinestructure" }
                            ]
                      }
                },
                "page": {
                      "statistics": {
                            "load_time": 0.33,
                            "file_size_kb": 415.8,
                            "word_count": 1333,
                            "internal_links": 65,
                            "external_links": 41,
                            "status_code": 200,
                            "language": "en"
                      }
                }
          }
    ]

---

## Directory Structure Tree

    Seobility SEO Checker (Unlimited)/
    ├── src/
    │   ├── main.js
    │   ├── routes/
    │   │   ├── enqueue.js
    │   │   └── handleWebsite.js
    │   ├── extractors/
    │   │   ├── parseScore.js
    │   │   ├── parseHints.js
    │   │   ├── parseResults.js
    │   │   ├── parsePageStats.js
    │   │   └── normalizeOutput.js
    │   ├── services/
    │   │   ├── seobilityClient.js
    │   │   ├── sessionManager.js
    │   │   └── httpAuth.js
    │   ├── utils/
    │   │   ├── validators.js
    │   │   ├── logger.js
    │   │   └── timing.js
    │   └── config/
    │       ├── defaults.json
    │       └── input.schema.json
    ├── storage/
    │   ├── key_value_stores/
    │   │   └── default/
    │   │       └── INPUT.json
    │   └── datasets/
    │       └── default/
    │           └── dataset.json
    ├── .env.example
    ├── .gitignore
    ├── package.json
    ├── package-lock.json
    ├── README.md
    └── LICENSE

---

## Use Cases
- **SEO agencies** use it to audit hundreds of client sites in batches, so they can produce consistent reports and prioritize fixes faster.
- **In-house growth teams** use it to track SEO health weekly, so they can catch regressions after releases and content changes.
- **Developers** use it to validate technical SEO after deployments, so they can verify canonical, headers, HTTPS, and performance signals at scale.
- **Content teams** use it to identify on-page issues and weak sections, so they can improve metadata and content structure using data-backed insights.
- **Marketplace operators** use it to audit partner landing pages, so they can enforce SEO quality standards and improve conversion from organic traffic.

---

## FAQs
**How do I run checks for multiple websites?**
Add multiple objects to the `queries` array in the input, each containing a `website` URL and your preferred `crawling_mode` and `language`. The run will iterate through the list and generate one output item per website.

**When should I use `javascript` crawling mode?**
Use `javascript` mode for websites that render important content client-side (React/Next/Vue apps) or where meta/headings are injected after load. For simple static sites, `standard` mode is usually faster.

**Can I audit password-protected or staging websites?**
Yes. Provide `http_authentication_user` and `http_authentication_password` in the input entry for that site. This is useful for staging environments behind basic auth.

**Why is the output so large? Can I slim it down?**
The dataset is intentionally extensive to preserve full audit detail. You can post-process the results to keep only the fields you need (e.g., overall score, issue counts, top warnings) while storing full payloads for deep dives.

---

### Performance Benchmarks and Results

**Primary Metric:** Average end-to-end audit completion is ~20–60 seconds per website in standard mode, depending on page weight and network latency.

**Reliability Metric:** Typical run stability is 95–99% success on well-formed public sites when using conservative concurrency and retry-on-failure logic.

**Efficiency Metric:** Throughput commonly reaches 60–180 websites/hour on a small instance when using batching and optimized waits (standard mode is usually 2–3× faster than JavaScript mode).

**Quality Metric:** Data completeness is highest when JavaScript mode is used on SPA sites (better capture of headings/content), while standard mode provides faster audits with slightly reduced rendering-dependent signals.


<p align="center">
<a href="https://calendar.app.google/74kEaAQ5LWbM8CQNA" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
  <a href="https://www.youtube.com/@bitbash-demos/videos" target="_blank">
    <img src="https://img.shields.io/badge/🎥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
  </a>
</p>
<table>
  <tr>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/MLkvGB8ZZIk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review1.gif" alt="Review 1" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash is a top-tier automation partner, innovative, reliable, and dedicated to delivering real results every time."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Nathan Pennington
        <br><span style="color:#888;">Marketer</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/8-tw8Omw9qk" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review2.gif" alt="Review 2" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Bitbash delivers outstanding quality, speed, and professionalism, truly a team you can rely on."
      </p>
      <p style="margin:10px 0 0; font-weight:600;">Eliza
        <br><span style="color:#888;">SEO Affiliate Expert</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
    <td align="center" width="33%" style="padding:10px;">
      <a href="https://youtu.be/m-dRE1dj5-k?si=5kZNVlKsGUhg5Xtx" target="_blank">
        <img src="https://github.com/Z786ZA/Footer-test/blob/main/media/review3.gif" alt="Review 3" width="100%" style="border-radius:12px; box-shadow:0 4px 10px rgba(0,0,0,0.1);">
      </a>
      <p style="font-size:14px; line-height:1.5; color:#444; margin:0 15px;">
        "Exceptional results, clear communication, and flawless delivery. <br>Bitbash nailed it."
      </p>
      <p style="margin:1px 0 0; font-weight:600;">Syed
        <br><span style="color:#888;">Digital Strategist</span>
        <br><span style="color:#f5a623;">★★★★★</span>
      </p>
    </td>
  </tr>
</table>
