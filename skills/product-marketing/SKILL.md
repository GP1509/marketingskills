---
name: product-marketing
description: "When the user wants to create or update their product marketing context. Also use when the user mentions 'product context,' 'marketing context,' 'set up context,' 'positioning,' 'who is my target audience,' 'describe my product,' 'ICP,' 'ideal customer profile,' or wants to avoid repeating foundational information across marketing tasks. Use this at the start of any new marketing project before using other marketing skills. In ChatGPT Web, create or update a portable `product-marketing-context.md` file (or equivalent Project context) that other marketing skills can reference for product, audience, positioning, voice, proof, and goals."
metadata:
  version: 2.1.0
  upstream: "coreyhaines31/marketingskills"
  adaptation: "chatgpt-web-1.0.1"
---

# Product Marketing Context

You help users create and maintain a product marketing context document. This captures foundational positioning and messaging information that other marketing skills reference, so users don't repeat themselves.

## ChatGPT Web compatibility

This adaptation preserves the original product-marketing methodology while replacing assumptions about a local agent filesystem.

In ChatGPT Web:

- Treat `product-marketing-context.md` as the canonical portable context file for the current brand, client, product, or business. This filename is intentionally compatible with the legacy filename already recognized by the other upstream marketing skills.
- Before asking questions, inspect information already available in the current conversation, Project context, attached files, and connected sources that are actually accessible.
- Never claim to have read, created, updated, or saved a file unless that action really occurred on the current surface.
- If `product-marketing-context.md` is available in the current Project or conversation, read it before gathering more context.
- Also recognize `.agents/product-marketing.md`, `.claude/product-marketing.md`, and `product-marketing.md` when the user provides them.
- When a file-creation capability is available, create or update `product-marketing-context.md` as a reusable file. If persistent file creation is not available, return the complete Markdown document and clearly tell the user it has not been persisted yet.
- Downstream marketing skills should reuse this context when it is available instead of repeating foundational questions.
- Respond in the user's language unless they request another language.

## Workflow

### Step 1: Check for Existing Context

First, check the current conversation, Project context, attached files, and accessible connected sources for `product-marketing-context.md`. Also recognize `.agents/product-marketing.md`, `.claude/product-marketing.md`, and `product-marketing.md` when available.

**If existing context is available:**
- Read it and summarize what's captured — note its current **Document version** and the last few **Changelog** entries so the user sees where the doc stands and what's changed recently.
- Ask which sections they want to update.
- Only gather information for those sections.
- On any substantive save, bump the version and add a changelog entry (see Step 4). This document is shared context for other marketing skills, so a dated paper trail of *what changed and why* is worth keeping.

**If it doesn't exist, offer two options:**

1. **Auto-draft from available materials (recommended):** Study accessible source materials such as the website, repository, README, landing pages, marketing copy, product documentation, uploaded files, or other relevant sources. Draft a V1 from evidence, then let the user review, correct, and fill gaps. Do not invent missing facts.

2. **Start from scratch:** Walk through each section conversationally, gathering information one section at a time.

Most users prefer option 1 when sufficient source material is available. After presenting the draft, ask: "What needs correcting? What's missing?"

### Step 2: Gather Information

**If auto-drafting:**
1. Read the materials that are actually accessible: website pages, repository/README, landing pages, marketing copy, about pages, meta descriptions, product docs, uploaded files, and existing notes.
2. Separate confirmed information from inference. Do not turn assumptions into facts.
3. Draft all sections supported by the evidence.
4. Mark genuinely unknown fields as unknown or needing confirmation rather than filling them with plausible-sounding content.
5. Present the draft and ask what needs correcting or is missing.
6. Iterate until the user is satisfied.

**If starting from scratch:**
Walk through each section below conversationally, one at a time. Don't dump all questions at once.

For each section:
1. Briefly explain what you're capturing.
2. Ask relevant questions.
3. Confirm accuracy.
4. Move to the next.

Push for verbatim customer language — exact phrases are more valuable than polished descriptions because they reflect how customers actually think and speak, which makes copy more resonant.

---

## Sections to Capture

### 1. Product Overview
- One-line description
- What it does (2-3 sentences)
- Product category (what "shelf" you sit on—how customers search for you)
- Product type (SaaS, marketplace, e-commerce, service, etc.)
- Business model and pricing

### 2. Target Audience
- Target company type (industry, size, stage)
- Target decision-makers (roles, departments)
- Primary use case (the main problem you solve)
- Jobs to be done (2-3 things customers "hire" you for)
- Specific use cases or scenarios

### 3. Personas (B2B only)
If multiple stakeholders are involved in buying, capture for each:
- User, Champion, Decision Maker, Financial Buyer, Technical Influencer
- What each cares about, their challenge, and the value you promise them

### 4. Problems & Pain Points
- Core challenge customers face before finding you
- Why current solutions fall short
- What it costs them (time, money, opportunities)
- Emotional tension (stress, fear, doubt)

### 5. Competitive Landscape
- **Direct competitors**: Same solution, same problem (e.g., Calendly vs SavvyCal)
- **Secondary competitors**: Different solution, same problem (e.g., Calendly vs Superhuman scheduling)
- **Indirect competitors**: Conflicting approach (e.g., Calendly vs personal assistant)
- How each falls short for customers

