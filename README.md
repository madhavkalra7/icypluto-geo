# Icypluto GEO Skills

This repository contains custom agentic skills designed for **Generative Engine Optimization (GEO)**. These skills guide AI agents in auditing and modifying company website content to maximize its visibility, citation frequency, entity matching, and overall recommendation authority within AI-driven search engines and conversational RAG (Retrieval-Augmented Generation) systems (e.g., Perplexity, SearchGPT, Gemini, Claude, Copilot).

---

## 📁 Repository Structure

The repository is structured as follows:

- **[`skills/`](./skills/)** - Root folder for all agentic skills.
  - **[`icypluto-geo/`](./skills/icypluto-geo/)** - The primary GEO optimization skill package.
    - **[`SKILL.md`](./skills/icypluto-geo/SKILL.md)** - The entry point defining the core description and the step-by-step GEO workflow for AI agents.
    - **[`citation_density.md`](./skills/icypluto-geo/citation_density.md)** - Guide for enhancing factual density, quantitative metrics, and citation anchors.
    - **[`readability_summaries.md`](./skills/icypluto-geo/readability_summaries.md)** - Guide for adding top-level TL;DR summary blocks optimized for semantic chunking and layout shift (CLS) safety.
    - **[`intent_faq.md`](./skills/icypluto-geo/intent_faq.md)** - Guide for constructing and injecting structured Q&A sections matching conversational search queries.
    - **[`brand_citations.md`](./skills/icypluto-geo/brand_citations.md)** - Guide for building comparison matrices and competitive differentiator tables.

---

## 🛠️ How it Works

The agentic skills in this repository are designed to be loaded by AI coding assistants (like Gemini/Antigravity). They contain structured instructions instructing the agent on how to scan, optimize, and verify target web copies.

### Skill Format
Each skill subdirectory contains a `SKILL.md` file formatted with YAML frontmatter containing metadata:
```yaml
---
name: "icypluto-geo"
description: "Actively audits, rewrites, and structures website content to optimize for Generative Engine Optimization (GEO), maximizing citations, entity matches, and recommendations in AI Search Engines."
---
```
Following the frontmatter is the markdown-formatted agent workflow specifying target optimization criteria, specialized audit sub-tasks, copy modification rules, and visual/compilation verification procedures.

---

## 🎯 Key Optimization Pillars

1. **Factual Density**: Replacing marketing jargon with objective data, statistics, and verifiable claims.
2. **RAG-Friendly Chunking**: Writing clear summary blocks (TL;DR cards) to be easily retrieved by search crawler splitters.
3. **Intent Q&A Mapping**: Adding semantic FAQ sections to answer conversational natural language queries directly.
4. **Competitor Comparison**: Building features tables mapping differentiators objectively vs competitors.
5. **Quality & Style Guardrails**: Ensuring no technical/SEO jargon leaks into the user-facing text, maintaining layout stability (CLS constraints), and verifying code integrity via automated build runs (`npm run build`).
