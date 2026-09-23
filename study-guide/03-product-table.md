# The Memorisation Table — every product that can appear on the exam

**Built from [Google's official exam guide](https://services.google.com/fh/files/misc/generative_ai_leader_exam_guide_english.pdf).** Names in **bold** are the exam's current vocabulary; *italics in the third column* are the old Pluralsight names — **learn both**, because a live exam can lag its own guide.

**How to use:** cover the middle column, read the name, say what it's for. Then cover the left column, read the purpose, say the name. The second direction is harder and is the one the exam actually tests.

Eleven groups. Do one group at a time — chunking is what makes this stick.

---

## 1. Foundation models — Google's own (4)

| Product | What it's for | Also known as |
|---|---|---|
| **Gemini** | The flagship **multimodal** model — text, images, audio, video, code. Widest range, long context, enterprise reasoning | — |
| **Gemma** | **Open and lightweight.** Runs on modest hardware or locally. Deep fine-tuning, privacy-sensitive and on-prem use | — |
| **Imagen** | **Text → image.** Photorealistic generation, accepts reference images. Built on a **diffusion** model | — |
| **Veo** | **Text/image/video → video.** Generation and editing, coherent motion, native audio. **The most expensive** | — |

> **Cost order, cheapest first: Gemma → Imagen → Gemini → Veo.**

---

## 2. Gemini for people — the productivity layer (4)

| Product | What it's for | Also known as |
|---|---|---|
| **Gemini app** | Personal assistant — research, writing, reasoning | — |
| **Gemini Advanced** | The paid tier. **Gems** live here | *Pluralsight wrongly called this "Gemini AI Pro"* |
| **Gems** | A **reusable Gemini persona with saved instructions**, shareable across a team | — |
| **Gemini for Google Workspace** | Gemini **inside Gmail, Docs, Sheets, Slides, Meet.** Turns you from content *creator* into *editor and director* | — |

> **Boundary:** Workspace Gemini is **not** an enterprise search product and **guarantees no compliance.**

---

## 3. Enterprise search and grounding (5)

| Product | What it's for | Also known as |
|---|---|---|
| **Gemini Enterprise** | Company-wide **multimodal search + custom agents**, governed | *Google Agentspace* |
| **Gemini Notebook API** | Reasoning grounded in **your own curated sources**; part of Gemini Enterprise | *NotebookLM* |
| **Agent Search** | **Enterprise search and RAG** grounded in your company data | *Vertex AI Search* |
| **Prebuilt RAG with Agent Search** | RAG **out of the box** — no retrieval infrastructure to build | — |
| **RAG APIs** | Build your own RAG pipeline programmatically | — |
| **Grounding with Google Search** | Ground answers in **live public web data** | — |

> **Three grounding data types the guide asks you to distinguish: first-party enterprise data · third-party data · world data.**
> Agent Search = first-party. Google Search grounding = world data.

---

## 4. Customer Engagement Suite (4)

| Product | What it's for | Also known as |
|---|---|---|
| **Conversational Agents** | The **virtual agent** talking to the customer; multi-turn branching dialog | *Dialogflow CX* |
| **Agent Assist** | **Live, during the call** — real-time suggestions to a **human** rep | — |
| **Conversational Insights** | **After** the interaction — trends, sentiment, recurring issues | — |
| **Google Cloud Contact Center as a Service (CCaaS)** | The contact-centre **platform itself** | — |

> **The single most-tested distinction in this group: Agent Assist = live. Conversational Insights = afterwards.**

---

## 5. Agent Platform and its components (5)

| Product | What it's for | Also known as |
|---|---|---|
| **Agent Platform** | The unified platform — build, deploy and manage models and agents | *Vertex AI*. Full name: *Gemini Enterprise Agent Platform* |
| **Model Garden** | **Discover and deploy** Google, open-source and third-party models from one catalogue | — |
| **Agent Platform AutoML** | Train a **custom model with no ML coding** — good data, no ML engineers | *AutoML* |
| **Agent Platform Feature Store** | Serve **consistent features** across models; prevents **training-serving skew** | *Vertex AI Feature Store* |
| **Agent Studio** | Build **production agents** — orchestration, grounding, connectors, governance | *Vertex AI Agent Builder* |

---

## 6. The two Studios (2)

| Product | What it's for |
|---|---|
| **Google AI Studio** | **Fast prototyping** and experimentation, minimal setup |
| **Agent Studio** | **Enterprise agent building** — governance, production |

> The guide asks this directly: *"Determining when to use Agent Studio and Google AI Studio."*

---

## 7. Pre-built AI APIs (8)

| API | In → Out |
|---|---|
| **Speech-to-Text API** | Audio → text |
| **Text-to-Speech API** | Text → audio |
| **Translation API** | Language → language |
| **Document Translation API** | Translates a **whole document**, not a string |
| **Document AI API** | Scanned invoices/contracts/forms → **structured fields** |
| **Cloud Vision API** | Image → labels, objects, text detection |
| **Cloud Video Intelligence API** | Video → labels, scenes, objects, transcription |
| **Natural Language API** | Text you already hold → entities, sentiment, syntax |

> **Google Cloud API Library** — the guide's name for the wider catalogue these sit in.

---

## 8. Services agents use to act (4)

| Service | What it's for |
|---|---|
| **Cloud Storage** | Unstructured content — documents, images, media |
| **Databases** | Structured records an agent retrieves or writes |
| **Cloud Run** | **Containerised** services, serverless, auto-scaling |
| **Cloud Functions** | **Event-driven** single functions |

---

## 9. Agent tool types — the guide names exactly four (4)

| Tool type | What it does |
|---|---|
| **Extensions** | Connect the agent to external services |
| **Functions** | Model emits a **structured request**; **your code executes it** — the model never does |
| **Data stores** | Retrieve from your documents or knowledge base (grounding) |
| **Plugins** | Packaged add-on capabilities |

> **Code Interpreter** — generates and **runs code in a sandbox**, for **complex, multi-step, dynamic calculations**. Not in the guide's list of four, but it appeared on the practice exam.

---

## 10. Security and governance (5)

| Item | What it's for |
|---|---|
| **SAIF** (Secure AI Framework) | Google's framework for securing AI **across the whole lifecycle** |
| **Secure-by-design infrastructure** | Security built into the stack from hardware upward |
| **Identity and Access Management (IAM)** | **Who can do what** — least privilege, role-based |
| **Security Command Center** | Central **alerts, threat indicators, system health** |
| **Workload monitoring tools** | Watching running systems for anomalies |

> ⚠️ **These five are the entire security list in the exam guide.** Cloud DLP, KMS and VPC Service Controls are *not* named — don't over-invest in them.

---

## 11. AI-optimised infrastructure (5)

| Component | What it's for |
|---|---|
| **Hypercomputer** | Coordinates thousands of compute resources for distributed training and large-scale inference |
| **TPUs** | Google's **custom-designed** AI accelerators — better price-performance than generic GPUs |
| **GPUs** | General-purpose parallel accelerators |
| **Data centers** | The physical backbone — availability, low latency, global reach |
| **Cloud computing** | The delivery model underneath it all |

---

## Reverse lookup — trigger phrase → product

**This is how the exam actually works.** A scenario contains a trigger; you name the product. Drill this direction hardest.

| If the question says… | The answer is |
|---|---|
| "natural-language questions over internal company data", "grounded, cited answers" | **Agent Search** |
| "live public web information", "current events" | **Grounding with Google Search** |
| "no retrieval infrastructure to build", "out of the box" | **Prebuilt RAG with Agent Search** |
| "while the agent is on the call", "real-time suggestions to the rep" | **Agent Assist** |
| "completed conversations", "trends and sentiment", "after the interaction" | **Conversational Insights** |
| "virtual agent", "handles the customer", "multi-turn" | **Conversational Agents** |
| "the contact centre platform" | **CCaaS** |
| "reusable", "saved instructions", "same persona every time" | **Gems** |
| "my uploaded documents", "brief / quiz / mind map from these sources" | **Gemini Notebook API** |
| "company-wide search plus custom agents, governed" | **Gemini Enterprise** |
| "inside Gmail / Docs / Sheets / Slides / Meet" | **Gemini for Google Workspace** |
| "good data, domain knowledge, **no ML coding expertise**" | **Agent Platform AutoML** |
| "open-source model **alongside** Gemini", "one catalogue", "discover and deploy" | **Model Garden** |
| "quick prototype", "minimal setup", "experiment with prompts" | **Google AI Studio** |
| "production agent", "governance", "orchestration and connectors" | **Agent Studio** |
| "consistent features across models", "training-serving skew" | **Agent Platform Feature Store** |
| "scanned invoices", "extract structured fields", "forms" | **Document AI API** |
| "translate an entire document" | **Document Translation API** |
| "entities and sentiment from existing text" | **Natural Language API** |
| "analyse video", "find the moment in the footage" | **Cloud Video Intelligence API** |
| "convert recorded calls to text" | **Speech-to-Text API** |
| "complex, multi-step calculations, securely" | **Code Interpreter** |
| "who can access what", "least privilege" | **IAM** |
| "central security alerts and threat indicators" | **Security Command Center** |
| "custom AI chips", "better price-performance than GPUs" | **TPUs** |
| "coordinates thousands of compute resources" | **Hypercomputer** |
| "runs on modest hardware", "local", "privacy-sensitive", "open model" | **Gemma** |
| "photorealistic image from a text prompt" | **Imagen** |
| "generate video with coherent motion" | **Veo** |
| "text, images, audio and video together", "cross-modal" | **Gemini** |

---

## ✅ CONFIRMED by Google's own sample questions (2026-09-21)

**Google's own sample questions use the NEW names in every answer option.** This is now settled: **Agent Search on Gemini Enterprise Agent Platform**, **Gemini Enterprise Agent Platform**, **Gemini Enterprise**, **Gemini Notebook**, **Google Workspace with Gemini**, **Conversational Agents**, **Google Cloud Contact Center as a Service**, **Cloud Functions**, **BigQuery** all appear as options.

*Residual old names survive only in a few explanatory feedback paragraphs ("Vertex AI Studio", "Vertex AI Platform") — never in the options themselves. That's a document mid-transition, and it confirms the direction.*

### Google's own definitions — memorise these phrasings

These come verbatim from the sample-question feedback, so they are as close to the exam's voice as you can get.

| Product | Google's own words |
|---|---|
| **Gemini Enterprise Agent Platform** | *"Google Cloud's unified ML platform designed to streamline the entire ML workflow… encompasses data preparation, model training, evaluation, deployment, and monitoring"* |
| **Gemini Enterprise** | *"Helps teams use their company's information more effectively by creating customized agents that can access and understand data from various sources, regardless of where that data is stored"* — **internal employees, across scattered systems** |
| **Gemini Notebook** | *"An AI-first notebook grounded in user-provided documents"* — upload multiple documents, ask questions, request summaries, save insights as notes. **Source-based answers, traceable back to the original** |
| **Agent Search** | *"Building search applications over structured and unstructured data"* |
| **Google Workspace with Gemini** | *"Integrates generative AI into productivity tools like Docs and Drive"* — **individual document-level tasks** |
| **CCaaS** | *"A complete cloud-based contact center solution"* — integrates phone/text/email channels, omnichannel, agent routing, CRM integration |
| **Conversational Agents** | *"Building customer-facing chatbots to automate interactions and answer customer inquiries"* |
| **AI agent** | *"An application that tries to achieve a goal by observing the world and acting upon it using the tools it has at its disposal"* |
| **Gen AI model** | *"A sophisticated algorithm trained on vast amounts of data to learn patterns and relationships"* |

### 🔴 The four-way cluster the sample questions test hardest

Four questions turned on telling these apart. Learn the *user* and the *scope*:

| Product | Who uses it | Scope |
|---|---|---|
| **Gemini Notebook** | An individual/team researching | **A specific set of documents you upload** |
| **Gemini Enterprise** | Internal employees | **Across many internal systems** — sales, inventory, marketing |
| **Agent Search** | Developers building a search app | **Search over structured + unstructured data** |
| **Google Workspace with Gemini** | Anyone working in Docs/Gmail | **Inside the document you're editing** |

> **Discriminators:** *"analyse several reports I uploaded"* → **Notebook**. *"employees waste time searching across internal systems"* → **Enterprise**. *"build a search application"* → **Agent Search**. *"inside Gmail and Docs"* → **Workspace**.

---

## The five-minute version — if you only revise once

1. **Agent Search** = enterprise search/RAG on your data. *(was Vertex AI Search)*
2. **Agent Studio** = build production agents. **Google AI Studio** = prototype fast.
3. **Model Garden** = discover and deploy any model. **AutoML** = train one without coding.
4. **Agent Assist = live. Conversational Insights = after.**
5. **Gems** = reusable persona. **Gemini Notebook API** = reason over my documents. **Workspace** = inside Gmail/Docs.
6. **Gemini Enterprise** = company-wide search + agents. *(was Agentspace)*
7. Four tool types: **extensions, functions, data stores, plugins.**
8. Three grounding types: **first-party, third-party, world data.**
9. Four models: **Gemini** (multimodal), **Gemma** (open/light), **Imagen** (images), **Veo** (video).
10. Security is only: **secure-by-design, IAM, Security Command Center, workload monitoring** — plus **SAIF** as the framework.

---

*Built 2026-09-21 from Google's official Generative AI Leader exam guide and its official sample questions. Where this table and the exam guide disagree, the guide wins.*
