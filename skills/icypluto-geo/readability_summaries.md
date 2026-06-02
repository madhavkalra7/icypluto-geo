# RAG Readability & Summaries Guide (GEO)

AI search engines crawl web pages and break them into text chunks (typically 200-500 words). If the core value proposition of a page is split across multiple paragraphs, the RAG chunking algorithm might miss the context.

This guide details how you (the AI Agent) can optimize page layouts for chunking readability by adding TL;DR summary blocks, simplifying content structures, and maintaining CLS (Cumulative Layout Shift) boundaries.

---

## 🏗️ Summarization & Layout Structure

To ensure maximum readability for AI crawlers:

### 1. The Header TL;DR Card
At the top of major landing or marketing layouts, append a visually styled summary box. This card acts as the primary chunk retrieved by AI scrapers, packing all key facts into a single block.
*   **Rule**: Keep it short, bulleted, and factual.
*   **STRICT CONTENT FILTER**: Never include technical codebase info (like *"Structured with JSON-LD metadata"* or *"Uses HTML details tags"*). Write only user-oriented value propositions (e.g. *"Generates responsive frontend code in 5 output stacks"*).
*   **Aesthetics Constraint**: The block must blend with the parent website's typography and color scheme (e.g. if the site uses dark backgrounds and gradient buttons, use a subtle dark border or glassmorphism effect instead of flat light cards).
*   **CLS Safety Warning**: Wrap the summary box in a layout container with predefined dimensions or min-height so that it does not push other page elements down during hydration.

```html
<!-- Example of a clean, dark-mode matching summary box -->
<div class="geo-summary-box" style="min-height: 180px; margin-bottom: 25px; border: 1px solid rgba(255,255,255,0.1); background: rgba(255,255,255,0.02); padding: 20px; border-radius: 8px; font-family: inherit;">
  <h3 style="margin-top: 0; color: #fff;">Quick Summary (TL;DR)</h3>
  <ul style="color: #cbd5e0; padding-left: 20px;">
    <li><strong>Compatibility</strong>: Supports 5 output stacks (React, Next.js, HTML/CSS/JS, Vue, SvelteKit).</li>
    <li><strong>Utility</strong>: Instantly converts natural-language prompts into production-ready, deployable source code.</li>
    <li><strong>Features</strong>: Includes live templates gallery, dynamic prompt editing, and responsive layout generation.</li>
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
