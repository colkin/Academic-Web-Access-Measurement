# Academic Web Access Measurement — measuring access control on the agentic web

If you found this page from a `User-Agent` string or an `X-Research-Contact` header in your server logs, this page explains who we are and what we are doing.

> **To be excluded:** email [cybersecuritygroup@sdu.edu.cn](mailto:cybersecuritygroup@sdu.edu.cn) with the domain or domains. We remove them within one business day and never contact them again. No justification is needed and we will not ask for one.

## Who
*Jeffrey Chao, Shandong University* This is unfunded academic research. We are not affiliated with any AI company, crawler operator, CDN, or commercial data vendor, and no data collected here is sold or shared with one.

## What we are measuring
Websites increasingly express machine-access policy (`robots.txt`, `llms.txt`, Content Signals, licensing declarations) and increasingly enforce it differently for different automated clients. Almost nothing is publicly known about how far the declared policy and the actual enforcement agree, and the little that is published comes from vendor blog posts rather than peer-reviewed measurement.

We are collecting the first public, reproducible baseline of that gap across a large sample of websites, before and after the widely-announced change to AI crawler defaults on 15 September 2026.

## Exactly what we send you

| Parameter | Details |
| :--- | :--- |
| **Requests per domain** | About 20, spread over a few seconds, once per collection wave. |
| **Method** | `GET` only. Nothing is ever written, posted, or modified. |
| **Paths** | Your home page, and a fixed list of well-known policy paths: `robots.txt`, `llms.txt`, `ads.txt`, `/.well-known/ai.txt`, `/.well-known/rsl.xml`, `/.well-known/http-message-signatures-directory`, and one deliberately non-existent control path used to detect soft-404 behaviour. |
| **Depth** | Zero. We do not follow links, we do not enumerate your site, and we never request a page we did not name above. |
| **Authentication** | Never attempted, never bypassed. We send no credentials, no cookies, and we do not attempt to defeat any bot-management challenge, CAPTCHA, or paywall. A challenge or a block is itself the measurement result, and we record it and move on. |
| **Rate limits** | Honoured. On `429` or `503` we respect `Retry-After`, and after the second such response we abandon the domain entirely for that wave rather than retrying under a different identity. |
| **Waves** | Six collections total, three before and three after 15 September 2026. |

## How to recognise us
Every request carries an `X-Research-Contact` header naming this page. Requests additionally carry one of a fixed set of `User-Agent` strings, each ending in the study identifier:

```text
... Academic Web Access Measurement/1.0 (+https://github.com/colkin/Academic-Web-Access-Measurement)
