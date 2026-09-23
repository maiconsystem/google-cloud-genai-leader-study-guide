# Google Cloud Generative AI Leader — Exam-Only Study Sheet

**What this is:** the exam-relevant subset, extracted from the 9 Pluralsight "GenAI: Engineering and Architecture" transcripts. Everything engineering-only has been cut.
**What got cut and why:** HNSW/IVF/PQ index internals, GPU memory hierarchy and model parallelism, VRAM math, serving frameworks (vLLM/TensorRT-LLM/TGI), circuit breakers and bulkheads, Kubernetes quotas, Airflow DAGs, PromQL and burn-rate alerting, Redis/idempotency patterns, LoRA mechanics, code demos. **None of that is on this exam** — it is engineering-interview material, not leader-exam material. See [the engineering path notes](../courses/02-engineering-architecture-path.md) if you want that depth after you pass.

> ⚠️ **Read this before anything else.** The exam has four domains. This path covers **two of them well, one partially, and one not at all.**
>
> | Domain (approximate weight — verify against the current official exam guide) | Does this path cover it? |
> |---|---|
> | 1. Fundamentals of generative AI (~30%) | ✅ **Yes, well** |
> | 2. Google Cloud's generative AI offerings (~35%) | ❌ **No. Zero.** The single biggest domain and this path gives you nothing |
> | 3. Techniques to improve model output (~20%) | ✅ **Yes, very well** — this is the path's strongest area |
> | 4. Business strategies for a successful gen AI solution (~15%) | 🟡 **Partially** — governance and risk yes, ROI/adoption/change management no |
>
> **This sheet alone will not pass the exam.** Domain 2 is ~35% of the questions and must come from Google Cloud Skills Boost. Section 6 below is your checklist for it.

---

## 1. Fundamentals of generative AI

### What the model actually is and does

- A **foundation model** is trained on broad data and adapted to many tasks. An **LLM** is a foundation model for language. **Multimodal** models handle text, images, audio, and documents together, converting each into a shared internal representation so the model can reason across them.
- **Training** happens once, up front. **Inference** is what happens every time a user sends a request — it is what users experience and what you pay for. In production, inference is judged on **latency, throughput, and cost**, not on training accuracy. *A highly accurate model that is slow or expensive is not useful.*
- Text is processed as **tokens**. You are billed for input tokens *and* output tokens. Every additional generated token costs time and money — generation length is **linear** in cost and latency.
- The **context window** is the fixed amount of text the model can consider at once. Prompt + system instructions + retrieved context + conversation history all compete for it.

### The four core limitations (know these — they are the "why" behind most exam answers)

1. **No access to real-time or private data.** The model only knows its training data.
2. **A training cutoff date.** Anything after it does not exist to the model.
3. **No built-in memory.** Each turn starts fresh unless you supply history.
4. **A fixed context window.**

**Consequences:** hallucination (confident, fluent, wrong), incomplete understanding of intent, loss of context, poor personalisation.

> **Hallucination is the single most important concept on this exam.** A model can produce a factually invented answer that is grammatically perfect and sounds authoritative. **Fluency does not guarantee correctness.** The exam's preferred fixes, in order: **grounding/RAG**, then human oversight, then guardrails and validation.

### Embeddings and semantic search

- An **embedding** is a numeric representation of meaning — text converted into a vector. Similar concepts land near each other in that space.
- **Semantic search** finds meaning, not keywords: it can retrieve a passage about canine veterinary care from "how do I look after my sick dog," even with no matching words.
- **Cosine similarity** is the standard measure — it compares *direction*, not magnitude, which is why it works across documents of different lengths.
- A **vector database** stores embeddings and finds the nearest ones fast. Traditional databases can't do this — they're built for exact matches and range queries.
- Compare the three data stores:

| Store | Best for |
|---|---|
| Relational / NoSQL | Structured transactional records, exact queries |
| **Vector database** | Semantic search over unstructured text — meaning-based retrieval |
| **Knowledge graph** | When the **relationships between entities matter as much as the entities** — fraud detection, recommendations, multi-hop questions |

### Sampling parameters (expect a question on temperature)

| Parameter | Low value | High value |
|---|---|---|
| **Temperature** | Deterministic, consistent, factual — use for summarisation, Q&A, extraction, decision support | Creative, diverse — use for ideation. More risk of incoherent or incorrect output |
| **Top-K** | Fewer candidate tokens → focused, stable | More variation |
| **Top-P (nucleus)** | Dynamic: fewer candidates when the model is confident | Broader exploration |

