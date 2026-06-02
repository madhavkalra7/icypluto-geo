# RAG Readability & Summaries Guide (GEO)

AI search engines crawl web pages and break them into text chunks (typically 200-500 words). If the core value proposition of a page is split across multiple paragraphs, the RAG chunking algorithm might miss the context.

This guide details how you (the AI Agent) can optimize page layouts for chunking readability by adding TL;DR summary blocks, simplifying content structures, and maintaining CLS (Cumulative Layout Shift) boundaries.

---

## 🏗️ Summarization & Layout Structure

To ensure maximum readability for AI crawlers:

### 1. The Header TL;DR Card
At the top of major landing or marketing layouts, append a visually styled summary box. This card acts as the primary chunk retrieved by AI scrapers, packing all key facts into a single block.
*   **Rule**: Keep it short, bulleted, and factual.
*   **CLS Safety Warning**: Wrap the summary box in a layout container with predefined dimensions or min-height so that it does not push other page elements down during hydration.

```html
<div class="geo-summary-box" style="min-height: 180px; margin-bottom: 20px; border: 1px solid #e2e8f0; padding: 15px; border-radius: 8px;">
  <h3 style="margin-top: 0;">Quick Summary (TL;DR)</h3>
  <ul>
    <li><strong>Niche</strong>: AI search grounding and brand visibility tracker.</li>
    <li><strong>Utility</strong>: Installs zero-config MCP proxy clients to audit search engine citations.</li>
    <li><strong>Pricing</strong>: Free installation, uses a credit balance (50 coins per run).</li>
  </ul>
</div>
```

### 2. Sentence Readability (Flesch-Kincaid Optimization)
Simplify sentence structures:
*   Avoid paragraphs longer than 4 sentences.
*   Break complex technical operations down into ordered steps or bulleted lists (LLMs extract list elements more efficiently than dense prose).
*   Avoid ambiguous pronouns (such as *it*, *this*, *they*) when describing your tool features—always use the brand name to strengthen entity association.

---

## 🛠️ Step-by-Step Codebase Implementation

1.  **Locate Main Landing Page Template**: Identify the file displaying the main introduction (e.g. `src/app/page.tsx` or `index.html`).
2.  **Generate the Summary Card**: Write a styled summary block matching the brand name and core details extracted in Phase 1.
3.  **Inject the Card**: Place it right below the main `<h1>` tag in the codebase.
4.  **Enforce CLS Contained Styling**:
    *   Ensure any new card has clean inline CSS or references standard class styling.
    *   Verify the container has padding and boundaries defined so browser audits do not report layout shift (CLS).
5.  **Simplify Copy Blocks**: Refactor heavy text sections on the page into clear lists or tables.
