# The 11 Questions I Got Wrong — and what each one teaches

**Practice exam, 2026-09-15: 39/50 = 78%.** Fundamentals 93% · Techniques 80% · Offerings 71% · Business 63%.

I kept this file because the errors were **not randomly distributed**. Eleven misses, four clear patterns, three genuine content gaps. The patterns are the useful part: they are habits of reading, not gaps in knowledge, and they are the habits that cost most candidates marks.

**Note what this implies about revision.** Fundamentals scored 14/15 — re-studying it would have been wasted time. Score your own practice exam by domain and do the same.

---

## PATTERN 1 — Multi-select is the single biggest leak 🔴

**I lost marks on all three multi-select questions I faced.**

| Q | Correct answers | I selected | Error |
|---|---|---|---|
| **Q35** (Business, Scale) | Infrastructure for concurrent users **+ change management and training plan** | Infrastructure only | **Under-selected** |
| **Q6** (Offerings, MLOps) | Pipelines **+ Feature Store + Model Garden** | Pipelines only | **Under-selected (1 of 3)** |
| **Q24** (Techniques, PEFT) | Reduced compute **+ small portable adapter files** | Reduced compute **+ "more knowledgeable model"** | Under-selected the right one, **added a wrong one** |

**The diagnosis: I stopped as soon as I found an answer that was clearly correct.** On Q6 I found Pipelines, recognised it as right, and moved on — leaving two marks on the table in the largest domain on the exam.

### The fix — four rules, apply them mechanically

1. **Read the stem for the count.** "Which components", "What are the primary advantages", "What are the most critical considerations" — **plural nouns mean multiple answers.** Q6 said "component**s**". Q35 said "consideration**s**". Q24 said "advantage**s**". All three said so in the stem.
2. **Evaluate all four options independently.** Ask of each one: *"Is this statement true, and does it answer the question?"* — not *"is this the best answer?"* Multi-select isn't a competition between options; each stands alone.
3. **If the interface doesn't tell you how many to pick, assume two.** Two is the most common. Never submit a multi-select with one box ticked unless you've actively rejected the other three with a reason.
4. **Guard the other direction too.** On Q24 I added a wrong one. A statement can be *plausible and still false* — "PEFT results in a more knowledgeable model" sounds reasonable but is backwards (full fine-tuning updates all parameters and incorporates knowledge more deeply; PEFT is an efficient *approximation*).

> **Expected value of fixing this alone: roughly 4–6 marks.** It is the highest-return thing on this page, and it costs no studying at all — just discipline.

---

## PATTERN 2 — The wrong lifecycle framework 🔴

**All three Business misses (Q5, Q18, Q35) are the same framework.** I had studied the *Pluralsight* lifecycle — pilot → validation → integration → scale → optimisation — but **the exam uses a different five-phase model with different names.** If you learn one thing from this repo, learn this one.

### Google's gen AI adoption lifecycle — the one the exam tests

| Phase | Primary goal | Signature activity |
|---|---|---|
| **Dream** | Ideate. What could gen AI do for us? | Exploring possibilities across the business |
| **Select** | Choose which use case to pursue | Prioritising by value and feasibility |
| **Scale** | Take a *validated* pilot to broad rollout | **Two things, always:** infrastructure for many concurrent users **and** change management + training to drive adoption |
| **Refine** | **Make the live solution better through measurement and iteration** | Feedback loops (thumbs up/down), using that data to fine-tune. **The solution stays in production** |
| **Expand** | **Leverage this success to find NEW use cases elsewhere in the business** | Restarts the cycle — new Dream and Select activities for other departments |

### Why each one was missed

- **Q5 (Refine).** I chose *roll back and limit access to testers*. That moves **backwards** out of production. Refine assumes the solution is **valuable enough to keep live** while you improve it. 15% inaccuracy is a *refinement input*, not a reason to retreat. **Rule: in Refine, the answer is always "instrument it and iterate", never "withdraw it".**
- **Q18 (Expand).** I chose *continue improving the existing marketing tool*. That is the definition of **Refine**. Expand's whole point is that you've proven the pattern and now **replicate it into other parts of the business**. **Rule: Refine = deeper on the same tool. Expand = wider into new areas.**
- **Q35 (Scale).** I picked infrastructure and missed **change management and training**. See Pattern 3.

### The discriminator to memorise

> **Same solution, getting better = Refine. New solutions elsewhere = Expand.**

