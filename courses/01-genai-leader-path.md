# The exam-aligned courses, summarised

Two paths, both of which I used. Course titles are exact — search for them by name.

---

## The official Google path

### Generative AI Leader Certification — Google Skills, path 1951

**Free · 5 activities · [skills.google/paths/1951](https://www.skills.google/paths/1951)**

Google's own learning path for this exam, on the Google Skills platform (formerly Google Cloud Skills Boost — the old `cloudskillsboost.google/paths/1951` URL still works).

**Why it matters more than any paid course:** it is written by the people who write the exam, and it is **the only course material using the current product vocabulary** — Gemini Enterprise, Agent Search, Gemini Notebook, Agent Studio. Every paid course I found still says Vertex AI. See [the 2026 renaming](../docs/04-product-naming-2026.md).

**What it covers:** gen AI fundamentals, then Google's tooling — **Gemini Advanced**, **Gemini Notebook**, **Google AI Studio**, and how the pieces fit together for a business audience.

**How to use it:** work it first, before any video course, so the correct names are the ones you learn first and the old names are the ones you translate. Then use this repo's [study guide](../study-guide/01-full-study-guide.md) for depth and the [product table](../study-guide/03-product-table.md) for recall.

---

## The Pluralsight path

### Google Cloud Generative AI Leader — 4 courses, ~5h44m, by Joseph Lowery

The four course titles map **1:1 onto the four exam domains**, which is itself a useful confirmation of the exam structure. Each course ends with an "Exam Question Review" module where the instructor works through official-style questions out loud — **those modules are the most valuable part of the path**, because they teach the elimination method rather than the content.

⚠️ **This path uses the pre-2026 product names throughout** (Vertex AI, Vertex AI Search, Agent Builder). The concepts are correct; the vocabulary is not. Translate as you go.

---

### Course 1 — "(Generative AI Leader) Fundamentals of Gen AI"

**2h01m · Exam Domain 1 (~30%)**

| Module | Covers |
|---|---|
| 1. Foundations of generative AI | AI ⊃ ML ⊃ gen AI; narrow vs general AI; supervised, unsupervised and reinforcement learning; what makes gen AI different (creation, summarisation, discovery, automation) |
| 2. Working with data in generative AI | Structured, unstructured and semi-structured data; the four dimensions of data quality; the five types of inconsistency; bias entering through data; the four levels of data maturity; metadata |
| 3. The generative AI technology stack | The five layers — infrastructure, models, platforms, agents, applications — and what each provides; GPUs vs TPUs |
| 4. Google's generative AI models and use cases | Gemini, Gemma, Imagen, Veo — modalities, relative cost, what each is for; how Imagen's two-part LLM-plus-diffusion architecture works |
| 5. Exam question review | Worked examples with the elimination method |

**Summary.** The vocabulary course. Everything the exam assumes you already know: the hierarchy, the three learning approaches, foundation models, context windows, prompt engineering versus prompt tuning, the ML lifecycle and the Google service at each stage, and the five-layer stack. **The layer diagram is a guaranteed question type** — a scenario describes a symptom and asks which layer to fix.

**Skip it if** you already work with gen AI day to day. Run it at 1.5–2× as a confirmation pass. **Do not skip module 3.**

**Corresponding material here:** [study guide, Section 2](../study-guide/01-full-study-guide.md#section-2--domain-1-fundamentals-of-gen-ai-30).

---

### Course 2 — "(Generative AI Leader) Google Cloud's GenAI Offerings"

**1h25m · Exam Domain 2 (~35%) · ⚠️ the most important 85 minutes in the path**

| Module | Covers |
|---|---|
| 1. Google Cloud's gen AI advantage | Google's AI history (TensorFlow, DeepMind, the 2017 Transformer paper); the four pillars of differentiation — TPUs, DeepMind access, the private fibre network, the integrated platform |
| 2. Pre-built gen AI offerings for AI-powered work | The Gemini app, Gemini Advanced, **Gems**, Gemini for Workspace, Gemini Notebook; individual vs enterprise Gemini; Gemini Cloud Assist vs Gemini Code Assist |
| 3. Improving customer experience with gen AI | The Customer Engagement Suite: Conversational Agents, **Agent Assist**, **Conversational Insights**, CCaaS; AI-powered search vs keyword search |
| 4. Building with AI and agents on Google Cloud | The pre-built → configurable → custom spectrum; Model Garden; AutoML; Agent Studio vs Google AI Studio; RAG out of the box; the services agents call |
| 5. Exam preparation | Worked examples |

**Summary.** The single highest-value block of study time available, and the one the path under-serves: **35% of the exam in 85 minutes of video.** This is where the "which product solves this problem?" questions come from, and where the 2026 renaming bites hardest.

**Do not watch this at 1.5×.** Take notes. Then reinforce it with the [product table](../study-guide/03-product-table.md) and the [Domain 2 drill](../practice/02-domain-2-product-drill.md) — I scored 71% on this domain in the practice exam, my worst, and this is what fixed it.

**The distinctions it teaches that the exam tests hardest:** Agent Assist (live, during the call) versus Conversational Insights (afterwards) · Agent Studio (production) versus Google AI Studio (prototype) · Gemini Notebook (your uploaded documents) versus Gemini Enterprise (across internal systems) versus Agent Search (build a search app) versus Workspace with Gemini (inside the document).

**Corresponding material here:** [study guide, Section 3](../study-guide/01-full-study-guide.md#section-3--domain-2-google-clouds-gen-ai-offerings-35).

---

### Course 3 — "(Generative AI Leader) Techniques to Improve GenAI Model Output"

**1h09m · Exam Domain 3 (~20%)**

| Module | Covers |
|---|---|
| 1. Overcoming foundation model limitations | The four limitations — hallucination, bias, knowledge cutoff, edge cases; why hallucination happens; the improvement ladder matching technique to risk |
| 2. Prompt engineering for better results | The four components of a strategic prompt; zero-, one- and few-shot; role prompting; prompt chaining; chain-of-thought; ReAct |
| 3. Controlling and steering model output | Temperature, top-P, top-K, output token limit, seed; matching parameters to use case; safety filters and their four categories |
| 4. Exam question review | Worked examples |

**Summary.** The most self-contained course in the path, and the one with the highest ratio of testable rules to minutes. Two ideas carry most of the marks:

> **Changing facts → RAG. Changing behaviour or tone → fine-tuning.**
>
> **Grounding controls information, not tone.**

The RAG-versus-fine-tuning comparison table is worth memorising outright, including the reason people get it wrong: RAG's headline benefit in a confidential or regulated scenario is **traceability and citation**, not cost.

**Corresponding material here:** [study guide, Section 4](../study-guide/01-full-study-guide.md#section-4--domain-3-techniques-to-improve-model-output-20).

---

### Course 4 — "(Generative AI Leader) Business Strategies for a Successful Gen AI Solution"

**1h09m · Exam Domain 4 (~15%)**

| Module | Covers |
|---|---|
| 1. Building a business-aligned gen AI strategy | Why initiatives stall; the strategy-to-value pipeline; capability → outcome mapping; the ROI formula; pre-built vs custom; the impact × complexity decision matrix |
| 2. Securing gen AI systems in the enterprise | Prompt injection, data leakage, model misuse and their attack surfaces; the shared responsibility model; **SAIF** and its four pillars; defence in depth |
| 3. Responsible AI for trust and accountability | Where bias enters across the lifecycle; measuring bias; anonymisation vs pseudonymisation; explainability and its four audiences; human oversight and auditability |
| 4. Exam question review | Worked examples |

**Summary.** The smallest domain and the one where my score was worst (63%). Not because it is hard, but because the questions are **the least intuitive for technical people**: the right answer is frequently about people, process and governance rather than systems.

> **The course states it outright and the exam tests it:** *"technology is only one part of the equation. People and processes ultimately determine success."*

⚠️ **One known gap.** This course teaches a **pilot → validation → integration → scale → optimisation** lifecycle. The exam uses a different five-phase model — **Dream → Select → Scale → Refine → Expand**. That difference cost me three marks. See [common mistakes, Pattern 2](../practice/03-common-mistakes.md).

**Corresponding material here:** [study guide, Section 5](../study-guide/01-full-study-guide.md#section-5--domain-4-business-strategies-15).

---

### Also on Pluralsight: the Practice Exam

**50 questions · 90 minutes · separate from the path**

It is a **different content type**, not a module inside the path, so finishing the videos does not include it. It was the most useful single item I used, for one reason: **it scores you by domain.** That is what tells you where to spend your remaining time.

**Take it under real conditions** — no notes, no pausing, no lookups — and record the per-domain breakdown, not just the total. My run: 39/50 = 78%, Fundamentals 93%, Techniques 80%, Offerings 71%, Business 63%. Those four numbers set everything I studied afterwards.

⚠️ Mine was dated **December 2025** and used the old product names. Do not let it teach you vocabulary.

---

## What I would do differently

1. **Do the Google Skills path first**, not the paid one. The names matter.
2. **Take the practice exam earlier.** I watched ~6 hours of video before taking one. An hour of diagnostics up front would have redirected the hours that followed.
3. **Spend more of the total on Domain 2 and less on Domain 1.** The path's hours are distributed almost inversely to the exam's weights.
