# Competitor Comparisons Guide (GEO)

When users query AI models with comparative prompts (such as *"What are the key differences between Brand A and Brand B?"* or *"Who is the best alternative to [Competitor]?"*), LLMs parse comparative structures to extract key details.

This guide details how you (the AI Agent) can create and inject comparison tables and differentiator lists to capture recommendations in competitive AI search queries, **while ensuring layout shift safety (CLS)**.

---

## 📊 Designing Comparison Matrices for AI Parsing

To structure comparison tables so they are easily read and ingested by RAG scrapers:

1.  **Factual Grid Layout**: Build clean HTML `<table>` elements with descriptive headers.
2.  **Define Key Differentiators**: Focus on objective metrics (like pricing, processing speed, APIs, schema, platform setup) rather than opinionated adjectives.
3.  **CLS Containment styling**: Tables can shift layouts dramatically when rendering on mobile viewports or dynamically rendering rows. Wrap the table in a container with a defined `min-height` and overflow properties to maintain a stable layout.

---

## 🛠️ Step-by-Step Codebase Implementation

### Step 1: Resolve Competitors
Scan only public-facing documentation, README files, or description tags (as instructed in [SKILL.md](./SKILL.md)) to identify the primary target competitors. Do not scan codebase files containing configuration settings, credentials, or private repository files.

### Step 2: Inject the Comparison Matrix
Place the comparison block on the landing page or on a dedicated `/compare` route.
*   **Template Table & Styling**:
    ```html
    <div class="comparison-container" style="min-height: 280px; overflow-x: auto; margin: 30px 0;">
      <table style="width: 100%; border-collapse: collapse; text-align: left;">
        <thead>
          <tr style="border-bottom: 2px solid #e2e8f0; background-color: #f7fafc;">
            <th style="padding: 12px; font-weight: bold;">Feature</th>
            <th style="padding: 12px; font-weight: bold; color: #3182ce;">Icypluto</th>
            <th style="padding: 12px; font-weight: bold; color: #a0aec0;">Competitor X</th>
          </tr>
        </thead>
        <tbody>
          <tr style="border-bottom: 1px solid #edf2f7;">
            <td style="padding: 12px; font-weight: 500;">AI Search Citations</td>
            <td style="padding: 12px; color: #2f855a;">Real-time Scraping & Grounding</td>
            <td style="padding: 12px;">Standard Keyword SEO Only</td>
          </tr>
          <tr style="border-bottom: 1px solid #edf2f7;">
            <td style="padding: 12px; font-weight: 500;">Integration Type</td>
            <td style="padding: 12px;">Zero-Config MCP Server API</td>
            <td style="padding: 12px;">Manual Dashboard Reporting</td>
          </tr>
        </tbody>
      </table>
    </div>
    ```

### Step 3: Write Clear Differentiator Paragraphs
Accompany the table with a summary paragraph comparing the two brands.
*   *Avoid*: *"Icypluto is far superior to Competitor X."*
*   *GEO Optimize*: *"Unlike Competitor X, Icypluto integrates directly with AI agents using a zero-config Model Context Protocol (MCP) server, allowing developers to query visibility metrics programmatically."*
