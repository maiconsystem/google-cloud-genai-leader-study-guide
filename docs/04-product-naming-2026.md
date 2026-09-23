# The 2026 renaming — why most study material is out of date

**This is the highest-value page in this repository.** It is also the mistake I nearly made.

---

## What happened

In 2026 Google folded its AI product line under the **Gemini Enterprise** brand. Vertex AI — the name on almost every tutorial, course and practice test written before 2026 — is now the **Gemini Enterprise Agent Platform**, and most of the products under it were renamed with it.

The exam guide and Google's official sample questions use the **new** names. A lot of paid study material still uses the old ones.

---

## The rename table

| Old name (in most study material) | Current name (what the exam uses) |
|---|---|
| **Vertex AI** | **Gemini Enterprise Agent Platform** — often shortened to **Agent Platform** |
| **Vertex AI Search** | **Agent Search** |
| **Vertex AI Agent Builder** | **Agent Studio** |
| **Agentspace** | **Gemini Enterprise** |
| **NotebookLM** | **Gemini Notebook** (the API is the Gemini Notebook API) |
| **AutoML** | **Agent Platform AutoML** |
| **Vertex AI Feature Store** | **Agent Platform Feature Store** |
| **Dialogflow CX** | **Conversational Agents** |

**Names that did *not* change** — do not over-correct:

- **Model Garden**
- **Google AI Studio** (the prototyping tool — distinct from Agent Studio)
- **Gemini, Gemma, Imagen, Veo**
- **Gemini Advanced**
- **Agent Assist**, **Conversational Insights**
- **BigQuery, Cloud Run, Cloud Functions, Cloud Storage, Pub/Sub, IAM, Security Command Center**
- All the pre-built APIs: Speech-to-Text, Text-to-Speech, Translation, Document AI, Vision, Video Intelligence, Natural Language

---

## How this was verified

I got this wrong first. I told myself the exam would still use "Vertex AI" because the practice exam I had taken used it. That practice exam was dated **December 2025** — before the rebrand. Three checks settled it:

1. **The official exam guide PDF.** I extracted the full text and searched it. **The word "Vertex" does not appear once.** Every product is named in the new vocabulary.
2. **The certification page.** [cloud.google.com/learn/certification/generative-ai-leader](https://cloud.google.com/learn/certification/generative-ai-leader) carries an explicit branding-update notice.
3. **Google's official sample questions.** Every *answer option* uses the new names — "Agent Search on Gemini Enterprise Agent Platform", "Gemini Enterprise", "Gemini Notebook", "Google Workspace with Gemini", "Google Cloud Contact Center as a Service". Old names survive only in a few explanatory feedback paragraphs, which is exactly what a document mid-transition looks like.

**The lesson is more general than the names:** when a practice test and the official exam guide disagree, the guide wins, and the date on your study material matters as much as its quality.

---

## What to do about it

**Learn both columns.** Recognise the old names, because course videos and question banks are full of them — but **answer with the new ones**.

In practice the exam asks *what a product does*, not what it is called, and most questions name the product in the option rather than the stem. So the risk is not that you fail to recognise "Agent Search"; it is that you see "Vertex AI Search" in your notes, never connect it to "Agent Search" in the option list, and rule out the correct answer.

**The one that actually catches people:**

> **Agent Studio** (build production agents, formerly Agent Builder) versus **Google AI Studio** (prototype quickly, unchanged name).
>
> The exam guide asks this directly: *"Determining when to use Agent Studio and Google AI Studio."* Two similar names, two different jobs. **Agent Studio = enterprise, governed, production. Google AI Studio = fast, minimal setup, experimentation.**

---

## Before you sit

Google changes product names faster than anyone can maintain a study repo. **Open the [official exam guide](https://services.google.com/fh/files/misc/generative_ai_leader_exam_guide_english.pdf) the week you sit and skim the product names.** It takes ten minutes and it is the cheapest insurance available.

If you find a name in this repo that Google has since changed, please [open an issue](../CONTRIBUTING.md).

---

*Verified 21 September 2026 against the official exam guide, the certification page and Google's official sample questions.*