**Rule for the exam:** *factual/structured task → lower temperature. Creative task → higher temperature.*

### Model size trade-off

Bigger models: better reasoning and quality, **higher latency and cost**. Smaller models: faster and cheaper, less reasoning depth.
**The pattern the exam rewards:** *use the smallest model that meets your quality bar, and escalate to a larger model only when necessary.* A common production design routes simple requests to a small model and complex ones to a frontier model.

---

## 2. Techniques to improve model output

*This is the path's strongest domain. Know it cold.*

### The four adaptation approaches — and when to use each

| Approach | What it does | Choose it when | Cost / effort |
|---|---|---|---|
| **Prompt engineering** | Change the instructions | Always try first — cheapest, fastest, no infrastructure | Lowest |
| **RAG (grounding)** | Retrieve real data at query time and inject it into the prompt | You need **current, private, or factual** data; answers must be traceable to a source | Moderate |
| **Fine-tuning** | Change the model's weights on your data | You need **consistent tone, style, format, or domain terminology** that prompting can't achieve; you have enough high-quality labelled data | High — expensive, needs a data pipeline, slow to update |
| **Agents / function calling** | Let the model choose and call tools | The task **branches**, or requires real-world actions and live system data | Highest complexity |

> **The exam's favourite distinction: RAG vs fine-tuning.**
> **Data freshness or factual grounding → RAG.** **Tone, style, or format consistency → fine-tuning.** RAG updates by changing your knowledge base; fine-tuning requires retraining. Most real systems use both.

### RAG / grounding

**Why it exists:** it directly fixes limitations 1, 2 and 4 above. The model gets real data at query time, so it doesn't have to invent.

**The pipeline, in order:**
1. **Data preparation** — collect documents → **chunk** them into smaller pieces → convert chunks to **embeddings** → store in a **vector database**.
2. **Query processing** — take the user's question (optionally rewrite/expand it).
3. **Retrieval** — embed the query, search the vector store, return the most relevant chunks.
4. **Augmentation** — inject the retrieved chunks into the prompt as context.
5. **Generation** — the model answers using that context.

**Chunking** is a real trade-off: chunks too large and the specific fact is buried and blurred; too small and you lose the surrounding context. Attach **metadata** (source, section, date) to every chunk so you can filter and cite.

**Retrieval quality is the bottleneck.** Retrieve the wrong documents and the model produces a confident, wrong answer. Improvements the exam may touch:
- **Hybrid search** — combine **semantic/vector** search with **keyword** search, then merge. Keyword search catches exact terms, names, product codes; semantic search catches meaning. Better together than either alone.
- **Re-ranking** — a second, stronger model reorders the retrieved results to put the best first.
- **Top-K** — how many chunks you retrieve. More isn't better: it adds latency, cost, and noise.

**Grounding's business payoff:** fewer hallucinations, answers traceable to trusted sources, and **citations** you can show the user — which is what actually builds trust in regulated, legal, and healthcare settings.

### Prompting techniques

- **Zero-shot** — instruction only.
- **Few-shot** — include a handful of examples. Dramatically improves consistency, especially for output format and classification labels.
- **Chain of thought** — ask the model to show its intermediate reasoning before answering. Use when each step depends on the last and there's a right answer (maths, logic, rule-driven workflows). Costs more tokens and time — overkill for simple lookups.
- **ReAct** — reason → act (call a tool) → observe the result → update reasoning. Use when the model needs new information before it can continue.
- **System prompt vs user prompt** — the system prompt sets role, tone, and constraints and must be treated as **immutable and higher priority** than user input.

**Prompt injection** is the key security concept: a user crafts input designed to override your instructions ("ignore your previous instructions..."). Defences: **strict separation of system/developer/user roles**, input sanitisation, and adversarial testing before deployment.

### Structured output

For anything feeding another system, don't parse free text — constrain the model to a **schema** (defined fields, data types, required flags, and **enumerations** for known option sets, which is what stops invented status values). Validate the output; on failure, retry feeding the validation error back to the model.

### Agents and function calling

The model **decides what to ask for; your code decides how and whether it's allowed.** The model emits a structured request against a defined tool schema; your application validates it, checks permissions, executes, and returns the result for the model to reason over.

**Why this matters for the exam:** it keeps deterministic logic and data access **outside** the model. A number comes from a system of record, not from the model guessing. Never let the model generate and execute raw SQL against a production database.

> **Agent design principle worth memorising:** *autonomy is a cost you pay when the task branches.* If the task doesn't branch, a single-shot call is the correct design — autonomy adds cost, latency, and unpredictability for nothing.

