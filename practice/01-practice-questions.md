# Gen AI Leader — 60 Practice Questions with Full Explanations

**Companion to [the main study guide](../study-guide/01-full-study-guide.md).** Work the guide first, then these.

**Question count by domain matches the real exam weighting:**

| Block | Domain | Weight | Questions |
|---|---|---|---|
| A | Fundamentals of gen AI | ~30% | 18 (Q1–18) |
| B | Google Cloud's gen AI offerings | ~35% | 21 (Q19–39) |
| C | Techniques to improve model output | ~20% | 12 (Q40–51) |
| D | Business strategies | ~15% | 9 (Q52–60) |

---

## ⚠️ READ THIS FIRST — two things that change how you study

### 1. Confirmed exam logistics (from Google, 2026-09-11)

| | |
|---|---|
| **Questions** | **50–60 multiple choice** |
| **Duration** | **90 minutes** (≈95 seconds per question) |
| **Cost** | **$99 USD** + tax |
| **Format** | Online-proctored or onsite-proctored |
| **Prerequisites** | **None** |
| **Valid for** | **3 years** |
| **Languages** | English, Japanese, Spanish, Portuguese |
| **Official sample questions** | <https://forms.gle/soztS7Q74AXBncATA> |
| **Official exam guide** | <https://services.google.com/fh/files/misc/generative_ai_leader_exam_guide_english.pdf> |
| **Official study guide** | <https://services.google.com/fh/files/misc/generative_ai_leader_study_guide_english.pdf> |
| **Skills Boost path** | <https://www.cloudskillsboost.google/paths/1951> |

**Domain weights confirmed as exactly 30 / 35 / 20 / 15.** Good news: that's what the study guide already assumed.

*One note on cost: your sprint plan says "~92 EUR (exam only)". The listed price is **$99 USD** plus tax — close enough, but budget from the dollar figure.*

### 2. 🔴 Google has renamed the products. Your course material uses the old names.

Verified against Google's own pages on 2026-09-11:

| Old name (what Pluralsight teaches) | Current name |
|---|---|
| **Vertex AI** | Google's page now reads **"Gemini Enterprise Agent Platform (formerly Vertex AI)"** |
| **Google Agentspace** | **Gemini Enterprise** (renamed Oct 2025) |

**What to do about it — practical guidance, not panic:**

- **Learn the function, not just the label.** "The managed platform where you discover models, train, deploy, monitor and run pipelines" is the durable knowledge. Whether it's called Vertex AI or Gemini Enterprise Agent Platform, the *job it does* is what the scenario questions describe.
- **Be able to recognise both names.** If an option says "Vertex AI Model Garden" and another says "Gemini Enterprise", treat them as potentially the same family and decide on function.
- **The official exam guide is authoritative, not blogs and not this file.** Certification exams lag product rebrands by months. Download the exam guide PDF and Skills Boost path and see which vocabulary *they* use — that's what you'll be tested on.
- **These questions use the Pluralsight/Vertex AI vocabulary**, because that's what your course material and most current exam prep still use. Where a rename is relevant I flag it inline.

### 3. On "real exam questions" from the internet

Searching turns up sites advertising "actual exam questions" and dumps. **Don't.** Three reasons, in order of importance: you will sign Google's exam agreement, and using leaked items violates it and can void your certification; the dumps are frequently *wrong*, teaching you incorrect answers you then confidently select; and they train recognition of specific items rather than the reasoning the exam actually tests.

**What I've done instead:** cross-referenced the official exam guide topic list (including topics your Pluralsight courses never covered — see Section 0 below) and written 60 original questions in the authentic style, modelled on the 14 official example questions in your courses' own "Exam Question Review" modules. That's legitimate, and it's better preparation.

---

## SECTION 0 — Gap-fill: topics on the exam guide that Pluralsight did NOT cover

**Read this before the questions.** The official topic list includes these; your four courses skipped or barely touched them. Questions on them appear in the blocks below.

**Deep learning.** The exam tests **AI ⊃ ML ⊃ deep learning ⊃ gen AI** as a nesting. Deep learning is ML using multi-layer neural networks; it is a *subset of machine learning*, and generative AI is built on deep-learning architectures (notably the transformer). Pluralsight taught AI ⊃ ML ⊃ Gen AI but skipped the deep-learning layer.

**The full Google Cloud AI API list.** Pluralsight named only Text-to-Speech and Translation. The exam guide also lists: **Speech-to-Text**, **Natural Language API**, **Vision API**, **Video Intelligence API**, and **Document AI**. Know what each ingests and emits.

**Customer Engagement Suite.** The umbrella name for the contact-centre products: **Conversational Agents** (virtual agents), **Agent Assist** (live help for human reps), **Conversational Insights** (post-interaction analytics). Pluralsight taught the three components without consistently naming the suite.

**Google Agentspace / Gemini Enterprise.** Enterprise-grade agents plus company-wide search across your business applications, with governance. Pluralsight covered "Gemini Enterprise capabilities" but not the Agentspace name that older exam material uses.

**Metaprompting.** Using the model to help write or improve your prompts — asking the LLM to generate or refine a prompt for a task. Appears on the exam guide's prompting list; absent from the Pluralsight courses.

