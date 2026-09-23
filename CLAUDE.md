# CLAUDE.md

Guidance for Claude Code (claude.ai/code) when working in this repository.

## What this repository is

**Not a codebase.** It is a study guide for the **Google Cloud Certified — Generative AI Leader** exam, written as Markdown. There is no build, no test suite, no lint step and no dependencies. Every change is an edit to a Markdown file.

The material was written by someone who passed the exam in September 2026, and the repository is published so that others can use it. It is **read-only to the public**: issues are welcome, pull requests are not accepted.

## Structure

| Path | Contents |
|---|---|
| `README.md` | Landing page: the 8-step path, the file map, and the 2026 renaming warning |
| `docs/` | How to use the repo, exam facts, study plans, the product renaming, exam technique, resources |
| `courses/` | Summaries of the video courses and learning paths, course by course and module by module |
| `study-guide/` | The main guide (four domains), a quick recall sheet, the product memorisation table, the exam-morning sheet |
| `practice/` | 60 original practice questions, a 40-question Domain 2 product drill, and an analysis of wrong answers |

Numeric file prefixes (`01-`, `02-`) indicate **reading order within a folder**, not priority.

## The facts that govern the content

- **Exam:** 50–60 questions, 90 minutes, $99, foundational level, no prerequisites, valid 3 years.
- **Domains and approximate weights:** Fundamentals ~30% · Google Cloud's gen AI offerings ~35% · Techniques to improve model output ~20% · Business strategies ~15%.
- **It is a business/leadership exam, not a technical one.** Google's description: the certified person's expertise is *"in strategic leadership and influence, not technical implementation."* Content that drifts toward implementation detail is off-target for this exam.
- **The authoritative source is Google's [official exam guide](https://services.google.com/fh/files/misc/generative_ai_leader_exam_guide_english.pdf).** Where anything in this repository conflicts with it, the guide wins and the repository is wrong.

## 🔴 Product naming — the thing to get right

Google rebranded its AI products in 2026. **The exam uses the new names; most study material still uses the old ones.**

| Old | Current |
|---|---|
| Vertex AI | **Gemini Enterprise Agent Platform** (Agent Platform) |
| Vertex AI Search | **Agent Search** |
| Vertex AI Agent Builder | **Agent Studio** |
| Agentspace | **Gemini Enterprise** |
| NotebookLM | **Gemini Notebook** |
| AutoML | **Agent Platform AutoML** |
| Vertex AI Feature Store | **Agent Platform Feature Store** |
| Dialogflow CX | **Conversational Agents** |

Unchanged: Model Garden · Google AI Studio · Gemini, Gemma, Imagen, Veo · Gemini Advanced · Agent Assist · Conversational Insights · the pre-built APIs · BigQuery, Cloud Run, Cloud Functions, IAM, Security Command Center.

`docs/04-product-naming-2026.md` is the canonical page for this. `study-guide/03-product-table.md` is written in the current vocabulary. `study-guide/01-full-study-guide.md` was built from pre-rebrand course transcripts and still contains old names in places — **that is deliberate and flagged**, because learners meet the old names in courses and need to translate. Do not bulk-rename it without preserving those old-name references.

## Rules for editing

- **Verify before changing a product fact.** Check Google's current exam guide or documentation, and say in the commit message what was checked. A confidently wrong product mapping is worse than no mapping.
- **No exam dumps, ever.** All questions here are original, written to match the style of the public sample questions. Never add real exam items, and never add content sourced from a brain-dump site. This is both an integrity rule and a condition of Google's exam agreement.
- **Keep cross-links working.** Files reference each other with relative links; renaming or moving a file means updating the links that point at it, including from `README.md`.
- **Match the existing voice:** direct, second person, tables over prose, exam traps called out inline with `>` blockquotes. Claims are hedged where they should be — "approximate", "verify against the current guide" — and that hedging is deliberate.
- **No personal information.** No names of employers or colleagues, no contact details, no career or job-search material, no client work. The author's own results (practice-exam scores, the four error patterns) appear because they are pedagogically useful, not as biography.
- **Diagrams are Mermaid**, rendered natively by GitHub. Keep them small enough to read on a phone.

## If you cloned this repo to study with

Most people reading this file will have forked or cloned the repository to prepare for the exam with Claude's help. **That is the intended use.** In a clone, the rules above still apply to the *content* — Claude should not invent product facts or add dump material — but the repository is yours to change however you like.

Things Claude is well suited to here, and how to ask for them:

| Ask | What Claude should do |
|---|---|
| *"Quiz me on Domain 2"* | Pull scenarios from `study-guide/03-product-table.md` and `practice/02-domain-2-product-drill.md`, ask one at a time, wait for an answer before revealing, and **keep a running tally by domain** |
| *"Write 20 more questions on grounding and RAG"* | Match the format in `practice/01-practice-questions.md` exactly: stem, four options, then an explanation of why each wrong option fails. Append to a new file rather than editing the originals |
| *"I scored 72%, here are my wrong answers"* | Look for the **pattern**, not just the facts — compare against the four patterns in `practice/03-common-mistakes.md` — then propose a study order, weighted by domain |
| *"Build me a 10-day plan, I have 90 minutes a day"* | Adapt `docs/03-study-plan.md` to the real constraint. Keep the sequencing rule: diagnose early, then study only what the scores point at |
| *"Translate the product table into Portuguese"* | Translate, but **keep every product name in English** — the exam is sat in English unless the candidate chose another language, and product names are not translated |
| *"Explain the difference between X and Y"* | Answer from the repo first. If the repo does not cover it, say so, check Google's current documentation, and offer to add it |

Two cautions worth repeating to anyone studying this way:

- **Claude's training data may predate the 2026 renaming.** If Claude says "Vertex AI Search" in a generated question, that is the old name leaking through — check it against `docs/04-product-naming-2026.md` and Google's current exam guide.
- **Generated practice questions are practice, not prediction.** They train recognition and technique. Neither Claude nor this repository knows what is on the exam, and any claim otherwise should be treated as a hallucination.

## Common tasks

- **Adding a resource:** `docs/06-resources.md`, in the correct section, with one line on *why* it is worth the reader's time. Verify the link resolves.
- **Recording a product rename:** update `docs/04-product-naming-2026.md`, `study-guide/03-product-table.md`, `CLAUDE.md` and the `README.md` table together — those four must agree.
- **Adding practice questions:** match the existing format exactly — stem, four options with the correct one in bold, then a `>` blockquote explaining why each distractor fails, not just why the answer is right. The explanation is the product; the question is only the delivery.
- **Updating exam logistics:** `docs/02-exam-facts.md` is the single source; `README.md` repeats only the headline figures.