**Multi-agent patterns:** a **hierarchical** coordinator that decomposes a goal and delegates to specialist agents; **peer-based** collaboration; **specialised expert** agents by domain. More agents is not better — each one adds coordination and communication cost.

### Evaluation

- **Automated metrics:** BLEU (n-gram overlap, misses correct-but-differently-worded answers), ROUGE (coverage, common for summarisation), BERTScore (semantic similarity via embeddings).
- **LLM-as-judge** — a model scores outputs against explicit criteria. Scalable and repeatable, but needs a well-defined rubric.
- **Human evaluation** — captures usefulness, clarity, and intent that automated metrics miss. Expert reviewers for high-stakes correctness and safety.
- **A single metric is never enough.** A response can be factually correct but irrelevant, coherent but unsafe, or fluent while ignoring the instructions. Evaluate **multiple dimensions**: accuracy, relevance, coherence, **instruction adherence**, and safety.
- **Ground truth / golden dataset** — a curated set of representative inputs with known-good answers, used to compare model versions objectively and to catch regressions.
- **Human-in-the-loop** — route low-confidence or high-risk outputs to a person before they take effect. This is the exam's default answer for consequential decisions.

### Monitoring and drift

The model that passed validation six months ago may not behave the same today, **even if the model itself never changed.**

- **Input drift** — users start asking different things.
- **Output quality drift** — accuracy, relevance, or safety degrade over time.
- **Data/retrieval drift** — your knowledge base, embeddings, or index changed, so the same question retrieves different context.

**Response:** monitor continuously against a baseline, evaluate on a schedule (not just at release), and retrain, re-index, or roll back when metrics cross a threshold.

---

## 3. Responsible AI, safety, and governance

*Spans domains 1 and 4. High-yield — the exam leans heavily here.*

### Guardrails run at two checkpoints

**Input guardrails** screen the user's request *before* the model sees it (blocking prompt injection, disallowed requests). **Output guardrails** check the response *before* the user sees it (hallucination checks, toxicity, policy violations, **PII redaction**). Either can block, modify, or allow.

### Bias

Bias enters through **training data**, and evaluation must be deliberate:
- **Demographic parity** — are outcomes distributed equally across groups?
- **Representation** — do all relevant groups appear in the training data?
- **Stereotyping** — does the model reinforce harmful patterns?
- **Performance disparity** — does accuracy vary by group? (Requires *disaggregated* metrics — an overall average hides this.)

For high-risk systems, bias evaluation is not optional; in some jurisdictions it is legally required.

### Data governance

Classify data and let the classification drive the controls:

| Class | Requirement |
|---|---|
| Public | Few restrictions |
| Internal | Review before training use; hosting matters |
| Customer | Explicit consent; approved infrastructure only |
| **Regulated (PII / PHI / PCI)** | Anonymisation, masking, complete audit trail |

> **The question compliance will always ask: "for any given request, what data touched the model?" If you can't answer that, you have a problem.**

Also know: **data residency** (does data leave the region?), **DPAs** — read whether your prompts are used to train the provider's models, and the fact that with a third-party API **your data leaves your network**.

### Use-case risk tiers

A three-tier model most enterprises land on:
- **Green — pre-approved:** internal document search, summarisation, code completion. Low risk, well-understood.
- **Yellow — requires review:** customer-facing chat, external document generation.
- **Red — prohibited:** automated hiring decisions, medical diagnosis without human oversight, anything with uncleared regulatory exposure.

**The strategic goal is to expand the green zone over time as confidence grows.**

### Transparency and explainability

- **Retrieval attribution** — cite the specific source document and section. This is the highest-value transparency feature for end users.
- **Confidence signals** — express uncertainty in **natural language** for end users ("well supported by your documents" / "verify independently"), not raw percentages, because a number like "78% confidence" sounds precise and gets over-trusted.
- **Audit trail** — for GenAI, one user question is a *chain* of decisions, not one event. A complete record captures: request context (who, when, which tenant) → the exact input prompt → **the retrieval trace (which documents, what scores)** → model version and raw output → what the guardrails did and the final response. **If you only log the final output, you can't tell whether the model misbehaved, retrieval surfaced the wrong document, or a guardrail overcorrected.**
- Audit logs must be **immutable** (append-only, write-once), complete, searchable, and retained per regulation.

### The regulatory landscape

**EU AI Act — four risk tiers.** Know these:

