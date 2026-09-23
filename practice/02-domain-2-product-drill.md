# Domain 2 Drill — rebuilt against the OFFICIAL exam guide

**Rebuilt 2026-09-18.** The previous version of this file used Pluralsight's vocabulary (Vertex AI, Vertex AI Search, Agent Builder). **That vocabulary is obsolete for this exam.** This version is written from [Google's own exam guide](https://services.google.com/fh/files/misc/generative_ai_leader_exam_guide_english.pdf). See [the naming guide](../docs/04-product-naming-2026.md) for the full list of renames.

**Google's own statement on the certification page:**

> *"This exam was recently updated to reflect branding changes. Refer to the exam guide to review product names used on the exam."*

**Domain 2 is 35% of the exam — and it was my weakest domain on the practice exam, at 71%.** Most of Domain 2 is scenario → product. This file drills that, in the correct names.

---

## The rename map — learn the right-hand column

Your Pluralsight courses and the Dec-2025 practice exam teach the left. **The exam tests the right.**

| Pluralsight / old | **Official exam guide** |
|---|---|
| Vertex AI | **Agent Platform** (full name: *Gemini Enterprise Agent Platform*) |
| Vertex AI Search | **Agent Search** |
| Vertex AI Agent Builder | **Agent Studio** |
| AutoML | **Agent Platform AutoML** |
| Vertex AI Feature Store | **Agent Platform Feature Store** |
| Google Agentspace | **Gemini Enterprise** |
| NotebookLM | **Gemini Notebook API** |
| "Gemini AI Pro" | **Gemini Advanced** (Pluralsight's rename claim was wrong) |
| Model Garden | **Model Garden** ✅ unchanged |
| Google AI Studio | **Google AI Studio** ✅ unchanged |

### ⚠️ The safe strategy: know BOTH labels for each concept

Evidence is not perfectly clean, so don't bet everything on one vocabulary:

| Source | Naming | Date |
|---|---|---|
| **Google's certification page** — *"recently updated to reflect branding changes"* | **New** | Current |
| **Official exam guide PDF** — zero occurrences of "Vertex" | **New** | Current |
| Google's **own sample questions** form | **New** — confirmed 2026-09-21, every answer option | Content refreshed despite the "May 2025" label |
| Pluralsight courses + practice exam | **Old** | Dec 2025 – May 2026 |
| Third-party guides (nicheelab, Whizlabs) | Still say **old** | ~May 2026, now stale |

**Primary sources win — Google's own page and guide both say new.** But a live exam can lag its own guide, and some items may not have been rewritten.

**So: learn the function, and attach both labels to it.** "The managed enterprise search / RAG product" = **Agent Search**, *formerly Vertex AI Search*. If either name appears in an option, you recognise it. This costs you one extra word per product and removes the risk entirely.

**Verbatim phrasings from the guide — these are how the exam will word things:**
- *"Agent Search on Gemini Enterprise Agent Platform"*
- *"Agent Platform (e.g., Model Garden, Agent Search, Agent Platform AutoML)"*
- *"Determining when to use **Agent Studio** and **Google AI Studio**"*
- *"Gemini Enterprise (e.g., Gemini Notebook API, multimodal search, and custom agent capabilities)"*
- *"Gemini app and Gemini Advanced (e.g., Gems)"*

---

## Domain 2, as the guide actually structures it

Five subsections. Know what each is asking for.

### 2.1 — Google Cloud's strengths in gen AI

The guide wants you to describe:
- **Google's AI-first approach** and commitment to future innovation
- **An enterprise-ready AI platform** — the five adjectives: **responsible, secure, private, reliable, scalable**
- **A comprehensive AI ecosystem** — gen AI integrated across Google products and services
- **Google Cloud's open approach**
- **AI-optimized infrastructure** — the guide names: **hypercomputer, Google's custom-designed TPUs, GPUs, data centers, cloud computing**
- **User control over data** — security, privacy, governance, open and leading first-party models, pre-built and customizable solutions, agents
- **Democratizing AI development** — **low-code and no-code tools, pre-trained models, APIs**

### 2.2 — Prebuilt offerings that enable AI-powered work

Three products, and only three:

| Product | Guide's own examples |
|---|---|
| **Gemini app** and **Gemini Advanced** | **Gems** |
| **Gemini Enterprise** | **Gemini Notebook API**, **multimodal search**, **custom agent capabilities** |
| **Gemini for Google Workspace** | — |

### 2.3 — Improving the customer experience

| Category | Products |
|---|---|
| **External search offerings** | **Agent Search on Gemini Enterprise Agent Platform** · **Google Search** |
| **Customer Engagement Suite** | **Conversational Agents** · **Agent Assist** · **Conversational Insights** · **Google Cloud Contact Center as a Service (CCaaS)** |

> **CCaaS is the fourth member.** Your Pluralsight material only taught three.

### 2.4 — Empowering developers to build with AI

| Topic | Guide's examples |
|---|---|
| **Agent Platform** | **Model Garden**, **Agent Search**, **Agent Platform AutoML** |
| **RAG offerings** | **prebuilt RAG with Agent Search**, **RAG APIs** |
| **Building custom agents** | using **Agent Platform** |

### 2.5 — Tooling for gen AI agents

**Agent tool types — the guide names exactly four:** **extensions · functions · data stores · plugins**

**Google Cloud services and pre-built AI APIs for agent tooling — the guide's full list:**
Cloud Storage · databases · **Cloud Functions** · **Cloud Run** · Agent Platform · **Speech-to-Text API** · **Text-to-Speech API** · **Translation API** · **Document Translation API** · **Document AI API** · **Cloud Vision API** · **Cloud Video Intelligence API** · **Natural Language API** · **Google Cloud API Library**

**And one explicit decision:** *"Determining when to use Agent Studio and Google AI Studio."*

---

## The confusion pairs that matter now

| # | Confusion | Discriminator |
|---|---|---|
| 1 | **Agent Search** vs **Gemini for Google Workspace** vs **Gemini Notebook API** | **Agent Search** = enterprise/external search, deployable, grounded in company data. **Workspace** = assistant *inside* Gmail/Docs/Sheets/Slides/Meet. **Notebook API** = reasoning over *your* curated sources, part of Gemini Enterprise |
| 2 | **Conversational Agents** vs **Agent Assist** vs **Conversational Insights** vs **CCaaS** | **Agents** = virtual agent talking to the customer. **Assist** = live help to a *human* rep. **Insights** = analysis of *completed* conversations. **CCaaS** = the contact-centre platform itself |
| 3 | **Agent Studio** vs **Google AI Studio** | **Agent Studio** = building agents, enterprise. **Google AI Studio** = fast prototyping and experimentation. *The guide asks this directly.* |
| 4 | **Model Garden** vs **Agent Platform AutoML** | **Garden** = discover and deploy existing models. **AutoML** = train a custom model without ML coding |
| 5 | **Agent Search** vs **Grounding with Google Search** | **Agent Search** = your **first-party enterprise** data. **Google Search grounding** = **world data** |
| 6 | **Gemini app / Advanced** vs **Gemini Enterprise** vs **Gemini for Workspace** | **App/Advanced** = individual productivity (Gems). **Enterprise** = company-wide search + custom agents. **Workspace** = embedded in the productivity apps |
| 7 | **Document AI API** vs **Cloud Vision API** vs **Document Translation API** | **Document AI** = structured extraction from documents. **Vision** = general image analysis. **Document Translation** = translating whole documents |
| 8 | **Speech-to-Text** vs **Text-to-Speech** vs **Translation** | Direction of travel. Audio→text / text→audio / language→language |
| 9 | **Cloud Run** vs **Cloud Functions** | **Run** = containerised services. **Functions** = event-driven single functions. *Both are named in the guide for agent tooling* |
| 10 | **extensions** vs **functions** vs **data stores** vs **plugins** | The four tool types agents use to interact with the external environment |

---

## Drill — 40 questions

Answer fast, 20–30 seconds. **Several are multi-select and are not marked as such** — your known weak format. Watch for plural nouns.

### Block A — Which product? (1–15)

1. Employees need to ask natural-language questions across internal company data and get grounded, cited answers.
2. A support rep needs suggested replies surfaced **while on a live call**.
3. A team has clean tabular data and domain knowledge but no ML coders, and wants a custom predictive model.
4. An analyst wants to reason over 30 uploaded PDFs and produce a briefing.
5. A manager wants a reusable Gemini pre-configured with saved instructions for a recurring task.
6. An organisation wants company-wide multimodal search plus custom agents, governed.
7. A finance team needs structured fields extracted from scanned invoices.
8. A quality team wants trends and sentiment from **completed** support conversations.
9. A developer wants to prototype prompts quickly with minimal setup.
10. An enterprise wants to deploy an open-source model alongside Gemini from one catalogue.
11. A team wants to build a production agent with orchestration and governance.
12. A contact centre needs the underlying platform to run its customer service operation.
13. A model must answer using **live public web information**.
14. A model must answer from the company's **own internal documents**, with no infrastructure to build.
15. Recorded calls must be converted to text before analysis.

<details><summary><b>Answers 1–15</b></summary>

1. **Agent Search** (on Gemini Enterprise Agent Platform) 2. **Agent Assist** 3. **Agent Platform AutoML** 4. **Gemini Notebook API** 5. **Gems** 6. **Gemini Enterprise** 7. **Document AI API** 8. **Conversational Insights** 9. **Google AI Studio** 10. **Model Garden** 11. **Agent Studio** 12. **Google Cloud Contact Center as a Service (CCaaS)** 13. **Grounding with Google Search** 14. **Prebuilt RAG with Agent Search** 15. **Speech-to-Text API**

</details>

### Block B — The guide's own lists (16–28)

16. Name the four agent tool types.
17. Name the four members of the Customer Engagement Suite.
18. Name the three prebuilt offerings under "AI-powered work" (2.2).
19. Name the three components the guide gives as examples of Agent Platform.
20. Name Google Cloud's three grounding offerings.
21. Name the three types of grounding data the guide asks you to differentiate.
22. Name the five adjectives describing Google Cloud's enterprise-ready AI platform.
23. Name the components of Google Cloud's AI-optimized infrastructure.
24. Name the five layers of the gen AI landscape.
25. Name Google's four foundation models.
26. Which sampling parameters does the guide list?
27. Name the security tools the guide lists in section 4.2.
28. What three ways does the guide say Google Cloud democratizes AI development?

<details><summary><b>Answers 16–28</b></summary>

16. **Extensions, functions, data stores, plugins**
17. **Conversational Agents, Agent Assist, Conversational Insights, Google Cloud Contact Center as a Service**
18. **Gemini app / Gemini Advanced** (e.g. Gems) · **Gemini Enterprise** · **Gemini for Google Workspace**
19. **Model Garden, Agent Search, Agent Platform AutoML**
20. **Prebuilt RAG with Agent Search · RAG APIs · Grounding with Google Search**
21. **First-party enterprise data · third-party data · world data**
22. **Responsible, secure, private, reliable, scalable**
23. **Hypercomputer, custom-designed TPUs, GPUs, data centers, cloud computing**
24. **Infrastructure, Models, Platforms, Agents, Applications**
25. **Gemini, Gemma, Imagen, Veo**
26. **Token count, temperature, top-p (nucleus sampling), safety settings, output length.** ⚠️ **Top-k is NOT in the guide**
27. **Secure-by-design infrastructure, Identity and Access Management (IAM), Security Command Center, workload monitoring tools**
28. **Low-code and no-code tools, pre-trained models, APIs**

</details>

### Block C — APIs and services (29–34)

29. Which API extracts entities and sentiment from text you already hold?
30. Which API analyses video content?
31. Which two services does the guide name for running agent logic?
32. Which API translates an entire document rather than a string?
33. Which API performs general image analysis?
34. What does the guide call the broader collection of Google Cloud APIs available for agent tooling?

<details><summary><b>Answers 29–34</b></summary>

29. **Natural Language API** 30. **Cloud Video Intelligence API** 31. **Cloud Run and Cloud Functions — two answers** 32. **Document Translation API** 33. **Cloud Vision API** 34. **Google Cloud API Library**

</details>

### Block D — Traps and boundaries (35–40)

35. Which is **not** something Gemini for Google Workspace does?
A. Draft replies in Gmail · B. Summarise a Meet discussion · C. **Guarantee legal compliance of documents** · D. Interpret trends in Sheets

36. In function calling, what does the model produce?
A. An executed result · B. **A structured object naming the function and its arguments** · C. A retrieved document · D. A tuned adapter

37. Which grounding source would you use for a question about a company's own internal HR policy?
A. Google Search grounding · B. **First-party enterprise data** · C. Third-party data · D. World data

38. Which are components of Agent Platform per the guide?
A. Model Garden · B. Agent Search · C. Agent Platform AutoML · D. Conversational Insights

39. Which belong to the Customer Engagement Suite?
A. Agent Assist · B. Conversational Insights · C. Model Garden · D. Conversational Agents

40. When would you choose Google AI Studio over Agent Studio?
A. Building a governed production agent · B. **Quick prototyping and experimentation** · C. Training a custom model · D. Extracting fields from invoices

<details><summary><b>Answers 35–40</b></summary>

35. **C** — no gen AI product guarantees compliance. Distrust absolutes.
36. **B** — the model **requests**; your code **executes**.
37. **B** — first-party enterprise data. *Google Search grounding is world data.*
38. **A, B, C — three answers.** *Conversational Insights is Customer Engagement Suite.* **Did you pick three?**
39. **A, B, D — three answers.** *Model Garden is Agent Platform.* **Did you pick three?**
40. **B.**

</details>

---

## Scoring

| Score | Action |
|---|---|
| **< 28/40** | Re-read the decoded exam guide, then redo |
| **28–33** | Drill the confusion pairs, redo tomorrow |
| **34–37** | Good — target only your misses |
| **38–40** | Domain 2 closed. Move to Business strategies (your 63%) |

**Check questions 31, 38 and 39 separately — they are multi-select.** Under-selecting cost you ~5 marks on the practice exam and it is the cheapest fix available.

---

## What is no longer worth studying

Cut from the previous version of this file because the official guide never names them: Dataplex, Dataprep, Dataflow, Dataproc, Pub/Sub, BigQuery ML, Looker, Cloud DLP, Cloud KMS, VPC Service Controls, GKE, Model Registry, Vector Search, Gemini Cloud Assist, Gemini Code Assist, Gemini in BigQuery/Looker/SecOps/Firebase, Chirp, Lyria, PaLM 2, Translation Hub, Vertex AI Workbench, Colab Enterprise.

**Two caveats.** Section 1.1 does say *"the Google Cloud tools for each stage"* of the ML lifecycle, so **data ingestion and preparation tools stay in scope** — just at a lower priority than Domain 2's named products. And the guide's security list is narrower than my earlier material claimed: **only** secure-by-design infrastructure, IAM, Security Command Center, and workload monitoring tools.

---

*Rebuilt 2026-09-18 from Google's official exam guide, confirmed against the downloaded PDF. Where this file and the exam guide disagree, the exam guide wins.*
