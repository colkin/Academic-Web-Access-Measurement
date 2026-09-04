# Academic Web Access Measurement Study — Measuring Access Control on the Agentic Web

If you found this page from a `User-Agent` string or an `X-Research-Contact` header in your server logs, this page explains who we are and what we are doing.

> **To be excluded:** Please email **REPLACE-WITH-CONTACT@EXAMPLE.EDU** with the domain or domains you would like to exclude. We will remove them within one business day and will never contact you again. No justification is needed, and we will not ask for one.

## Who

**REPLACE — researcher name, group, department, institution.**

This is unfunded academic research. We are not affiliated with any AI company, crawler operator, CDN, or commercial data vendor, and no data collected here is sold or shared with any of them.

## What We Are Measuring

Websites increasingly express machine-access policies through mechanisms such as `robots.txt`, `llms.txt`, Content Signals, and licensing declarations. They may also enforce these policies differently for different types of automated clients.

Very little is publicly known about how closely declared policies correspond to actual enforcement behavior. The limited existing evidence largely comes from vendor reports and blog posts rather than independent, peer-reviewed measurement.

We are collecting a public, reproducible baseline of this gap across a large sample of websites, before and after the widely announced change to AI crawler defaults on **15 September 2026**.

## Exactly What We Send You

| Item | Details |
|---|---|
| **Requests per domain** | About 20, spread over a few seconds, once per collection wave. |
| **Method** | `GET` only. Nothing is ever written, posted, or modified. |
| **Paths** | Your home page and a fixed list of well-known policy paths: `/robots.txt`, `/llms.txt`, `/ads.txt`, `/.well-known/ai.txt`, `/.well-known/rsl.xml`, `/.well-known/http-message-signatures-directory`, and one deliberately non-existent control path used to detect soft-404 behavior. |
| **Depth** | Zero. We do not follow links, enumerate your site, or request any page we did not name above. |
| **Authentication** | Never attempted and never bypassed. We send no credentials or cookies, and we do not attempt to defeat bot-management challenges, CAPTCHAs, or paywalls. A challenge or block is itself a measurement result; we record it and move on. |
| **Rate limits** | Honored. On `429` or `503`, we respect `Retry-After`. After the second such response, we abandon the domain entirely for that wave rather than retrying under a different identity. |
| **Waves** | Six collections total: three before and three after 15 September 2026. |

## How to Recognize Us

Every request carries an `X-Research-Contact` header naming this page.

Requests additionally carry one of a fixed set of `User-Agent` strings, each ending in the study identifier:

    ... AcademicCrawlerStudy/1.0 (+REPLACE-WITH-THIS-PAGE-URL)

To measure how sites treat different classes of automated clients, some of these strings contain crawler tokens published by commercial operators, for example:

    GPTBot
    ClaudeBot
    Googlebot

**We are not those operators and we do not claim to be.**

The study suffix is present precisely so that this is unambiguous in your logs, and the requests originate from our own address, not from any operator's published ranges.

This technique is long-established in web measurement research and has been used to study differential treatment of automated clients. It is used here solely to observe how websites respond to different client classifications from the outside.

## What We Keep

We store:

- HTTP status codes
- A selected set of response headers
- Response sizes
- Content hashes
- Derived classification labels

Public policy files such as `robots.txt` and similar files are retained in full because they are the objects of study.

For all other responses, we retain at most the first **1 KB**, which is sufficient to distinguish a normally served page from an interstitial challenge or similar response.

We never republish raw page content.

Any public release consists only of:

- Aggregate statistics
- The target list
- Hashes
- Derived labels

## Legal and Ethical Basis

All requests are read-only retrievals of publicly reachable resources on public web servers.

Requests are:

- Sent using `GET` only
- Sent at a rate far below ordinary human browsing
- Identified through an `X-Research-Contact` header
- Associated with an identified research operator
- Covered by a working opt-out mechanism

We do not circumvent access controls or request non-public resources.

We do not:

- Attempt authentication
- Submit credentials
- Send cookies
- Bypass CAPTCHAs
- Defeat bot-management challenges
- Bypass paywalls
- Circumvent other technical access controls

**REPLACE — institutional ethics review reference or exemption determination, once obtained.**

---

**Last updated:** September 4, 2026

**Contact:** cybersecuritygroup@sdu.edu.cn
