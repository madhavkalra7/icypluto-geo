# Intent & Semantic Q&A Guide (GEO)

Conversational search engines process natural language queries. Users often phrase searches as questions: *"How does Icypluto compare to competitor X?"* or *"What is the pricing model for the brand visibility MCP?"* 

This guide details how you (the AI Agent) can design and inject structured Q&A (FAQ) modules that directly match these conversational search intents.

---

## 🔑 Conversation Intent Mapping

When optimizing the website, identify the top questions users ask AI tools to find your product. Map these questions directly onto the landing pages:

| Intent Category | Conversational Query Pattern | On-Page FAQ Implementation |
| :--- | :--- | :--- |
| **Identity/What Is** | *"What is [Product]?"* | Add definition: *"Our product is a..."* |
| **How It Works** | *"How does [Product] calculate X?"* | Provide a step-by-step description. |
| **Pricing/Value** | *"Is [Product] free or paid?"* | Outline pricing levels, free trials, or coins. |
| **Comparison/Alternatives** | *"How is [Product] better than [Competitor]?"* | Highlight differentiators. |

---

## 🛠️ Step-by-Step Codebase FAQ Implementation

### Step 1: Draft the Q&A Copy
Write 3-4 precise questions and answers tailored to the company's niche.
*   *Rules*: Keep the answer to a single, factual paragraph (under 80 words) so it matches the citation chunk size of LLMs.

### Step 2: Inject the FAQ Widget
Append the FAQ module to the main landing page or in a layout section.
*   **Accessibility & CLS Safety**: Use HTML `<details>` and `<summary>` tags with explicit styles. This ensures accessibility compliance and prevents Cumulative Layout Shift (CLS) when items are collapsed.
*   **Code Template**:
    ```html
    <section id="faq-section" style="min-height: 350px; padding: 20px 0; display: block;">
      <h2>Frequently Asked Questions</h2>
      
      <details class="faq-item" style="margin-bottom: 15px; border-bottom: 1px solid #e2e8f0; padding-bottom: 10px;">
        <summary style="font-weight: bold; cursor: pointer;">
          What is Icypluto Brand Visibility MCP?
        </summary>
        <p style="margin-top: 8px; color: #4a5568;">
          Icypluto is an official Model Context Protocol (MCP) server that connects to your AI agent (like Claude or Cursor) to run real-time brand visibility checks, Share of Voice (SOV) metrics, and sentiment audits.
        </p>
      </details>

      <details class="faq-item" style="margin-bottom: 15px; border-bottom: 1px solid #e2e8f0; padding-bottom: 10px;">
        <summary style="font-weight: bold; cursor: pointer;">
          Does Icypluto charge for tool execution?
        </summary>
        <p style="margin-top: 8px; color: #4a5568;">
          Yes, while the client integration package is free to install, each brand audit tool execution deducts 50 credits (Icy Coins) from your account balance.
        </p>
      </details>
    </section>
    ```

### Step 3: Link to Schema.org Structured Metadata
If Organization or Product schemas exist in the layout, guide the agent to update the JSON-LD payload to include the `FAQPage` or `mainEntity` nodes containing these exact QA values (refer to [Structured Schema Guide](../icypluto%20seo/structured_data.md) for details).