⚠️ *Source note: these phase definitions are reconstructed from the practice exam's own answer rationales. I could not find this framework in Google's public documentation, so **verify it against the official study guide PDF and Skills Boost path 1951** before relying on the phase names. The underlying logic is sound regardless of what the phases are called.*

---

## PATTERN 3 — Defaulting to the technical answer and missing the people answer

On **Q35** the two correct answers were infrastructure **and** change management. I took the technical one and stopped.

This is worth naming because **the course material teaches the opposite explicitly**: *"technology is only one part of the equation. People and processes are what ultimately determine success."* Knowing it is not enough. Under exam pressure the systems answer is the natural reach for anyone with a delivery or engineering background — which is most people taking this exam.

**The correction:** this is a **leadership** exam. Google's own description says the certified person's expertise is *"in strategic leadership and influence, not technical implementation."* When a scenario involves rolling something out to people, **adoption, training, change management and governance are first-class answers, not soft extras.**

**Drill:** for any "what's needed to scale / launch / roll out" question, force yourself to check three buckets before answering — **people** (skills, trust, training, adoption) · **process** (workflows, governance, approval) · **technology** (infrastructure, integration). If the question allows multiple answers and you've only picked technology, you are probably wrong.

---

## PATTERN 4 — Picking the plausible answer over the *primary* one

Two misses where I chose something defensible but not what the question asked for.

**Q36 — RAG vs fine-tuning for confidential documents.** I chose *"RAG is less expensive and complex."* Often true! But the stem specified **private, confidential company documents**, and for that scenario the primary advantage is **precise source attribution and fact-checking** — the answer is generated from retrieved chunks, so the system can **cite sources and users can verify**. Fine-tuning blends knowledge into weights and you lose traceability.

> **Refinement to the RAG-vs-fine-tuning rule:** it's not only *changing facts → RAG*. It's also **"needs to be auditable / citable / verifiable → RAG."** In regulated, legal, medical or confidential contexts, **traceability is the headline benefit**, not cost.

**Q13 — complex multi-step financial calculations.** I chose *"a simple API call to a calculator service."* A calculator API is fixed-function; the requirement was **complex, multi-step, dynamic** logic. The answer was a **Code Interpreter tool**.

**The habit to build:** after selecting an answer, re-read the *stem* — not the options — and ask **"does my answer address every qualifier in the question?"** Q36 said *confidential*. Q13 said *complex, multi-step*. Both qualifiers were the whole question.

---

## CONTENT GAP A — Agent tool types

**Q13 exposed this.** An agent can be given different *kinds* of tools, and the exam distinguishes them:

| Tool type | What it does | Use when |
|---|---|---|
| **Function calling** | Model emits a structured request; **your code executes it** | Triggering a specific, predefined action against a known API |
| **Code Interpreter / code execution** | Model **generates and runs code** (e.g. Python) in a **secure sandboxed environment** | **Dynamic logic, complex or multi-step calculations, data manipulation** — anything a fixed API can't express |
| **Data store / retrieval tool (grounding)** | Retrieves from your documents or knowledge base | Answers must be grounded in enterprise content |
| **Extensions / connectors** | Pre-built integrations to external services | Connecting to email, productivity apps, third-party systems |

> **Signal words for Code Interpreter: "complex", "multi-step", "calculations", "dynamic", "data manipulation", "securely".** A fixed API call is the wrong answer whenever the logic has to be *generated*, not just *invoked*.

---

## CONTENT GAP B — Function calling: what the model does **not** do

**Q17.** I chose *"automatically execute the selected function and return the result."* That is the single most common misconception about function calling, and the exam tests it directly.

**What actually happens:**

1. The model interprets intent and **generates a structured JSON object** containing the **function name** and the **arguments**, extracted from the user's query.
2. **The model stops there. It does not execute anything.**
3. **Your application code** receives that structured request, **validates it, checks permissions, and runs the function.**
4. The result is passed back to the model, which reasons over it and decides what happens next.

> **The one-line version: the model *requests*, your code *executes*.** That separation is the entire security value of function calling — it's why sensitive logic and data access stay outside the model, and why you can enforce permissions and validation. The study guide says "the model decides *what* to ask for; your code decides *how* and whether it's allowed" — this is the precise mechanical form of that sentence.

---

## CONTENT GAP C — Gemini for Google Workspace: know its boundaries

**I missed two questions on this product (Q12 and Q25), in opposite directions** — over-extending it once and under-describing it once.

**What it IS:** an AI assistant **embedded inside Workspace apps** — Gmail, Docs, Sheets, Slides, Meet. Drafting, summarising, rewriting, analysing spreadsheet trends, structuring slides, recapping meetings.