| Tier | Examples | Obligation |
|---|---|---|
| **Unacceptable** | Government social scoring; AI manipulating vulnerable people | **Banned** |
| **High risk** | Hiring, credit scoring, medical devices, critical infrastructure | Risk documentation, **human oversight**, logging, conformity assessment **before market** |
| **Limited risk** | Chatbots, deepfakes, emotion recognition | **Transparency** — users must be told they're interacting with AI |
| **Minimal risk** | Spam filters, AI in games | Largely unregulated |

**Extraterritorial reach:** if your system is used by people in the EU, it applies — regardless of where your company is. You don't opt out by geography.

**Sector rules that apply regardless of what you call the system:** **HIPAA** (anything touching PHI), **SR 11-7** (US model risk management — regulators have confirmed it applies to GenAI: documented validation, independent review, ongoing monitoring), plus SOC 2, ISO 27001, PCI-DSS, GDPR.

**Design consequence:** don't hard-code compliance. Use **configuration per jurisdiction** — feature flags, configurable thresholds, and modular controls — so a new rule is a config change, not a rebuild.

---

## 4. Business strategy

*Partial coverage in this path. Section 6 lists what's missing.*

### The trade-off triangle — latency, accuracy, cost

Every architectural choice pulls toward one vertex and away from the others. The method:
1. Define **minimum acceptable thresholds** for all three.
2. Identify the **primary** dimension for that specific workload.
3. Optimise it while keeping the others above threshold.
4. Measure and iterate.