**Top-down vs bottom-up AI adoption.** *Top-down* = leadership-driven, centrally funded and mandated, aligned to strategy, faster to scale but risks poor fit with real workflows. *Bottom-up* = individual teams and employees adopting tools organically, strong workflow fit and enthusiasm, but risks shadow AI, fragmentation and no governance. **Mature organisations combine both** — leadership sets guardrails and platform, teams innovate inside them. (This is the same logic as the centralized/federated/**hybrid** platform models from your governance course.)

**Context window as a model-selection criterion.** Pluralsight covered context windows conceptually; the exam guide lists **context window capacity** explicitly as a factor when *choosing between models*, alongside modality, performance, and open vs proprietary availability.

---

## BLOCK A — Fundamentals of gen AI (Q1–18, ~30%)

**Q1.** Which statement correctly describes the relationship between the terms?

A. Machine learning is a subset of generative AI
B. **Deep learning is a subset of machine learning, and generative AI is built on deep learning architectures**
C. Natural language processing is a subset of machine learning
D. Artificial general intelligence is the current commercial form of narrow AI

> **B.** **D** is always wrong on this exam — AGI is theoretical and does not exist commercially. **A** inverts the hierarchy: gen AI is an application *of* ML, not its parent. **C** is the subtle one: NLP is a subfield of **AI** sitting *alongside* ML, not inside it — Pluralsight states this explicitly. **B** is the correct nesting: AI ⊃ ML ⊃ deep learning, with gen AI built on deep-learning architectures such as the transformer.

**Q2.** A bank wants to detect transactions that don't fit normal customer behaviour. There are no labels marking which past transactions were fraudulent. Which approach?

A. Supervised learning
B. **Unsupervised learning**
C. Reinforcement learning
D. Prompt tuning

> **B.** **D** is a technique for adapting a model's behaviour, not an ML paradigm for detection. **C** requires a reward/penalty feedback loop with an agent acting in an environment — not described. **A** is the trap: fraud detection is *often* supervised, but only when labels exist. The stem explicitly says **no labels**. **B** is right: unsupervised learning detects **anomalies** by spotting data points that don't fit expected behaviour — one of its three canonical uses alongside segmentation and topic discovery.

**Q3.** Which is the best description of what makes generative AI different from traditional machine learning?

A. It runs on TPUs rather than GPUs
B. It requires labelled training data
C. **It uses data to create new content rather than primarily to make predictions**
D. It eliminates the need for data governance

> **C.** **D** is the opposite of true — gen AI *increases* governance requirements. **B** is wrong because foundation models are trained largely through self-supervised learning on unlabelled, unstructured data. **A** confuses hardware with capability; both run on either. **C** is the definitional distinction: ML predicts or forecasts; gen AI **creates**.

**Q4.** Which four functions does generative AI provide, according to Google's framing?

A. Classification, regression, clustering, forecasting
B. **Creation, summarisation, discovery of insights, automation of tasks**
C. Training, tuning, deployment, monitoring
D. Ingestion, preparation, inference, retraining

> **B.** **A** lists traditional ML tasks. **C** lists model lifecycle stages. **D** lists data pipeline stages. **B** is the gen AI capability set: create new content, condense long content, uncover insights and patterns hidden in data, and automate tasks that previously required human judgment.

**Q5.** A model produces a detailed, confident answer citing a research paper that does not exist. What is this, and why does it happen?

A. Drift, because inputs have evolved
B. Bias, because training data was imbalanced
C. **Hallucination, because the model generates from patterns and probabilities rather than verifying facts**
D. Prompt injection, because a user manipulated the input

> **C.** **D** requires a malicious input, not described. **A** is degradation *over time*; this is a single wrong answer. **B** concerns systematically skewed outputs across groups, not fabrication. **C** is exactly it — and the *why* matters: the model isn't checking facts, it's producing statistically plausible continuations. That's why grounding (giving it real material to reference) is the primary mitigation.

**Q6.** Which is the correct definition of a context window?

A. The time period covered by the model's training data
B. **The amount of information a model can hold at one time while generating a response**
C. The maximum number of users who can query a model concurrently
D. The geographic region where inference occurs

> **B.** **A** describes the knowledge cutoff. **C** is a concurrency/throughput concept. **D** is data residency. **B** is the definition — the model's short-term memory. Know the consequence too: **a larger context window reduces hallucinations**, because the model can rely on actual text in the input rather than guessing.

**Q7.** A business analyst wants better results from Gemini by rewriting their request with clearer instructions and examples. A separate ML team plans to adapt the model's internal behaviour by training it on hundreds of domain examples. Which pair of terms describes these?

A. Fine-tuning and RAG
B. **Prompt engineering and prompt tuning**
C. Grounding and metaprompting
D. Few-shot prompting and zero-shot prompting

> **B.** **D** describes two variants of the same activity (both are prompting), not two different activities. **C** mismatches: grounding connects to data sources; metaprompting is using the model to write prompts. **A** is close but wrong — RAG isn't what the analyst is doing. **B** is the distinction the exam loves: **prompt engineering** = changing the prompt, low effort, immediate, accessible to end users and analysts, **no model change**. **Prompt tuning** = altering model behaviour with many examples, moderate effort, slower, performed by **ML specialists**.

**Q8.** Roughly what proportion of enterprise information is unstructured, and why does this matter for gen AI?

A. 20–30%; gen AI works best on structured tables
B. **80–90%; generative models learn patterns from unstructured content, which captures meaning, intent and tone**
C. 50%; the split determines model size
D. 80–90%; but it must all be converted to structured fields before use

> **B.** **A** inverts both the figure and the principle. **C** invents a relationship that doesn't exist. **D** has the right figure but the wrong conclusion — and it's the trap, because forcing unstructured content into predefined fields **loses nuance, context and language patterns** that generative models depend on. **B** is correct: structured data captures *facts*, unstructured captures *meaning, intent and tone*.

**Q9.** A fraud team has structured transaction records and unstructured customer emails. Which data strategy is best?

A. Use only the structured transaction data — it is easier to process
B. Convert all unstructured data into structured fields
C. **Use both, because generative models learn from diverse inputs**
D. Use only multimodal image data

> **C.** *(Adapted from a course example.)* **D** is irrelevant — fraud analysis here involves text and numbers, not images. **B** loses the meaning held in free text. **A** handles transaction history but not the looser emails, discarding context about intent, behaviour and anomalies. **C** gives the full picture: structured records reveal numerical patterns, unstructured emails reveal sentiment, intent and behavioural cues.

**Q10.** Which Google Cloud service is designed for real-time ingestion of event streams such as clickstream data, application logs and IoT sensor readings?

A. Cloud Storage
B. BigQuery
C. **Pub/Sub**
D. Dataproc

> **C.** **D** is Spark/Hadoop processing for large-scale data prep, not ingestion. **A** is the landing zone for **bulk files** and unstructured content. **B** ingests structured data for analytics, via batch loads or streaming inserts. **C** is the purpose-built real-time event ingestion service, capturing live streams and delivering them instantly to downstream processors.

**Q11.** In the ML lifecycle, which service detects that a deployed model's live predictions are degrading and signals that retraining is needed?

A. Vertex AI Pipelines
B. **Vertex AI Model Monitoring**
C. Dataplex
D. Cloud DLP

> **B.** **D** detects and masks sensitive data. **C** catalogues metadata and traces lineage. **A** is the close distractor — pipelines *automate the retraining workflow* once you know retraining is needed, but they don't detect the problem. **B** continuously checks live predictions for **drift** and alerts when performance degrades. The pairing to remember: **Model Monitoring detects, Pipelines respond.**

**Q12.** A team needs to clean and transform a messy dataset but has no engineers who write code. Which service?

A. Dataflow
B. Dataproc
C. **Dataprep**
D. Pub/Sub

> **C.** **D** is ingestion, not transformation. **A** is managed streaming/batch processing — powerful, but you build pipelines. **B** requires Spark/Hadoop familiarity. **C** is the **visual, no-code** environment that automatically spots missing values, inconsistent entries and outliers. Note the exam's recurring pattern: when a stem stresses **lack of technical expertise**, the answer is the no-code option (here Dataprep; for model training, AutoML).

**Q13.** Which describes a diffusion model?

A. A model that processes tokens in parallel using self-attention
B. **A model that starts from noise and refines it step by step into a coherent image, audio clip or video**
C. A model that distributes inference across multiple GPUs
D. A model that retrieves documents before generating

> **B.** **D** is RAG. **C** describes model parallelism, an infrastructure technique. **A** describes the **transformer**, which is a different architecture. **B** is the diffusion process — and it's the architecture behind image generation, which is why **Imagen** pairs a language model (to encode prompt meaning) with a diffusion model (to generate the image).

**Q14.** An organisation is choosing a foundation model. Which set of factors matches the exam guide's model-selection criteria?

A. Programming language, IDE, repository host, CI tool
B. **Modality, context window capacity, performance, and availability (open vs proprietary)**
C. Data centre location only
D. Number of employees and annual revenue

> **B.** **A** lists developer tooling irrelevant to model choice. **C** is one narrow factor (residency) presented as the whole decision. **D** is unrelated. **B** is the criteria set: what **modalities** the model handles, how much **context** it can hold, its **performance**, and whether it's **open or proprietary** — plus, from the Pluralsight framing, size/scale, cost efficiency (inference is the biggest production expense), customisability, and ecosystem support.

**Q15.** Order the five layers of the gen AI technology stack from bottom to top.

A. Models, Infrastructure, Agents, Platforms, Applications
B. **Infrastructure, Models, Platforms, Agents, Applications**
C. Infrastructure, Platforms, Models, Applications, Agents
D. Applications, Agents, Platforms, Models, Infrastructure

> **B.** **D** is the correct order reversed. **A** and **C** transpose layers. **B** is right, and the flow sentence is worth memorising: *infrastructure runs the models → models power the platforms → platforms enable the agents → agents drive the applications → applications create business value.*

**Q16.** What distinguishes a TPU from a GPU?

A. TPUs are general-purpose processors; GPUs are AI-specific
B. **TPUs are custom Google-designed chips built specifically for the matrix operations behind deep learning**
C. TPUs are used only for inference, never training
D. TPUs are open-source hardware designs

> **B.** **A** inverts them. **C** is false — TPUs serve both training and inference. **D** is invented. **B** is correct, and note *why it matters strategically*: TPUs offer better price-performance than generic GPUs for training and prediction, which is one of the four pillars of Google Cloud's differentiation.

**Q17.** Which is an example of **reinforcement** learning?

A. Labelling 10,000 X-rays as healthy or pneumonia, then classifying new scans
B. Grouping customers into segments without predefined categories
C. **A system that takes actions, receives rewards or penalties, and adjusts its strategy over many cycles**
D. Retrieving documents to ground a model's answer

> **C.** **D** is RAG. **A** is textbook supervised learning. **B** is unsupervised. **C** is the reinforcement loop in order: *agent acts in an environment → model evaluates the result → feedback (reward or penalty) is sent → the agent's strategy is refined → repeat.*

**Q18.** A company's CRM and billing system disagree about whether an account is active, so an AI assistant gives a customer incorrect operational advice. Which data problem is this?

A. Semantic inconsistency
B. Time lag
C. **Source-of-truth misalignment**
D. Conflicting values

> **C.** All four are real inconsistency types, which makes this hard. **A** would be terms like "inactive", "closed" and "dormant" used interchangeably but meaning different things. **B** would be stale data lagging reality. **D** would be the same field holding incompatible entries *within* a dataset. **C** is specifically **two authoritative systems disagreeing** — which is what the stem describes, and its named consequence is exactly this: models and the agents relying on them deliver incorrect guidance.

---

## BLOCK B — Google Cloud's gen AI offerings (Q19–39, ~35%)

*The biggest domain. If you're short on time, drill this block twice.*

**Q19.** A team wants to evaluate and deploy a Meta open-source model alongside Gemini within one managed environment. Which supports this?

A. **Vertex AI Model Garden**
B. Vertex AI Feature Store
C. Cloud Run
D. Dataplex

> **A.** **B** centralises data features. **D** is cataloguing and lineage. **C** could host something but doesn't address discovery or unified management. **A** is the centralised catalogue spanning first-party (Gemini, Imagen, Veo), partner models (Anthropic, Meta, Mistral, Hugging Face), fine-tunable open models (Gemma, Llama), and task-specific solutions. **Model Garden is the single most-tested product in this domain.**

**Q20.** During a live support call, a representative needs suggested responses and the relevant warranty clause surfaced immediately. Which product?

A. Conversational Insights
B. **Agent Assist**
C. Dialogflow CX
D. Vertex AI Pipelines

> **B.** *(Adapted from a course example.)* **D** orchestrates ML workflows. **C** builds the *virtual* agent that handles conversations before escalation — but a human is already on this call. **A** is the deliberate trap: Conversational Insights analyses **completed** interactions for trends and sentiment. The stem says *during a live call*. **B** is purpose-built for real-time assistance to human reps.
>
> **Memorise: Agent Assist = live. Conversational Insights = after.**

**Q21.** Which three products make up Google Cloud's Customer Engagement Suite?

A. Vertex AI Search, Agent Builder, Model Garden
B. **Conversational Agents, Agent Assist, Conversational Insights**
C. Gemini, Imagen, Veo
D. Dialogflow CX, NotebookLM, Gems

> **B.** **C** lists foundation models. **A** lists Vertex AI components. **D** mixes a conversational agent tool with two personal-productivity features. **B** is the suite: the **virtual agent** that handles the customer, the **live assistance** for the human rep, and the **post-interaction analytics**. This maps exactly onto the four-stage contact-centre workflow.

**Q22.** An HR manager wants a reusable version of Gemini pre-programmed to act as a technical recruiter, always applying the same screening criteria to every résumé. Which feature?

A. Gemini Advanced Search
B. **Gems**
C. NotebookLM
D. Gemini Extensions

> **B.** *(From a course example.)* **C** is for grounded analysis of *uploaded source documents*, not creating a persistent persona. **A** enhances retrieval, not reusable behaviour. **D** connects Gemini to external tools and services but doesn't define a saved role, tone or instruction set. **B** is the definition of a Gem: a customisable version of Gemini with **saved instructions and role-based guidance**, applied consistently every time.

**Q23.** A policy team wants to upload 40 internal PDFs and generate an executive brief, a mind map and a quiz from *only* those documents. Which product?

A. Vertex AI Search
B. Gemini app
C. **NotebookLM**
D. Google AI Studio

> **C.** **D** is a prototyping environment for prompts. **B** is a general assistant drawing on broad public knowledge. **A** is the strongest distractor — it grounds answers in enterprise content, but it's a *search and Q&A* service, not a workspace that produces structured deliverables. **C** is grounded in the sources *you* upload, and its **Studio panel** produces exactly these outputs: audio overviews, video summaries, mind maps, reports, flashcards, quizzes, slide decks, infographics, data tables.

**Q24.** Which statement about enterprise Gemini deployments is correct?

A. All interactions improve Google's public models
B. **Customer data is not used for model training unless the organisation explicitly opts in**
C. Enterprise deployments cannot connect to private company content
D. Each user manages their own audit trail

> **B.** **C** is backwards — connecting to private content is a core enterprise capability. **D** inverts it: enterprise brings **centralised** administration with audit trails, governance and retention rules. **A** describes personal/individual usage. **B** is the enterprise guarantee, and it's a likely question because it's a primary buying objection.

**Q25.** A cloud operations team wants AI help diagnosing a complex system incident, identifying root causes and receiving remediation suggestions. Which product?

A. Gemini Code Assist
B. **Gemini Cloud Assist**
C. Gemini in BigQuery
D. Security Command Center

> **B.** **C** is for natural-language data exploration and SQL generation. **D** surfaces security alerts and threat indicators — related to incidents but security-specific, and not an AI assistant for general cloud operations. **A** is the near-miss: Code Assist helps **developers** write and refactor code. **B** is for **cloud professionals managing environments**: lifecycle management, diagnosing system issues and root causes, security guidance, cost and performance optimisation.

**Q26.** Which pairing correctly matches purpose to studio?

A. Google AI Studio for enterprise governance; Vertex AI Studio for quick prototyping
B. **Google AI Studio for rapid experimentation; Vertex AI Studio for enterprise evaluation, governance and deployment**
C. Both are identical, differing only in price
D. Google AI Studio for images; Vertex AI Studio for text

> **B.** **D** invents a modality split. **C** is false. **A** has them the right way round — reversed. **B** is correct: **Google AI Studio** = speed and creativity at the experimentation stage, minimal setup, individual developers and small teams. **Vertex AI Studio** = structured evaluation, access controls, deployment workflows, production use where reliability and compliance matter.

**Q27.** An organisation wants to ground an internal assistant in policy documents that change monthly, without building indexing, embedding and ranking infrastructure. Which is most appropriate?

A. Fine-tune the model monthly
B. **Vertex AI Search**
C. AutoML
D. BigQuery ML

> **B.** **C** trains predictive models from tabular data. **D** runs ML inside the data warehouse on structured data. **A** is the RAG-vs-fine-tuning trap: retraining monthly is expensive, slow and loses source traceability. **B** delivers **RAG out of the box** — content ingestion and indexing, natural-language retrieval, relevance controls — with answers grounded in current documents.

**Q28.** A retailer has strong domain knowledge and clean sales data but no ML engineers, and wants a custom demand-forecasting model. Which capability?

A. Vertex AI Pipelines for manual orchestration of training scripts
B. **AutoML**
C. Vertex AI Studio for manual prompt engineering
D. Model Garden to download a base model for local manual fine-tuning

> **B.** *(From a course example — note the giveaway.)* **A** assumes the team writes and manages training code, which is the exact gap. **C** works with foundation models through prompts, not structured prediction from tabular data. **D** requires significant ML knowledge. **B** is designed for teams with strong data and domain knowledge but **limited ML coding experience**.
>
> **Technique note: the word "manual" appears in all three wrong answers and not in the right one.** Scan for that clustering.

**Q29.** Which Google Cloud API converts spoken audio into written text?

A. Text-to-Speech API
B. **Speech-to-Text API**
C. Natural Language API
D. Translation API

> **B.** Read the direction of travel carefully — this is a pure recall question and the exam includes several. **A** is the reverse (text → audio). **C** analyses text for entities, sentiment and syntax. **D** converts between languages. **B** is audio → text.

**Q30.** A logistics firm needs to extract structured fields from scanned invoices and contracts. Which is purpose-built?

A. Vision API
B. **Document AI**
C. Video Intelligence API
D. Natural Language API

> **B.** **C** analyses video. **D** analyses text you already have, but doesn't extract it from a scanned page. **A** is the close distractor — Vision API does general image analysis including some text detection, but it isn't built for structured document understanding. **B** is purpose-built to extract structured information from invoices, contracts and forms.

**Q31.** Which best describes Google Agentspace (now **Gemini Enterprise**)?

A. A no-code model training service
B. **Enterprise search across company applications combined with AI agents that can research, plan and act, under enterprise governance**
C. A data catalogue with lineage tracking
D. A hardware accelerator family

> **B.** **D** is TPUs/GPUs. **C** is Dataplex. **A** is AutoML. **B** is the product: Google-quality enterprise search plus agents that act across business apps, with governance.
>
> ⚠️ **Naming:** Agentspace was renamed **Gemini Enterprise** in October 2025. Older exam prep says Agentspace; newer says Gemini Enterprise. **Recognise both.**

**Q32.** Which four milestones correctly reflect Google's AI history?

A. Transformer paper 2023, Gemini 2017, TensorFlow 2020, DeepMind 2019
B. **DeepMind acquired 2014, TensorFlow open-sourced 2015, Transformer paper 2017, Gemini 2023**
C. Gemini 2015, TensorFlow 2017, DeepMind 2021, Transformer 2023
D. TensorFlow 2001, Transformer 2010, DeepMind 2015, Gemini 2020

> **B.** Only **B** has a coherent sequence. The one that matters most is **2017 — the Transformer paper**, which introduced self-attention and is the architectural foundation for Gemini, GPT-4 and Claude. Its business significance: by making training **parallelisable**, it turned gen AI at scale from a research curiosity into an economic possibility.

**Q33.** What is the primary function of Vertex AI Pipelines?

A. Detecting drift in production models
B. Discovering and comparing available models
C. **Automating the workflow that connects data preparation, training, evaluation, registration and deployment into one repeatable process**
D. Storing and serving consistent data features

> **C.** **A** is Model Monitoring. **B** is Model Garden. **D** is Feature Store. **C** is Pipelines — and note the framing from the course: pipelines are **not a stage** in the lifecycle, they **connect** the stages, giving consistency, traceability and operational discipline.

**Q34.** A recommendation engine and a support assistant must both use the same current customer purchase history and product usage data, without each maintaining its own copy. Which service?

A. Cloud Storage
B. BigQuery
C. **Vertex AI Feature Store**
D. Dataplex

> **C.** **A** is object storage. **B** is the data warehouse — it could hold the data, but doesn't solve consistent *feature serving* to multiple models. **D** catalogues and traces data assets but doesn't serve features. **C** is the "well-stocked pantry": centralising features so different models and applications work from the same consistent, current inputs.

**Q35.** Which layer of Google's gen-AI-optimised infrastructure coordinates thousands of compute resources for distributed training and large-scale inference?

A. Global data centres
B. Custom TPU and GPU accelerators
C. **Hypercomputer orchestration**
D. AI platforms and models

> **C.** The four layers bottom-to-top are: **data centres → accelerators → hypercomputer orchestration → AI platforms and models.** **A** is the physical backbone. **B** provides the compute. **D** sits on top. **C** is specifically the coordination layer, abstracting the complexity of distributed workloads from the customer.

**Q36.** Which is a genuine differentiator of Google Cloud for gen AI?

A. Only Google-authored models may run on the platform
B. **Proprietary TPUs, direct access to Google DeepMind research, a global private fibre network, and an integrated AI platform**
C. Open-source models must be manually ported to TPU hardware
D. Gen AI services are available exclusively in a single region

> **B.** *(Adapted from a course example.)* **A** invents a "locked ecosystem" policy that contradicts how Model Garden actually works. **C** is the manual/brute-force distractor — Vertex AI abstracts infrastructure so you don't hand-port code. **D** is false and would be a weakness, not a differentiator. **B** is the four-pillar answer, summarised as **deep vertical integration — Google owns and operates the full stack.**

**Q37.** Under which circumstances would you choose Cloud Run over GKE for serving a model?

A. When you need to train a model at scale
B. **When you want serverless deployment of a lightweight model service that auto-scales on demand**
C. When you need a catalogue of foundation models
D. When you need to detect data drift

> **B.** **A** is Vertex AI training. **C** is Model Garden. **D** is Model Monitoring. **B** is Cloud Run's role in the lifecycle: serverless, lightweight, automatically scaling — for cases like form processing, text classification or batch scoring. **GKE** is the alternative for scalable **container-based** deployment serving complex models at high inference volume.

**Q38.** Which describes how Gemini appears inside Google Cloud services?

A. Only as a standalone chat interface
B. **Embedded in BigQuery, Looker, SecOps and Firebase, bringing gen AI into the tools teams already use**
C. Only via the Gemini app
D. Only through Vertex AI Studio

> **B.** **A**, **C** and **D** all describe Gemini as confined to one surface, contradicting Google's stated "AI everywhere" strategy. **B** is correct — and know the specific value in each: **BigQuery** (natural-language exploration, SQL generation, insight summaries), **Looker** (report creation, trend explanation, narrative insights), **SecOps** (threat summarisation, incident investigation, response prioritisation), **Firebase** (code generation, troubleshooting).

**Q39.** Which sequence correctly describes the adoption spectrum from least to most customisable?

A. Vertex AI custom training → Vertex AI Search → Translation API
B. **Pre-built APIs (Text-to-Speech, Translation) → configurable (Vertex AI Search, Vertex AI Studio) → custom (Vertex AI model development, AI agents)**
C. Vertex AI Studio → Translation API → Model Garden
D. AutoML → Document AI → Gemini app

> **B.** **A** is the correct spectrum reversed. **C** and **D** mix categories without a coherent progression. **B** is the continuum: ready-to-use APIs with minimal configuration → services you tailor to your own data → full model development, fine-tuning and agent orchestration. The matching persona ladder is **business users (no code) → developers (API level) → data scientists (custom model layer).**

---

## BLOCK C — Techniques to improve model output (Q40–51, ~20%)

**Q40.** A clinic's assistant answers questions about opening hours and insurance policies that change monthly. Why recommend RAG over fine-tuning?

A. Fine-tuning is more cost-effective for frequently changing data
B. RAG is better for teaching a specific brand tone
C. **RAG allows near real-time updates of facts without the cost of retraining**
D. Fine-tuning provides better source attribution than RAG

> **C.** *(From a course example.)* **D** flips reality — RAG enables citations because it pulls from identifiable documents at runtime; fine-tuning blends knowledge into weights and loses traceability. **A** fails because retraining on every change is expensive and inefficient. **B** swaps the use cases: tone is fine-tuning's strength. **C** is the fit.
>
> **The one-liner: changing facts → RAG. Changing behaviour → fine-tuning.**

**Q41.** A support bot is correctly grounded in the product manual but answers complaints in flowery, dismissive-sounding prose. What should a leader explain?

A. Grounding is failing; the manual needs more data
B. Switch to zero-shot prompting to fix tone
C. The knowledge cutoff is causing it
D. **Grounding controls factual accuracy, not creative tone or style**

> **D.** *(From a course example.)* **B** confuses mechanisms — zero-shot concerns example count, not style. **C** is irrelevant: cutoff affects currency, not register. **A** contradicts the stem, which says grounding works. **D** is the principle, and it is one of the most commonly tested ideas in this domain: **grounding controls the information; prompts and parameters control the behaviour.**

**Q42.** A tax team uses gen AI for multi-step calculations and logical deductions. Results are frequently wrong. Which technique?

A. One-shot prompting
B. **Chain-of-thought prompting**
C. Raising temperature to 1.0
D. Removing constraints from the prompt

> **B.** *(From a course example.)* **D** would worsen it — constraints guide and focus reasoning. **C** increases randomness, the opposite of what logic needs. **A** helps with format and pattern, but the deficit is **structured reasoning**, not examples. **B** makes the model work through intermediate steps explicitly before concluding.

**Q43.** Which correctly distinguishes chain-of-thought from prompt chaining?

A. They are the same technique under different names
B. **Chain-of-thought shows intermediate reasoning within a single prompt and response; prompt chaining breaks a task into a sequence of separate connected steps**
C. Chain-of-thought requires external data retrieval; prompt chaining does not
D. Prompt chaining only works with images

> **B.** **D** is invented. **A** is false. **C** describes **ReAct**, not chain-of-thought. **B** is the distinction — and complete the trio: **ReAct** = reasoning *plus* going out and retrieving additional information, for research tasks, tool or database queries and multi-source investigations.

**Q44.** A team wants twenty varied slogan options for a brainstorm. Which parameter configuration?

A. Low temperature, low top-K, short token limit
B. **Higher temperature, broader top-P/top-K, moderate token limit**
C. Temperature 0 with a fixed seed
D. Low temperature, maximum token limit

> **B.** **C** pins the model to near-identical outputs — a fixed seed exists precisely to make results **reproducible**, which defeats the purpose. **D** produces one long, conservative answer. **A** is the configuration for factual, consistent tasks. **B** widens the token pool and increases variation, which is what ideation needs; slogans don't require many tokens.

**Q45.** What does top-P (nucleus sampling) do?

A. Limits the model to a fixed number of most likely tokens
B. **Selects from the smallest set of tokens whose cumulative probability reaches a threshold**
C. Sets the maximum response length
D. Controls how many documents are retrieved

> **B.** **C** is the output token limit. **D** is top-K retrieval in RAG — a different "top-K", and a genuine source of confusion worth noting. **A** is **top-K sampling**, the fixed-count sibling. **B** is top-P: dynamic, e.g. 0.9 means the smallest set of words together accounting for 90% of likelihood.

**Q46.** According to the risk ladder, which control is appropriate for the *most* critical decisions?

A. Prompt engineering
B. Grounding with RAG
C. Fine-tuning
D. **Human-in-the-loop review**

> **D.** The ladder rises with risk: **A** for low risk (drafting, summarising), **B** for moderate risk (support, internal knowledge — accuracy matters), **C** for higher risk (consistency and domain-specific behaviour critical), **D** for the most critical, where human review validates outputs before use to ensure accuracy, compliance and accountability. Controls are cumulative in practice; the question asks what the top tier requires.

**Q47.** Which is the best description of **metaprompting**?

A. Chaining several prompts together in sequence
B. **Using the model itself to generate or refine a prompt for a task**
C. Embedding metadata in retrieved documents
D. Assigning the model a role or persona

> **B.** **D** is role prompting. **A** is prompt chaining. **C** is metadata enrichment in a RAG pipeline. **B** is metaprompting — asking the LLM to write or improve your prompt. It's on the official exam guide's prompting list but absent from your Pluralsight courses, so it's a genuine blind spot.

**Q48.** A model that performed well six months ago now gives less relevant answers, though it hasn't been changed. What is happening and what's the response?

A. Prompt injection; add input filtering
B. **Drift; monitor KPIs against baselines and retrain or refresh the knowledge source**
C. Hallucination; lower the temperature
D. Bias; rebalance the training set

> **B.** **A** requires a malicious input. **C** misdiagnoses — hallucination is fabrication, and temperature governs variability, not relevance decay. **D** concerns systematically uneven outcomes across groups, not gradual degradation. **B** is drift: real-world inputs evolve — user behaviour, products, business processes — so what the model encounters no longer matches its training. Track accuracy, hallucination frequency and user feedback against baselines. **Version control** sits alongside, so you can revert quickly.

**Q49.** Which prompting technique provides several labelled examples so the model can learn category distinctions and edge cases?

A. Zero-shot
B. One-shot
C. **Few-shot**
D. Chain-of-thought

> **C.** **A** gives instructions only. **B** gives a single example — good for enforcing a **format**. **D** elicits visible reasoning, not category learning. **C** provides multiple examples, which is what's needed for complex or ambiguous classification where the model must distinguish between categories accurately.

**Q50.** Which four components make a prompt "strategic"?

A. Temperature, top-P, top-K, token limit
B. **Instruction, context, structure, constraints**
C. Retrieval, augmentation, generation, evaluation
D. Ingestion, preparation, training, deployment

> **B.** **A** lists *parameters*, which are model settings rather than prompt components. **C** is the RAG pipeline. **D** is the ML lifecycle. **B** is the prompt anatomy: **instruction** (what to do), **context** (background, role, audience), **structure** (how the response is organised), **constraints** (length, tone, exclusions).

**Q51.** Which safety categories can be configured in Vertex AI's safety filters?

A. Accuracy, latency, cost, availability
B. **Hate speech, dangerous content, sexually explicit content, harassment**
C. Bias, drift, hallucination, injection
D. Public, internal, customer, regulated

> **B.** **D** is data classification. **C** lists risks, not filter categories. **A** lists performance metrics. **B** is the four configurable categories, each settable to **Off / Block few / Block some / Block most**.

---

## BLOCK D — Business strategies (Q52–60, ~15%)

**Q52.** A firm needs a gen AI solution quickly, with a strict budget and limited AI expertise. Which approach?

A. Build a fully custom foundation model from scratch
B. Train a proprietary model using all available enterprise data
C. **Use a pre-built gen AI solution with minimal customisation**
D. Use only open-source models hosted on-premises

> **C.** *(From a course example.)* **B** is worst — proprietary training brings cost, complexity and governance burden, and *"all available enterprise data"* adds needless privacy and security risk. **A** demands time, budget, infrastructure and expertise they lack. **D** looks cheap because open source is free, but **on-premises hosting** raises operational overhead precisely where resources are thinnest. **C** gives fast deployment, lower upfront cost and managed capabilities.

**Q53.** Under the shared responsibility model, which remains **primarily** the customer's responsibility?

A. Securing Google's physical data centres
B. **Defining user access controls and governance policies**
C. Managing hardware-level encryption chips
D. Configuring security settings and access permissions correctly

> **B.** *(From a course example.)* **A** and **C** are Google's. The real difficulty is **D** vs **B**: both mention access, but **configuration is a *shared* responsibility**, so it isn't *primarily* the customer's. **B** is — determining who can access systems and data, and establishing the governance policies for secure, compliant use.

**Q54.** A hospital wants to use patient records to improve an assistant while reducing privacy risk. Which approach?

A. Role-based access controls without reducing identifiable information
B. Remove logging and monitoring so sensitive data isn't captured
C. Encrypt the data while continuing to use directly identifiable information
D. **Anonymisation or pseudonymisation before processing**

> **D.** *(From a course example.)* **C** protects data at rest and in transit but leaves identifiers exposed *inside the processing workflow*. **A** limits who can view data but doesn't reduce the risk of processing identifiable information. **B** is superficially attractive and actively harmful — removing logging destroys visibility into security events, making misuse harder to detect and compliance harder to prove. **D** masks or transforms identifiers *before* data reaches the system.

**Q55.** Which correctly distinguishes anonymisation from pseudonymisation?

A. Anonymisation is reversible; pseudonymisation is not
B. **Anonymisation removes identifiers and is intentionally hard to reverse; pseudonymisation substitutes tokenised identifiers that can be re-linked with authorised access**
C. They are the same technique
D. Pseudonymisation is only used for public research datasets

> **B.** **C** is false. **A** reverses them. **D** inverts the typical use: *anonymisation* suits public datasets, analytics and research where identity needn't be preserved; **pseudonymisation** suits **enterprise systems** needing privacy *and* the ability to reconnect records when authorised. **B** is correct: anonymisation is stronger for pure privacy, pseudonymisation offers more operational flexibility.

**Q56.** Which pairing matches a SAIF pillar to its Google Cloud tooling?

A. Protect data → IAM and VPC controls
B. Control access → Cloud DLP and Cloud KMS
C. **Monitor and respond → Cloud Monitoring and Security Command Center**
D. Secure models → Dataplex and Dataprep

> **C.** The four pillars map as: **protect data → Cloud DLP + Cloud KMS**; **secure models → Vertex AI controls + model policies**; **control access → IAM + VPC controls**; **monitor and respond → Cloud Monitoring + Security Command Center**. **A** and **B** swap the first and third pillars' tooling. **D** names data-prep and cataloguing services unrelated to model security.

**Q57.** Which correctly maps a security risk to its primary attack surface?

A. Prompt injection → data sources
B. Data leakage → user input
C. **Model misuse → output**
D. Prompt injection → output

> **C.** The fixed mapping: **prompt injection → user input**, **data leakage → data sources**, **model misuse → output**. **A**, **B** and **D** cross-wire it. Know the business consequences too: injection → loss of trust and legal exposure; leakage → incorrect or harmful outputs; misuse → brand damage and compliance issues.

**Q58.** A pilot showed strong technical results, but six months on adoption is minimal: staff don't trust the outputs and workflows were never changed. What does this illustrate?

A. Insufficient model capability
B. Inadequate infrastructure scaling
C. **Organisational readiness gaps in people and process**
D. A data quality problem

> **C.** **A** and **B** point at technology, but the stem says technical results were strong. **D** would present as poor output quality; the problem described is trust and workflow. **C** matches the course's explicit teaching: readiness rests on **people** (skills, trust, adoption), **process** (workflows, governance) and **technology** — and **technology is only one part; people and processes ultimately determine success.**

**Q59.** An organisation's AI adoption is entirely driven by individual teams choosing their own tools, with no central platform or policy. What is the main risk, and what is the recommended correction?

A. No risk; bottom-up adoption is always preferable
B. **Fragmentation and shadow AI with no governance; combine bottom-up enthusiasm with top-down guardrails and a shared platform**
C. Excessive centralisation; devolve further to individuals
D. The models will be too small; mandate frontier models everywhere

> **B.** **A** overstates a real benefit — bottom-up gives excellent workflow fit and enthusiasm, but alone it produces inconsistency. **C** misdiagnoses the direction. **D** is unrelated to the governance problem. **B** is the recommended balance, and it's the same logic as the **hybrid** organisational model: *governance centralized, flexibility distributed* — because **teams that route around the platform are invisible to it.**

**Q60.** A use case has high potential business impact but requires substantial customisation and specialist development. Where does it sit on the decision matrix?

A. Low impact, low complexity — don't build
B. **High impact, high complexity — custom solution justified**
C. High impact, low complexity — use pre-built
D. Low impact, high complexity — reconsider

> **B.** **A** and **D** contradict the stated high impact. **C** would apply if the need were simple, but the stem specifies substantial customisation. **B** is the quadrant where the extra investment in time and resources can deliver meaningful **differentiation and competitive advantage**.

---

## Answer key — for fast re-drilling

| | | | | | | | | | |
|---|---|---|---|---|---|---|---|---|---|
| 1 **B** | 2 **B** | 3 **C** | 4 **B** | 5 **C** | 6 **B** | 7 **B** | 8 **B** | 9 **C** | 10 **C** |
| 11 **B** | 12 **C** | 13 **B** | 14 **B** | 15 **B** | 16 **B** | 17 **C** | 18 **C** | 19 **A** | 20 **B** |
| 21 **B** | 22 **B** | 23 **C** | 24 **B** | 25 **B** | 26 **B** | 27 **B** | 28 **B** | 29 **B** | 30 **B** |
| 31 **B** | 32 **B** | 33 **C** | 34 **C** | 35 **C** | 36 **B** | 37 **B** | 38 **B** | 39 **B** | 40 **C** |
| 41 **D** | 42 **B** | 43 **B** | 44 **B** | 45 **B** | 46 **D** | 47 **B** | 48 **B** | 49 **C** | 50 **B** |
| 51 **B** | 52 **C** | 53 **B** | 54 **D** | 55 **B** | 56 **C** | 57 **C** | 58 **C** | 59 **B** | 60 **B** |

> **Note on the answer distribution:** B is over-represented here because I wrote the correct answer into a consistent slot while drafting. **The real exam randomises positions.** Do not let "it's usually B" become a habit — on exam day, reason from the content only.

---

## How to score yourself

| Score | Interpretation |
|---|---|
| **< 60%** | Not ready. Re-read the main study guide, especially any domain you failed badly, before re-testing |
| **60–69%** | Borderline. Identify which *domain* you're losing marks in and drill only that |
| **70–74%** | Book the exam, keep studying |
| **75%+** | Ready. Take the Pluralsight practice exam to confirm, then sit it |

**Google does not publish the passing score.** The widely-reported working assumption is around 70%, so **target 75%+** on practice to leave margin.

**Score by domain, not overall.** A 72% overall hiding a 50% on Domain 2 means you're likely to fail, because Domain 2 is 35% of the real exam. Write down your per-domain percentages and attack the weakest one.

---

## Sources

- [Generative AI Leader — Google Cloud](https://cloud.google.com/learn/certification/generative-ai-leader) — official certification page: logistics, domains, sample questions link
- [Official exam guide (PDF)](https://services.google.com/fh/files/misc/generative_ai_leader_exam_guide_english.pdf)
- [Official study guide (PDF)](https://services.google.com/fh/files/misc/generative_ai_leader_study_guide_english.pdf)
- [Official sample questions](https://forms.gle/soztS7Q74AXBncATA)
- [Skills Boost learning path 1951](https://www.cloudskillsboost.google/paths/1951)
- [Gemini Enterprise Agent Platform (formerly Vertex AI)](https://cloud.google.com/vertex-ai) — confirms the rename
- [Cloudfluently — Gen AI Leader exam guide 2026](https://cloudfluently.com/blog/google-cloud-generative-ai-leader-exam-guide-2026) — detailed topic breakdown used to identify the Pluralsight gaps
- [Tutorials Dojo — Gen AI Leader study guide](https://tutorialsdojo.com/google-cloud-certified-generative-ai-leader-exam-study-guide/)
- [Atlan — What is Gemini Enterprise (formerly Agentspace)](https://atlan.com/know/ai-agent/ai-agent-applications/google-agentspace/) — rename timeline

*Built 2026-09-11. Questions are original, written in the style of the official example questions; they are not real exam items. Verify product naming against the official exam guide before sitting — Google's AI product names are changing rapidly.*