### 6. Differentiation
- Key differentiators (capabilities alternatives lack)
- How you solve it differently
- Why that's better (benefits)
- Why customers choose you over alternatives

### 7. Objections & Anti-Personas
- Top 3 objections heard in sales and how to address them
- Who is NOT a good fit (anti-persona)

### 8. Switching Dynamics
The JTBD Four Forces:
- **Push**: What frustrations drive them away from current solution
- **Pull**: What attracts them to you
- **Habit**: What keeps them stuck with current approach
- **Anxiety**: What worries them about switching

### 9. Customer Language
- How customers describe the problem (verbatim)
- How they describe your solution (verbatim)
- Words/phrases to use
- Words/phrases to avoid
- Glossary of product-specific terms

### 10. Brand Voice
- Tone (professional, casual, playful, etc.)
- Communication style (direct, conversational, technical)
- Brand personality (3-5 adjectives)

### 11. Proof Points
- Key metrics or results to cite
- Notable customers/logos
- Testimonial snippets
- Main value themes and supporting evidence

### 12. Goals
- Primary business goal
- Key conversion action (what you want people to do)
- Current metrics (if known)

---

## Step 3: Create the Document

After gathering information, create or update `product-marketing-context.md` with this structure:

```markdown
# Product Marketing Context

**Document version:** v1
**Last updated:** [date]

## Product Overview
**One-liner:**
**What it does:**
**Product category:**
**Product type:**
**Business model:**

## Target Audience
**Target companies:**
**Decision-makers:**
**Primary use case:**
**Jobs to be done:**
-
**Use cases:**
-

## Personas
| Persona | Cares about | Challenge | Value we promise |
|---------|-------------|-----------|------------------|
| | | | |

## Problems & Pain Points
**Core problem:**
**Why alternatives fall short:**
-
**What it costs them:**
**Emotional tension:**

## Competitive Landscape
**Direct:** [Competitor] — falls short because...
**Secondary:** [Approach] — falls short because...
**Indirect:** [Alternative] — falls short because...

## Differentiation
**Key differentiators:**
-
**How we do it differently:**
**Why that's better:**
**Why customers choose us:**

## Objections
| Objection | Response |
|-----------|----------|
| | |

**Anti-persona:**

## Switching Dynamics
**Push:**
**Pull:**
**Habit:**
**Anxiety:**

## Customer Language
**How they describe the problem:**
- "[verbatim]"
**How they describe us:**
- "[verbatim]"
**Words to use:**
**Words to avoid:**
**Glossary:**
| Term | Meaning |
|------|---------|
| | |

## Brand Voice
**Tone:**
**Style:**
**Personality:**

## Proof Points
**Metrics:**
**Customers:**
**Testimonials:**
> "[quote]" — [who]
**Value themes:**
| Theme | Proof |
|-------|-------|
| | |

## Goals
**Business goal:**
**Conversion action:**
**Current metrics:**

## Changelog
*Newest first. One line per revision: what changed and why.*
- v1 ([date]) — Initial context.
```

---

## Step 4: Confirm, Version, and Persist

- Show the completed document.
- Ask if anything needs adjustment.
- **Set the version and changelog** — this is the paper trail for a document every other marketing skill can reuse:
  - **New document:** set `Document version: v1` and a single Changelog entry — `- v1 ([today]) — Initial context.`
  - **Updating an existing document:** increment the version (v2 → v3 …), update `Last updated` to today, and **prepend a new Changelog entry** at the top of the list (newest first) summarizing *what changed and why* in one line. Never rewrite or reorder past entries.
  - A good entry names the sections touched and the reason, not "updated the doc." Examples:
    - `- v3 (2026-07-16) — Repositioned from "email tool" to "deliverability platform"; added RevOps to the ICP.`
    - `- v2 (2026-06-02) — Rewrote value prop and objections after 5 customer interviews; added competitor Acme.`
  - Use today's date in ISO form (YYYY-MM-DD) for the entry and `Last updated`.
  - **Pure typo-only fix:** don't bump the version or add a changelog entry — just save the correction. Every other change bumps the version and gets an entry. When the change is a real repositioning, say so plainly — downstream skills will now generate against the new context.
- If file creation/update is available, create or replace `product-marketing-context.md` and provide the resulting file to the user.
- If the current surface cannot persist that file, provide the complete Markdown in the response and state clearly that it still needs to be added to the relevant Project/files for reuse across future chats in that project.
- Tell the user that other adapted marketing skills should use this context whenever it is available, and that the Changelog tracks positioning changes over time.

---

## Tips

- **Be specific**: Ask "What's the #1 frustration that brings them to you?" not "What problem do they solve?"
- **Capture exact words**: Customer language beats polished descriptions.
- **Ask for examples**: "Can you give me an example?" unlocks better answers.
- **Validate as you go**: Summarize each section and confirm before moving on.
- **Skip what doesn't apply**: Not every product needs all sections (e.g., Personas for B2C).
