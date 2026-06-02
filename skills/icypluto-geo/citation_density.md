# Factual Citation & Stats Guide (GEO)

Generative AI search models (like Perplexity and SearchGPT) utilize retrieval systems that scan web content for objective, verifiable claims. They discount generic, high-adjective marketing descriptions. 

This guide details how you (the AI Agent) can optimize content copy by injecting quantitative metrics, statistics, and external citations.

---

## 🔬 Core Copywriting Rules for AI Search

To make your copy highly attractive to search grounded LLMs, apply these rules:

1.  **Quantitative Substantiation**: Every primary claim must be backed by a number, rate, time, or comparative percentage.
2.  **Citation Anchor Tags**: Reference recognized reports, open standards, or third-party benchmarks using HTML anchor tags or Markdown links. LLM retrieval algorithms identify citation link graphs to calculate authority.
3.  **Factual Sentence Patterns**: Use clear, declarative syntax. Avoid passive voice or vague qualifiers (e.g. *often*, *generally*, *extremely*).

---

## 🛠️ Step-by-Step Copy Optimization

### Step 1: Scan Content for Subjective Adjectives
Look for copy sections that describe features using adjectives.
*   *Avoid*: *"We use next-generation security to protect your database with high speed."*
*   *GEO Issue*: This has zero factual weight.

### Step 2: Inject Verifiable Stats
Rewrite the copy to include concrete numbers. If the exact metrics are not defined in the workspace:
- Check the codebase for parameters (like encryption keys, timeout lengths).
- Use industry-standard benchmarks (e.g. `256-bit AES encryption`, `99.9% uptime`) and log a comment detailing the baseline.
*   *Optimize*: *"Our platform protects your database using 256-bit AES encryption and achieves less than 50ms processing latency under peak concurrent loads."*

### Step 3: Embed Citation Links (Reference Anchors) & Filter Dev Links
When adding reference links, they must be relevant to the business/niche, **never** to software development docs.
*   **STRICT BAN**: Do not link to `nextjs.org`, `developer.mozilla.org` (MDN), `react.dev`, `google.com/search-console`, or other developer documentation inside user-facing pages.
*   **Allowed Link Types**: 
    - Niche industry stats (e.g. *"Our builder accelerates layout assembly by 3x based on the [2026 AI Developer Survey](https://industryreport.com)"*).
    - Internal pages of the site (e.g., pointing to `/pricing`, `/docs/features`, or `/about`).
*   **Rule of Thumb**: If no natural external industry study is available, **do not inject any external links in the hero or main summaries**. Keep the text as flat, factual numbers. Do not manufacture random citations.

---

## 📋 Copy Translation Matrix (Before vs After)

Use this table to translate generic copy into GEO-optimized copy:

| Subjective (Avoid) | Factual/GEO (Inject) |
| :--- | :--- |
| *"Our pricing plans are very cheap and affordable."* | *"Our pricing starts at $0.00 for the free tier, with premium plans starting at $49.00 per month."* |
| *"We track competitors instantly across the web."* | *"We scrape search rankings and mentions across 3 search engines, calculating competitor SOV scores in under 5 seconds."* |
| *"Our website is optimized to load super fast."* | *"Our landing page features an average Largest Contentful Paint (LCP) time of 1.8 seconds."* |