**Different workloads in the same product get different answers.** Real-time customer chat optimises **latency** (customers won't wait). An internal expert copilot optimises **accuracy** (bad suggestions destroy trust). Batch analytics optimises **cost per item** (latency is irrelevant — nobody cares if the report takes 10 minutes or 20).

> **Your use case must dictate your architecture, not the other way around.** Using RAG for every problem is the "golden hammer" anti-pattern.

### Cost

- Cost is driven by **tokens in + tokens out**, request volume, and premium model/feature choices.
- **GenAI costs do not scale linearly.** A traffic spike causes a *spend* spike, not just a latency spike.
- **Hidden costs to name if asked:** failed requests and **retries** (a system can silently double or triple spend for the same visible output), retrieval and preprocessing compute, storage of embeddings and logs, **observability data volume**, network egress, and idle/over-provisioned capacity.
- **Levers:** shorter prompts, **caching** (serve repeated or semantically similar questions without calling the model), batching, capping max output tokens, and routing to smaller models by default.
- **Measure cost per request, per token, and — most importantly — per *successful outcome*.** Total spend hides the expensive failures.

### Build vs buy / hosting

| Option | Gain | Give up |
|---|---|---|
| **Third-party API** | Fastest to start, no infrastructure, pay per use | Your data leaves your network; you depend on a vendor's availability, rate limits, and pricing |
| **Self-hosted open model** | Full data control, better unit economics at high volume | Significant operational burden and specialist staff |
| **Hybrid** | Different choice per workload — usually the right answer | Complexity |

Compliance frequently decides this, not cost. A model that performs brilliantly but sends sensitive data to an unknown location **isn't approved — it's liability.**

### Governance and approval

A governance committee needs **four perspectives**: Legal/Compliance (regulatory risk), Security (threat model, data handling), Data Science/ML (feasibility and model fitness), and Business (value and priority) — chaired with final authority. **No single function can approve a GenAI application alone.**

**Workflow:** proposal → **risk assessment** (low/medium/high — the score determines how much scrutiny follows) → technical review → committee decision → production sign-off with monitoring requirements. Low-risk proposals get fast-tracked; the process must scale.

**Why GenAI governance is different from traditional software governance:** outputs are **nondeterministic**, failures are **stochastic** (1 in 1,000 requests), and the attack surface includes training data, prompts, and every generated output.
> **Traditional governance asks "did you follow the process?" GenAI governance asks "is the system behaving as intended *right now*?" It cannot be a gate you pass once — it must be continuous.**

**Model lifecycle governance:** development → validation → deployment → **monitoring** → **retirement**. Every phase has requirements; skipping one leaves a gap in the compliance story. Higher risk tiers get more scrutiny: low risk → automated evaluation; medium → human review; high → full committee approval, continuous audit, documented incident response.

### Deployment strategy

Ship changes gradually, never all at once:
- **Canary** — route a small share of real traffic (5–10%) to the new version, compare quality/latency/cost/safety against the baseline, then roll forward or back.
- **Shadow testing** — mirror production traffic to the new version but don't show its output to users. Zero user impact.
- **A/B testing** — split traffic and compare user-facing outcomes.
- **Gradual rollout** with defined thresholds and **automatic rollback**.

**Rollback triggers:** quality regression, operational instability, and — immediately, without debate — **any increase in policy violations, harmful outputs, or safety failures.**

### The organisational model

| Model | Trade-off |
|---|---|
| **Centralized** | Strong governance, but the platform team becomes a bottleneck — and teams that can't move fast enough build their own, so you lose visibility |
| **Federated** | Fast and flexible, but fragmented: no shared audit trail, no consistent policy |
| **Hybrid** ✅ | Where mature enterprises land: central team owns gateway/guardrails/observability/audit; app teams self-serve. **Governance centralized, flexibility distributed** |

> **The line worth remembering: governance only works if teams actually use the platform. Teams that route around it are invisible to it.** That's why developer experience *is* a governance mechanism, not a nice-to-have.

---

## 5. Rapid-fire recall

| Prompt | Answer |
|---|---|
| Model invents a fact | **Hallucination** → fix with grounding/RAG, then human oversight |
| Need current or private data | **RAG**, not fine-tuning |
| Need consistent tone or format | **Fine-tuning**, not RAG |
| Cheapest thing to try first | **Prompt engineering** |
| Numeric representation of meaning | **Embedding** |
| Finds meaning, not keywords | **Semantic search**, using a **vector database** |
| Standard similarity measure for text | **Cosine similarity** |
| Fixed amount the model can read at once | **Context window** |
| Makes output more deterministic | **Lower temperature** |
| Model chooses and calls a tool | **Function calling / agent** |
| Task branches and needs multiple steps | Agentic; otherwise single-shot |
| Show intermediate reasoning | **Chain of thought** |
| Reason → act → observe → repeat | **ReAct** |
| A few examples in the prompt | **Few-shot** |
| Attack that overrides your instructions | **Prompt injection** |
| Screens input and output | **Guardrails** (two checkpoints) |
| Person reviews before it takes effect | **Human-in-the-loop** |
| Behaviour degrades over time | **Drift** → continuous monitoring |
| Small share of real traffic to a new version | **Canary** |
| Mirror traffic, hide the output | **Shadow testing** |
| Curated known-good test set | **Golden dataset / ground truth** |
| Model scores another model's output | **LLM-as-judge** |
| EU tier requiring human oversight + conformity assessment | **High risk** |
| EU tier requiring "tell users it's AI" | **Limited risk** |
| Three competing goals | **Latency, accuracy, cost** |

---

## 6. The gap — what this path does NOT give you

**Domain 2 (Google Cloud's gen AI offerings) is ~35% of the exam and this path covers none of it.** Study these from **Google Cloud Skills Boost — Generative AI Leader learning path** (free, authoritative):

**Products to be able to define, and say when you'd choose each:**
- **Vertex AI** — the umbrella platform. Vertex AI Studio, Model Garden, Model Registry, Pipelines, Agent Engine, evaluation tooling.
- **Gemini** — the model family, its tiers, and when to pick which.
- **Vertex AI Search** (and Vertex AI Agent Builder) — managed grounding/RAG and agent construction.
- **Model Garden** — browsing and deploying first-party, third-party, and open models.
- **NotebookLM** — grounded research and summarisation over your own documents.
- **Gemini for Google Workspace** and **Google Agentspace** — gen AI in everyday productivity tools.
- **BigQuery ML** and **Document AI** — AI over structured data, and document processing.
- **Grounding with Google Search** and grounding with your own data.

**Also from Google, not from this path:**
- Google's **Responsible AI principles** and the **SAIF** (Secure AI Framework).
- **AI adoption maturity / readiness** framing, and Google's own change-management and business-value language.
- GCP security fundamentals as they touch AI: **IAM**, **VPC Service Controls**, **CMEK**, data residency on Google Cloud.

**Highest-leverage study move:** as you meet each Google product on Skills Boost, write one line saying **which concept in this sheet it implements** (e.g. "Vertex AI Search = managed RAG pipeline — section 2"). That fuses the two bodies of knowledge instead of memorising them separately, and it's how you answer scenario questions rather than definition questions.

---

*Extracted 2026-09-08 from the nine Pluralsight "Generative AI: Engineering and Architecture" courses. Domain weights are approximate — confirm against the current official exam guide before you book.*

> **A technique worth stealing:** the most useful practice questions I wrote were the ones grounded in **my own past projects** — taking a system I had actually delivered and asking "which Google product would I use for this now, and why?". Do that for three or four projects of your own. It converts product recall into something you can reason about under pressure, and it is also how you will be asked about this material in an interview.