**Its core productivity benefit (Q25):** it **shifts the user from content *creator* to content *editor and director*.** You start from a generated first draft rather than a blank page, then review, edit and direct.

**What it is NOT:**
- ❌ **Not an enterprise search engine.** Q12 — an intranet search over internal product specifications answering natural-language questions is **Vertex AI Search**. Workspace Gemini works *inside documents*, not as a standalone search product over enterprise data.
- ❌ **Not a compliance guarantee.** Q25's distractor claimed it ensures documents are *"automatically compliant with legal standards."* No gen AI product guarantees legal compliance — output still needs human review.

> **Watch for absolute claims in distractors: "ensures all", "automatically guarantees", "eliminates the need for".** Gen AI products reduce effort and improve quality; they don't *guarantee* correctness or compliance. An option promising certainty is usually the wrong one.

---

## CONTENT GAP D — Vertex AI as an MLOps platform, not just a gen AI platform

**Q6** asked which components make Vertex AI a comprehensive **MLOps** platform "extending beyond just generative models". Three were correct:

| Component | MLOps role |
|---|---|
| **Vertex AI Pipelines** | Orchestrate and automate entire ML workflows as repeatable sequences — **the cornerstone of MLOps** |
| **Vertex AI Feature Store** | Central repository to store, share and serve features. **Prevents training-serving skew**, improves collaboration |
| **Vertex AI Model Garden** | Central hub to discover, use and manage pre-trained models — **the starting point of the development lifecycle**, not just a gen AI catalogue |

**"Training-serving skew"** is a term worth knowing: when the features a model sees in training differ from those it sees in production. The Feature Store exists largely to prevent it.

---

## CONTENT GAP E — PEFT precision

**Q24.** Two true advantages, one plausible falsehood.

**✅ PEFT gives you:**
- **Much lower compute and memory** — you train a small fraction of parameters, so large models become tunable on modest hardware.
- **Small, portable adapter files** — often just megabytes. Store many task-specific adaptations of one shared base model and **swap them at runtime** instead of keeping full model copies.

**❌ PEFT does NOT give you:** a *more knowledgeable* model. **Full fine-tuning updates all parameters and can incorporate new knowledge more deeply and broadly.** PEFT is an efficient **approximation** and may not match full fine-tuning's performance.

> **The framing: PEFT trades a little capability for a lot of efficiency and portability.** Any option claiming PEFT is *better* than full fine-tuning on quality or knowledge depth is wrong.

---

## Your 10-point pre-exam checklist

Read this immediately before you sit.

1. **Count the answers.** Plural noun in the stem = multiple correct. Never submit one box on a multi-select without rejecting the other three deliberately.
2. **Evaluate every option on its own merits**, true/false, before comparing them.
3. **People and process are real answers.** This is a leadership exam.
4. **Re-read the stem after choosing.** Does your answer cover *every* qualifier — "confidential", "multi-step", "monthly", "during a live call"?
5. **Refine = same solution, better. Expand = new solutions, elsewhere.**
6. **The model requests; your code executes.** Function calling never auto-runs.
7. **Complex/dynamic/multi-step calculation → Code Interpreter**, not a fixed API.
8. **Confidential or regulated + needs verification → RAG**, for *attribution*, not cost.
9. **Gemini for Workspace = inside Docs/Gmail/Sheets/Slides/Meet.** Enterprise search = **Vertex AI Search**.
10. **Distrust absolutes.** "Ensures all", "automatically guarantees", "eliminates the need for" — almost always the wrong option.

---

## What this predicts

Your 78% breaks down roughly as:

| Cause | Marks | Fixable? |
|---|---|---|
| Multi-select technique | ~4–6 | **Yes — pure discipline, no studying** |
| Adoption-lifecycle framework | ~3 | **Yes — one hour** |
| Content gaps (Code Interpreter, function-calling mechanics, Workspace boundaries) | ~3 | **Yes — this file** |
| Genuine Domain 2 product-recall depth | ~3–4 | Needs Skills Boost + flashcards |

**Most of your loss is technique and two specific gaps, not broad ignorance.** That's a much better position than a flat 78% suggests — a flat 78% across the board would need weeks. This needs a few days.

**Realistic target after this file plus two days on Domain 2: 88–92%.**

---

*Built 2026-09-15 from the eleven incorrect answers on the Pluralsight practice exam. Companion to [the main study guide](../study-guide/01-full-study-guide.md) and [the practice questions](01-practice-questions.md).*
