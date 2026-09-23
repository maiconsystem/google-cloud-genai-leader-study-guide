# Google Cloud Generative AI Leader — MAIN STUDY GUIDE

**This is your primary study material for the exam.** Built from the four Pluralsight "(Generative AI Leader)" course transcripts in this folder, reorganised by exam domain, with the low-yield material stripped out and practice questions added throughout.

**Read order:**
1. **This file** — the main guide. Sections 1–7.
2. [02-quick-recall-sheet.md](02-quick-recall-sheet.md) — the shorter recall sheet. Use it for the final 48 hours.
3. [03-product-table.md](03-product-table.md) — the product memorisation table. The highest-yield rote work for Domain 2.
4. [04-exam-morning-sheet.md](04-exam-morning-sheet.md) — one page to read on the day.

> **About the practice questions.** They are **original**, written to match the style, length, and distractor patterns of the 14 official example questions in the courses' own "Exam Question Review" modules. They are **not** real exam questions — real items are under Google's exam agreement and nobody may publish them. Question *style* is what you can legitimately practise, and style is most of the battle on this exam. Where a question is adapted from a course example, it says so.
>
> **Accuracy note.** Everything not marked is from the transcripts. Items marked **[+]** are added from outside knowledge to fill a gap the courses left. Google's product catalogue changes frequently — verify product names against the current official exam guide before you sit.

---

## SECTION 1 — The exam, and how to beat it

### What the exam is testing

Google's own description of the certified individual:

> *"A visionary professional with comprehensive knowledge of how gen AI can transform and be used within a business… business-level knowledge of Google Cloud's gen AI products and services… They can engage in meaningful conversations with both technical and non-technical teams… **Their expertise is in strategic leadership and influence, not technical implementation**, though they have a conceptual understanding of gen AI concepts and technology."*

**Read that last sentence twice.** It tells you what the wrong answers look like. When two options are both defensible, the exam nearly always wants the one a *leader* would choose — the efficient, governed, business-aligned option — not the technically maximal one.

### The four domains

| Domain | Approx. weight | Notes |
|---|---|---|
| 1. Fundamentals of gen AI | ~30% | Concepts and vocabulary. Most candidates score highest here |
| **2. Google Cloud's gen AI offerings** | **~35%** | **The largest domain, and mostly product recall. Prioritise it.** |
| 3. Techniques to improve model output | ~20% | RAG, fine-tuning, prompting, parameters |
| 4. Business strategies for a successful gen AI solution | ~15% | Smallest domain, least intuitive questions |

*Weights are approximate — confirm against the current official exam guide.*

### Exam technique — this is worth as much as the content

The course instructor demonstrates one method across all 14 example questions: **eliminate wrong answers first, then justify the survivor.** Do not read the four options looking for the right one. Read them looking for reasons to kill three.

**The six distractor patterns that appear again and again:**

| Pattern | What it looks like | Example from the courses |
|---|---|---|
| **1. Reality flip** | The option states the *opposite* of the truth, confidently | *"Fine-tuning provides better source attribution than RAG"* — backwards; RAG is what enables citations |
| **2. Use-case swap** | A real technique attached to the wrong job | *"RAG is better for teaching a specific brand tone"* — no, that's fine-tuning |
| **3. Too narrow** | True, but doesn't answer the whole question | *"Vertex AI supports text-based models for external developers"* — true but ignores the open-source-plus-Gemini requirement |
| **4. Invented policy** | A plausible-sounding rule that doesn't exist | *"Google's Locked Ecosystem policy"* — no such thing |
| **5. Manual / brute-force** | Technically possible but inefficient; the exam rewards the managed path | *"Manually port open-source code to run on proprietary TPU hardware"* |
| **6. Right layer, wrong moment** | A real product used at the wrong stage of the lifecycle | *Conversational Insights* (post-call analysis) offered when the question needs **live** help → *Agent Assist* |

**Three tells to look for in the question stem:**

1. **Keyword giveaways.** In one course example the word *"manual"* appeared in all three wrong answers and not in the right one. Scan for a word that clusters in the distractors.
2. **Constraint words.** *"Quickly", "limited expertise", "strict budget", "changes monthly", "real-time", "during a live call"* — each one eliminates half the options by itself.
3. **What the question says is already working.** If the stem says *"they already selected a foundation model and built the agent logic"*, then the model layer and agent layer are **not** the answer. The exam frequently tells you where the problem *isn't*.

**Two further rules from the instructor:**
- *"Google Cloud exams often look for the most efficient answer."* If option X would work but takes six steps and option Y is the managed service built for exactly this, the answer is Y.
- Watch for *"which **strategy**"* in the stem. That signals the answer is a **combination** — matching each task to the right tool — not a single product for everything.

---

## SECTION 2 — Domain 1: Fundamentals of Gen AI (~30%)

### 2.1 The hierarchy — know it cold

**AI ⊃ ML ⊃ Gen AI.** Artificial intelligence is the umbrella: a computer technology performing tasks that normally require human intelligence — **learn, solve problems, make decisions.** Machine learning is a *subfield* of AI. Other subfields sit alongside ML: **natural language processing** (understand/interpret/produce human language) and **computer vision** (interpret images and video). **Generative AI is an application of machine learning focused on creating new content.**

> **Exam trap:** "AI and ML are the same thing" is false, and the exam tests it. So is treating NLP as a branch of ML — it's a sibling subfield of AI.

**Narrow AI vs General AI:**

| | Narrow AI | General AI |
|---|---|---|
| Status | **Here today** — virtual assistants, spam filters, stock algorithms, all current gen AI models | **Purely theoretical.** Science fiction only |
| Scope | Task-specific; cannot step outside its lane. A fraud model can't write a novel | Human-level; moves fluidly across any task |
| How it "knows" | Pattern recognition in a constrained domain. **Correlates and predicts — no genuine understanding** | True reasoning, judgment, long-term planning |

> **Exam trap:** any answer option containing "artificial general intelligence" as the solution to a present-day business problem is **always wrong.** AGI does not exist.

### 2.2 The three ML approaches

| Approach | How it learns | Use it for | Business examples |
|---|---|---|---|
| **Supervised** | Labelled data — "a teacher guiding you with examples." Model learns input→output mapping | **Prediction** of a known outcome | Classification, regression, forecasting, churn prediction, medical image classification |
| **Unsupervised** | **No labels.** Model discovers hidden structure itself | **Exploration** — understanding the data | Customer segmentation, **anomaly/fraud detection**, topic discovery |
| **Reinforcement** | Feedback loop: agent acts → model evaluates → reward or penalty → strategy adjusts | Learning good behaviour by trial and error over many cycles | Robotics, navigation, resource allocation |

**The reinforcement loop, in order:** *agent takes an action in an environment → model evaluates the result → system sends feedback (reward/penalty) → agent's strategy adjusts → repeat.*

**Rule-based vs data-driven ML:** rule-based defines if-X-then-Y logic up front and suits **stable, well-defined** situations; data-driven learns patterns from raw data and suits **fluid** situations with plenty of data.

**Labelling has real costs** — and the exam asks about it: human effort (worse for specialist domains like medical imaging or legal), quality assurance (multiple raters must agree), operational cost (platforms, workflow tooling, secure handling), and **opportunity cost** (too little labelled data stalls development; RLHF becomes a human bottleneck).

### 2.3 What makes Gen AI different

ML **predicts**. Gen AI **creates**. From that core ability come **four functions** — memorise these four:

1. **Creation** — new text, images, audio, music, video, code.
2. **Summarisation** — condensing reports, papers, emails, transcripts.
3. **Discovery / insights** — surfacing trends, extracting themes, spotting anomalies across large volumes.
4. **Automation** — drafting responses, generating action plans, filling forms, triggering workflows: tasks that previously needed human judgment.

### 2.4 Essential terminology

| Term | Definition |
|---|---|
| **Foundation model** | Extremely large neural network trained on massive multi-domain, multi-modal data. Flexible, multi-use; adaptable without a separate model per use case |
| **LLM** | A foundation model for language — conversation, code generation, deep language understanding |
| **Multimodal model** | Understands *and* produces several data types: text, image, audio, video |
| **Diffusion model** | Starts from pure static/noise and refines step by step into an image, audio clip or video. **This is the image-generation architecture** |
| **Context window** | How much information the model can hold **at one time** while generating. Its short-term memory |
| **Prompt engineering** | **Changing the prompt.** Low effort, immediate, accessible to *end users, analysts and PMs.* No model change |
| **Prompt tuning** | **Changing the model's behaviour** by training it on many examples. Moderate effort, slower, done by *ML professionals/AI specialists* |
| **Inference** | A trained model generating a response from new incoming data. **Usually the biggest production expense** |

**Why a larger context window matters (exam-relevant):** it lets the model reference more of a conversation or document; **it reduces hallucinations** because the model can rely on actual text in the input rather than guessing; it maintains coherence over long, multi-step reasoning; and it enables enterprise work like reviewing whole legal agreements, multi-year financials, or long audit logs in a single pass.

> **Exam trap:** prompt engineering vs prompt tuning is a favourite. The discriminator is **who does it and whether the model changes.** Prompt engineering = anyone, no model change. Prompt tuning = specialists, model behaviour altered.

### 2.5 The ML lifecycle — and the Google service at each stage

**Memorise this table. It is Domain 1 and Domain 2 simultaneously.**

| Stage | What happens | Google Cloud services |
|---|---|---|
| **Ingestion** | Raw data brought in | **BigQuery** (structured, batch or streaming) · **Pub/Sub** (real-time event streams: clicks, logs, IoT) · **Cloud Storage** (bulk files, images, video, JSON — the raw landing zone for unstructured) |
| **Preparation** | Cleaned, organised, transformed | **Dataflow** (managed streaming/batch processing) · **Dataproc** (Spark/Hadoop for large ETL) · **Dataprep** (visual, *no-code* cleaning) · **BigQuery** (SQL-based transformation at scale) |
| **Training** | Model learns from examples | **Vertex AI** (custom training, fine-tuning foundation models, hyperparameter tuning) |
| **Deployment** | Model serves predictions | **GKE** (scalable container-based, high-volume inference) · **Cloud Run** (serverless, lightweight, auto-scaling) |
| **Management** | Monitor performance and health | **Vertex AI** monitoring/observability — accuracy, latency, alerting on behaviour shifts |
| **Retraining** | Keep the model current | **Vertex AI Model Monitoring** (detects **drift**, alerts when performance degrades) · **Vertex AI Pipelines** (automates the whole retraining workflow) |

**Data protection and governance services** (asked about often): **Cloud DLP** — detects and masks sensitive data (names, credit card numbers, health identifiers); supports GDPR/HIPAA compliance. **Dataplex Universal Data Catalog** — centralised view of all data assets; discovery, **metadata management, data lineage**.

### 2.6 Choosing a model — the three-step method

**Step 1: identify the use case.**

| Task | Model type | Named examples |
|---|---|---|
| Read, summarise, write, reason over text | LLM | Gemini Pro, PaLM 2 |
| Generate images, interpret visuals | Vision/**diffusion** model | **Imagen**, Stable Diffusion |
| Audio→text, text→speech | Audio foundation model | **Chirp**, **WaveNet** |
| **Cross-modal reasoning** | **Multimodal** foundation model | **Gemini Pro** |
| Domain-specific deep knowledge | Domain-tuned model | via **Vertex AI Model Garden** |
| Custom enterprise scenario | Fine-tuned/custom model | via **Vertex AI training** |

**Step 2: consider the data context.** Public/open data → general-purpose pre-trained model. **Private, sensitive or regulated data → a fine-tunable model deployed inside your own Google Cloud environment** (customisation with governance and security). Multilingual/regional/cultural → a multilingual foundation model.

**Step 3: evaluate organisational fit — four factors.** **Size and scale** (smaller = faster and cheaper; larger = better reasoning, more compute, more latency) · **cost efficiency** (inference is usually the biggest production expense; parameter-efficient tuning reduces fine-tuning cost) · **customisation and adaptability** · **ecosystem and support**.

### 2.7 Data — why it matters more than the model

> **"If models are the brain of AI, data is the blood."** Better data is often more important than a more powerful model.

**Four kinds of bad data:** **missing values** (blind spots) · **incorrect/mislabelled** (model learns patterns that don't reflect reality — fraud labelled legitimate teaches the system risky behaviour is normal) · **out-of-date** (decisions rooted in an outdated reality) · **noisy** (can't separate signal from random fluctuation).

**Four dimensions of data quality:** **completeness · consistency · relevance · availability.**

**Five types of data inconsistency:**
1. **Conflicting values** — same customer, different ages.
2. **Different formatting standards** — date formats, units, text casing.
3. **Source-of-truth misalignment** — CRM and billing disagree, so the assistant gives wrong operational advice.
4. **Semantic inconsistency** — "inactive", "closed", "dormant" used interchangeably but meaning different things.
5. **Time lag / partial updates** — recommendation engines serving stale content.

**Data and fairness:** bias enters through **underrepresentation** of groups, **historical inequity** carried forward (uneven loan approvals, selective hiring), **subjective labels**, **sampling skew**, and **imbalanced classes** (dominant class crowds out important rare cases in fraud or diagnosis).

**Three data types:**

| Type | Examples | Note |
|---|---|---|
| **Structured** | Relational tables, databases, metrics — strict schema | Easy to query and filter. **Captures facts** |
| **Unstructured** | Images, audio, video, free text | **80–90% of business information.** **Captures meaning, intent, tone** |
| **Semi-structured** | Code, emails, log files | Some organisational cues/tags, needs more processing |

> **Key exam point: Gen AI is fundamentally about unstructured data.** Generative models learn *patterns, not rules*; self-supervised learning (predicting masked/missing parts) requires high-volume natural unstructured content. But when a question involves *both* kinds of source — e.g. transaction history **and** customer emails — the answer is almost always **"both are needed"**, not "convert everything to structured."

**How multimodal actually works (five steps):** inputs arrive in different modalities → **each is encoded** (image encoder, text encoder) into numerical vectors → both are mapped into a **shared representation / latent space** → the model **fuses** them and reasons across them → a **decoder** generates the output.

**Data maturity — four levels:**
1. **Low** — data scattered across disconnected systems, no shared definitions, manual processes, frequent gaps.
2. **Emerging** — centralising onto shared platforms, high-value datasets cleaned, simple pipelines, basic governance.
3. **Moderate** — **cloud data warehouse as the single source of truth**, automated ETL/ELT, structured governance with defined metadata, role-based access control.
4. **High** — real-time high-quality data, **advanced governance with lineage tracking and quality scoring**, continuous feedback loops, **MLOps/AIOps automation**.

**Metadata** = "data that describes your data" — meaning, origin, currency, ownership. It guides AI models toward the right documents/tables and **filters out sensitive or restricted data**. Managed with **Dataplex**.

### 2.8 The five-layer Gen AI technology stack

**Bottom to top — memorise the order and one example each:**

| # | Layer | What it provides | Examples |
|---|---|---|---|
| 1 | **Infrastructure** | Compute, storage, networking, security | **TPUs**, GPUs, BigQuery |
| 2 | **Models** | Foundation and fine-tuned models that interpret, generate, transform | Gemini, Llama, GPT |
| 3 | **Platforms** | Build, train, evaluate, secure, deploy | **Vertex AI**, MLOps pipelines |
| 4 | **Agents** | Apply models to carry out tasks, decide, call tools/APIs | Vertex AI Search, BigQuery Data Insights |
| 5 | **Applications** | User-facing products | Agent Assist, virtual agents |

> **How it flows:** *Infrastructure runs the models → models power the platforms → platforms enable the agents → agents drive the applications → applications create business value.*
>
> **This is a guaranteed question type.** A scenario describes a symptom and asks which layer to fix. Map the symptom: **scaling/performance failures under load → Infrastructure.** Poor answer quality → Models. Wrong decisions/orchestration → Agents. UI/user workflow → Applications. And read carefully for what the stem says is *already working*.

**GPU vs TPU:** GPUs are **versatile parallel accelerators** for a wide range of ML workloads. **TPUs are custom Google-designed chips** engineered specifically for the matrix maths of deep learning — extremely high throughput, better price-performance for training and prediction than generic GPUs. **TPUs are a Google differentiator — expect them in an answer about Google's advantage.**

**Three model types:** **pre-trained** (ready to use, broad general training) · **fine-tuned** (further trained on domain-specific examples for sharper accuracy) · **open** (e.g. **Gemma** — freely available to download, self-host, inspect, modify; good for experimentation, offline deployment, compliance requirements).

**Four ways to tailor a foundation model:** **RAG** (connect to external knowledge at query time) · **fine-tuning / parameter-efficient tuning** (update weights, or a small subset) · **prompt engineering** (no model change) · **tool / function calling** (invoke APIs, databases, calculators — lets the model *act* and pull real-time data).

**Agent governance and reliability** (Domain 1 *and* 4): control agent **permissions**; strong **data governance** so agents access only authorised data; appropriate **autonomy levels** keeping humans involved; clear **guardrails** to limit hallucination. For reliability: structured step-by-step planning, **strict tool-call schemas**, error handling and automatic retries, and **fallback/escalation paths**.

### 2.9 Google's four flagship models

| Model | Modalities | Cost | Best for |
|---|---|---|---|
| **Gemini** | **Text, images, audio, video, code — the widest range** | Varies by size; moderate | Enterprise-grade reasoning, multimodal workflows, long context, RAG + tool calling |
| **Gemma** | Text and images | **Low** | **Open, lightweight.** Runs on modest GPUs/TPUs or local hardware. Deep fine-tuning, low latency, **hybrid/privacy-sensitive environments where data must stay local** |
| **Imagen** | Text → image (optionally with reference images) | Cost-efficient | Photorealistic image generation. Creative production, product visualisation, brand content, UI mockups |
| **Veo** | Text, image, video → video | **Most expensive** (video complexity) | Video generation and editing; coherent motion, native audio |

**How Imagen works:** a **two-part architecture** — an LLM encodes the prompt's meaning into a rich internal representation, then a **diffusion model** transforms noise into a coherent image. Separating text interpretation from image creation gives better prompt-following and compositional control.

**[+] Naming note:** the courses mention **Nano Banana** as Gemini's newer image engine, but state the exam guide still cites **Imagen**. Answer **Imagen** for image generation.

---

## SECTION 3 — Domain 2: Google Cloud's Gen AI Offerings (~35%)

**This is the largest domain and the one most candidates lose marks on. If you only have time for one section, make it this one.**

### 3.1 Google's AI history — the milestones that show up as context

| Year | Milestone | Why it matters |
|---|---|---|
| **2001** | Search converted to production ML ("Did you mean") | Google has been doing production ML for 25 years |
| **2014** | Acquired **DeepMind** | Strategic move into fundamental AI research |
| **2015** | Open-sourced **TensorFlow** | Democratised AI; made TPUs the gold standard |
| **2016** | Sundar Pichai: **"AI-first"** (no longer mobile-first). **AlphaGo** beats Lee Sedol | |
| **2017** | **The Transformer paper** — self-attention | **The architectural foundation for Gemini, GPT-4 and Claude.** Made training parallelisable = a cost and scale revolution |
| **2023** | **Gemini** launched, natively multimodal from day one. **Vertex AI** expanded for enterprise | |
| Now | **Agentic AI** era | |

### 3.2 Why Google Cloud — the differentiation answer

**Four pillars, bottom to top:** **proprietary TPUs** (better price-performance than generic GPUs) → **direct access to Google DeepMind** (breakthroughs reach the platform almost immediately) → **global private fibre-optic network** (low latency for real-time multimodal) → **integrated AI platform** (from custom models to off-the-shelf apps).

> The summarising phrase: **deep vertical integration — Google owns and operates the full technology stack.**

**Enterprise-ready means four things:** responsible AI principles embedded · enterprise governance controls · **customer data private and under the organisation's control** · strong security foundations (encryption, IAM, continuous monitoring). **Reliability at scale** is evidenced by Gmail, Search, YouTube and Maps running on the same global infrastructure.

**Gen-AI-optimised infrastructure, bottom to top:** global data centers → **custom TPU and GPU accelerators** → **hypercomputer orchestration** (coordinates thousands of compute resources for distributed training and large-scale inference) → AI platforms and models.

**General-purpose cloud vs Google's AI-optimised cloud** (a likely comparison question): general-purpose is built first for web apps and VMs with AI bolted on, performance varies at scale, higher cost per AI result, infrastructure treated as a commodity. Google's is designed for AI from the ground up, with purpose-built accelerators, hypercomputer orchestration, predictable performance and lower cost — **infrastructure as a strategic differentiator.**

### 3.3 Vertex AI — the platform layer

**The unified platform for building, training and deploying ML and gen AI models.** The dashboard mirrors the lifecycle in three areas:

1. **Prepare Data** — manage datasets and features. *Enterprise AI doesn't begin with training; it begins with governed, well-managed data.*
2. **Model Development** — **Model Garden** (selection), **training** (including **AutoML**), experiments, automatic metadata tracking.
3. **Deploy & Use** — register models, online endpoints for real-time prediction, batch inference, **Vector Search** for semantic retrieval, monitoring and scaling.

**Vertex AI Pipelines are not a stage — they connect the stages.** A pipeline can ingest data, trigger training, evaluate, register and deploy as one repeatable workflow, giving consistency, traceability and operational discipline.

**The key Vertex AI components and what each is *for*:**

| Component | Use it when |
|---|---|
| **Model Garden** | You need to **discover, evaluate and deploy** models — Google's, open-source, and third-party — from one catalogue |
| **AutoML** | The team has **good data and domain knowledge but lacks ML coding expertise**. No-code/guided training of a custom model |
| **Vertex AI Studio** | **Enterprise-scale** prompt experimentation, model tuning, evaluation, governance, deployment workflows |
| **Vertex AI Search** | You want **RAG out of the box** — grounding in enterprise content without building retrieval infrastructure |
| **Vertex AI Agent Builder** | Building **production-ready agents** with orchestration, grounding, connectors, governance |
| **Vertex AI Pipelines** | **Automating and repeating** the training→deployment workflow |
| **Vertex AI Model Monitoring** | Detecting **drift** and performance degradation in production |
| **Vertex AI Feature Store** | **Centralising the data features** models use, so different models/apps work from the same consistent, current inputs |
| **Vertex AI training** | Building fully custom or fine-tuned models on proprietary data |

**Model Garden contents — four tiers:** **first-party** (Gemini, Imagen, Veo) · **partner models** (Anthropic, Meta, Mistral, Hugging Face) · **fine-tunable models** (Gemma, Llama) · **task-specific solutions** (translation, code generation, document summarisation, text classification).

> **Model Garden is the single most-tested product in this domain.** It is the answer whenever a question involves **using open-source or third-party models alongside Gemini**, or **choosing among models**.

### 3.4 Gemini for people — app, Gems, NotebookLM

**Gemini app** — personal productivity. Acts as a **research assistant** (condenses threads, surfaces action items), a **writing partner** (structures ideas, refines tone), and a **reasoning collaborator** (organises thoughts, identifies gaps in logic).

**Gemini AI Pro** — the subscription tier, **formerly called Gemini Advanced**.

**Gems** — **customisable, reusable versions of Gemini with saved instructions** for a specific task, role or workflow. You create a Gem once (name, description, instructions, default tool, reference files) and it behaves consistently every time. Gems can be **shared across a team**, which standardises best practice, creates a unified brand voice, and speeds onboarding.

> **Gems is the answer whenever a question describes wanting a *reusable, pre-programmed persona with saved instructions* applied consistently.** Distinguish from: **NotebookLM** (grounded analysis of *your uploaded sources*), **Gemini Extensions** (connecting to external tools/services), and **search** features (retrieval).

**NotebookLM** — an AI workspace **grounded in the sources you provide** (PDFs, websites, Drive docs, pasted text). Unlike a general chatbot it reasons over *your* curated materials. The **Studio panel** turns sources into deliverables: audio overviews, video summaries, mind maps, reports, **flashcards, quizzes**, slide decks, infographics, data tables. Ideal for policy analysis, research review, contract examination, executive briefs.

**Individual vs enterprise Gemini — a likely question:**

| | Individual | Enterprise |
|---|---|---|
| Data used for training? | Interactions may improve public models | **Customer data is NOT used for model training unless explicitly opted in** |
| Knowledge | Broad public pre-learned knowledge | **Can connect to private company content** |
| Security | Standard consumer protections | Business-grade controls, IAM integration |
| Administration | User manages own settings | **Centralised admin: audit trails, governance, data retention** |

### 3.5 Gemini embedded across Google — "AI everywhere"

**Gemini is not a standalone tool — it's the reasoning engine embedded across the whole Google stack.**

**In Google Workspace:** Gmail (draft replies, condense threads, surface next steps) · Docs (drafts, clarity, audience tailoring) · Sheets (interpret trends, recommend formulas, build projections) · Slides (structure content, speaker notes) · Meet (summarise discussions, capture decisions, generate action items).

**In Google Cloud:** **BigQuery** (natural-language exploration, generate SQL, summarise insights) · **Looker** (report creation, explain trends, narrative insights) · **SecOps** (summarise threats, support incident investigation, prioritise response) · **Firebase** (generate code, troubleshoot, AI-powered app experiences).

**Two developer/ops assistants — don't confuse them:**
- **Gemini Cloud Assist** — for **cloud professionals managing environments**: lifecycle management, **diagnosing system issues and root causes**, security guidance, cost and performance optimisation.
- **Gemini Code Assist** — for **developers**: analyses entire local codebases, real-time code completion, automates multi-step tasks like refactoring and boilerplate, enterprise security support.

### 3.6 Customer experience — the contact centre stack

**The three pillars of modern CX:** **search** (immediate answers) · **conversation** (natural, human-like) · **personalisation** (tailored to them).

**The full workflow and its four products — this ordering is highly testable:**

| Stage | Product | What it does |
|---|---|---|
| 1. Customer contacts | **Conversational Agent** (Dialogflow CX) | Virtual agent using natural language understanding; handles common questions, account info, basic troubleshooting, self-service — often resolving without a human |
| 2. Escalation | *(hand-off)* | Seamless transfer to a live agent **with conversation context preserved** so the customer doesn't repeat themselves |
| 3. **During the live call** | **Agent Assist** | **Real-time** suggestions, surfaces knowledge articles, recommends responses, highlights next best actions |
| 4. **After the interaction** | **Conversational Insights** | Analyses **completed** conversations at scale: trends, common issues, sentiment, bottlenecks |

> **The classic trap: Agent Assist vs Conversational Insights.** *Live, during the call, helping the rep* → **Agent Assist.** *Analysing completed interactions for trends* → **Conversational Insights.** Read the stem for tense and timing.

**Dialogflow CX** — designing conversational agents handling **complex, multi-turn, branching dialogs**.

### 3.7 Search — traditional vs AI-powered

| Traditional search | AI-powered search |
|---|---|
| Matches **keywords** | Understands **natural language, context and intent** |
| Returns a **ranked list of links** | Returns a **synthesised answer** |
| User must open pages and piece it together | **Grounded in trusted enterprise content** |

**Vertex AI Search accepts many input types:** natural language text, **speech/audio** (search across call transcripts), **images and video**, structured and unstructured documents (PDFs, Word, slides, spreadsheets), websites, and enterprise knowledge bases (CRM, wikis, databases).

**Business impact / ROI:** faster results → higher customer satisfaction · improved self-service → **lower cost to serve** · better discovery → **higher conversion** · routine queries resolved automatically → agents freed for high-value work.

### 3.8 RAG on Google Cloud

**Why public models aren't enough for enterprises:** trained on general data (enterprises need *their* verified information) · fine for low-risk tasks (enterprises make high-stakes decisions) · **no built-in access to internal documents** · can generate plausible-but-incorrect content (business needs traceable, evidence-based answers) · training data may be out of date · **not aligned with organisational governance**.

**The RAG pipeline — three steps, know the names:**
1. **Retrieval** — instead of relying only on pre-training, the system pulls relevant information from connected corporate data sources (internal documents, knowledge bases, product manuals, policy files, structured databases).
2. **Augmentation** — the retrieved information is combined with the original prompt and passed to the model, which incorporates it into its reasoning.
3. **Generation** — the model produces a response **grounded in the retrieved content**.

**Vertex AI Search delivers RAG out of the box** — no need to build indexing, embedding pipelines and ranking logic yourself. Features: content ingestion and indexing across documents/websites/structured sources · natural language retrieval · **relevance controls** (e.g. boost official compliance docs above archived material).

**Six RAG business use cases named in the course:** HR Q&A assistant · customer support self-service · sales enablement assistant · compliance drafting · incident response runbook copilot · internal policy assistant.

### 3.9 Building — the adoption spectrum and who builds what

**The pre-built → custom continuum:**

| Level | Services | Characteristics |
|---|---|---|
| **Pre-built** | **Text-to-Speech API**, **Cloud Translation API**, Vision API, Document AI | Ready to use, minimal configuration |
| **Configurable** | **Vertex AI Search**, **Vertex AI Studio** | Tailor AI behaviour to your own data; experiment with prompts and prototype |
| **Custom** | **Vertex AI** (full model development, training, deployment), **AI agents** | Domain-specific models, fine-tuning on proprietary data, end-to-end pipelines |

**Three builder personas:** **business users** (no code — intuitive interfaces, pre-built tools) · **developers** (API level — REST APIs and SDKs) · **data scientists** (custom model layer — build, fine-tune, optimise, evaluate, deploy pipelines).

**Google AI Studio vs Vertex AI Studio — a very likely question:**

| **Google AI Studio** | **Vertex AI Studio** |
|---|---|
| **Quick iteration and exploration** | **Enterprise-scale development** |
| Test prompts, experiment with Gemini, prototype with minimal setup | Structured evaluation, **governance**, deployment workflows, access controls |
| Individual developers, small teams, validating a concept | Production use where **reliability and compliance matter** |

**Services agents draw on:** data (Cloud Storage, managed databases) · compute (**Cloud Run** containers, **functions for Cloud Run** event-driven) · language (Text-to-Speech, Translation) · media intelligence (Vision APIs, document processing).

### 3.10 Data governance in Google Cloud AI

**Always-on by default:** proprietary data stays isolated and **is not exposed for external model training**; **encryption in transit and at rest**.

**Configurable:** **data sovereignty/residency controls** (where data is stored and processed) · **IAM policies** (role-based, who can access which tools, datasets, capabilities) · **audit logging** (who accessed data, what queries were submitted, how outputs were generated).

---

## SECTION 4 — Domain 3: Techniques to Improve Model Output (~20%)

### 4.1 Foundation model strengths and limitations

**Strengths:** content creation across media · language understanding and response · **versatility** (one model, many tasks, no retraining) · **operating at scale**.

**Four limitations — the exam's favourite list:**
1. **Hallucination** — generates information that sounds convincing but is incorrect. Confident wrong statistics, fabricated citations.
2. **Bias** — reflects biases in training data; especially dangerous in hiring, lending, customer interactions.
3. **Knowledge cutoff** — trained at a point in time; unaware of recent events, product updates, policy changes unless connected to external data.
4. **Edge cases** — behaviour becomes unpredictable in rare, unusual or complex situations. **In enterprises, this is where the highest risk lives.**

> **Why hallucination happens:** the model isn't verifying facts — it's generating from **patterns and probabilities**.

### 4.2 The improvement ladder — match control to risk

**This diagram is the single most testable concept in Domain 3.**

| Risk level | Technique | When |
|---|---|---|
| **Low** | **Prompt engineering** | Drafting content, summarising. Structured prompts are enough |
| **Moderate** | **Grounding / RAG** | Accuracy matters. Customer support, internal knowledge retrieval |
| **Higher** | **Fine-tuning** | **Consistency and domain-specific behaviour are critical** |
| **Highest** | **Human-in-the-loop** | The most critical decisions. Human review before outputs are used |

Plus **monitoring and governance**, which runs across all levels over time.

**The human-in-the-loop workflow:** user submits request → AI generates an initial draft → **a human reviews** for accuracy, clarity, tone, compliance → content finalised and approved.

### 4.3 RAG vs fine-tuning — memorise this table

| | **Fine-tuning** | **RAG** |
|---|---|---|
| **Changes** | The model's **behaviour** | The model's **information** |
| Use when | **Tone, style, structure, format** must be consistent; **domain specialisation** (legal language, medical terminology) | Information **changes frequently**; answers must **reference specific documents** |
| Cost of updating | **Retraining — expensive and slow** | Just update the knowledge base — **near real-time** |
| Citations / traceability | **Weak** — knowledge is blended into the model | **Strong** — pulls from specific documents at runtime |
| Typical cases | Legal drafting style, medical coding classification, highly structured output | Product documentation, internal knowledge bases, support articles, policies that change monthly |

> **The two exam traps, both seen in the course examples:**
> - *"Fine-tuning is more cost-effective for frequently changing data"* — **false.** Retraining on every change is expensive and inefficient.
> - *"RAG is better for teaching a brand voice or creative tone"* — **false.** That's fine-tuning's job.
>
> **Memorise the one-liner:** *changing facts → RAG. Changing behaviour → fine-tuning.*

**Grounding as an open-book test:** without grounding the model answers "from memory" and fills gaps with plausible guesses. With RAG it's an **open-book exam** — it can reference the correct material before answering.

### 4.4 Prompt engineering

**Four components of a strategic prompt:**

| Component | Purpose | Example |
|---|---|---|
| **Instruction** | *What* to do | "Create an overview" — active verb + task type |
| **Context** | Background, role, audience, situation | "Mobile budgeting application for recent college graduates" |
| **Structure** | How the response is organised | "Three bullet points", a table, step-by-step |
| **Constraints** | Boundaries | "Under 120 words", avoid competitors, formal tone |

**Worked contrast:** *"Summarize this report"* (model has to guess what matters) versus *"Summarize the report in three bullet points focused on revenue growth, risks, and strategic priorities"* (format specified, focus specified, ambiguity removed).

**The prompting techniques — know which solves which problem:**

| Technique | What it is | Use for |
|---|---|---|
| **Zero-shot** | Instructions only, no examples | Straightforward tasks |
| **One-shot** | One example | Enforcing a **specific format** or interpretation |
| **Few-shot** | Multiple examples | Complex/ambiguous tasks; teaching category distinctions and edge cases |
| **Role prompting** | Assign a role/perspective ("act as a product manager") | Bringing the right domain lens and priorities |
| **Prompt chaining** | Break into a **sequence of separate connected steps** | Complex workflows; transparency and control |
| **Chain-of-thought** | Model shows intermediate reasoning **within a single prompt and response** | **Multi-step maths, logic, analytical reasoning.** Also when you must explain how a conclusion was reached |
| **ReAct (Reason + Act)** | Reasoning **plus retrieving additional information** | Research tasks needing external data, tool/database queries, multi-source investigations |

> **Chain-of-thought vs prompt chaining vs ReAct:** chain-of-thought = one prompt, one response, visible reasoning. Prompt chaining = several separate steps. ReAct = reasoning *plus* going and fetching data.
>
> **Exam signal: "complex multi-step math and logical deductions… output frequently incorrect" → chain-of-thought.**

**Trade-offs of advanced prompting:** increased **transparency** (valuable in regulated environments), but added **latency** (more steps) and **cost** (more tokens).

### 4.5 Controlling output — parameters

> **The single most important conceptual point in this domain: grounding controls the *information*, not the *behaviour*.** A perfectly grounded model can still answer in the wrong tone. Tone, style and consistency are managed through **prompts and parameters**, not grounding.

| Parameter | Effect | Low value | High value |
|---|---|---|---|
| **Temperature** | Predictability vs creativity | Consistent, focused, factual — **customer support, summarisation, internal knowledge, compliance, technical documentation** | Varied, imaginative — **marketing slogans, brainstorming, creative writing, ideation** |
| **Top-P (nucleus)** | Selects the smallest set of words whose **cumulative probability** reaches a threshold (e.g. 0.9 = top 90% of likelihood) | Conservative, focused | Broader word choice, more variation |
| **Top-K** | Limits to a **fixed number** of most likely next tokens (e.g. 25) | Tightly focused | More variety, less predictability |
| **Output token limit** | How much text can be generated | Concise summaries | Detailed step-by-step guides. Affects cost |
| **Seed** | Controls randomness for **reproducible results** | — | Useful for **testing and debugging** |

**Matching parameters to use case:** customer support chatbot → low temperature, focused token selection, moderate length. Feedback analysis → moderate temperature, larger token limit. Idea generation → **high** temperature, broad token range. Executive summaries → **low** temperature, tight constraints, short length.

**The risk/variability alignment:** low risk (brainstorming, slogans, social posts) tolerates variability · moderate risk (meeting summaries, reports, product descriptions) needs clarity and accuracy with some flexibility · **high risk (customer support responses, compliance explanations, financial guidance) requires tightly controlled variability.**

**Safety filters in Vertex AI** cover four categories — **hate speech, dangerous content, sexually explicit content, harassment** — each settable to **Off / Block few / Block some / Block most**.

**[+] Also in the Vertex AI settings panel:** model choice, thinking level (low/medium/high — higher brings detail but **more cost and latency**), structured output (enforce JSON), grounding options (Google Search, Google Maps, your own enterprise data via RAG engine or Vertex AI Search), region.

### 4.6 Monitoring, drift and continuous improvement

**The lifecycle is a loop, not a line:** create the solution → release → **monitor** → **evaluate** → **improve** → **update** → repeat.

**Five KPIs for a gen AI system:** how often outputs are **correct/reliable** · how often the model produces **unsupported or incorrect content** (hallucination rate) · **latency** · **user feedback/satisfaction** · **policy or safety violations**.

**Drift monitoring:** performance shifts away from **ground truth** over time, usually because **real-world inputs evolve** — user behaviour, business processes, or external conditions change and no longer match the training data. A support assistant trained on older product features struggles with new releases. Track accuracy, hallucination frequency and user feedback to detect it early.

**Version control** works alongside drift monitoring: track what changed and its impact, and **revert quickly** when an update introduces problems.

**Three kinds of ongoing update:** **security updates** (new vulnerabilities) · **platform patches** (infrastructure bugs and stability) · **performance upgrades** (speed, accuracy, resource efficiency, cost).

**Vertex AI Feature Store** — "a well-stocked pantry for a chef." Centralises the **data features** models use so different models and applications work from the **same consistent, current inputs**. Examples: customer purchase history, product usage patterns, recent support interactions.

---

## SECTION 5 — Domain 4: Business Strategies (~15%)

### 5.1 From hype to value

**Why initiatives stall:** lots of experimentation and demos with **no clear connection to business value** — then come the questions about ROI, security and fit.

**What successful initiatives have — three things:** a **clear use case** (something specific the business is solving) · **measured impact** with defined metrics · **integration into a workflow** (part of how work gets done, not a standalone tool).

**The strategy-to-value pipeline — four stages:**

| Stage | What happens | Tools named |
|---|---|---|
| **1. Define the business problem** | Identify high-value opportunities; align to **goals and KPIs** (cost reduction, customer satisfaction, time to market) | **BigQuery** (analyse data, validate opportunities) · **Looker** (define and track KPIs via dashboards) |
| **2. Choose the solution** | Map the business need to the right gen AI capability; choose approach and evaluate cost | Gemini APIs, pre-built models, or customise in **Vertex AI** |
| **3. Integrate into workflows** | Embed in systems people already use; ensure scalability and security | **Agent Builder** · **Cloud Run** |
| **4. Measure and optimise** | Track KPIs, ROI, quality; monitor and iterate — refine prompts, improve data, adjust workflows | **BigQuery** · **Looker** |

**Capability → business outcome mapping:**

| Capability | Outcome |
|---|---|
| Text generation | Faster content creation |
| **RAG** | **Better customer support** (accurate, grounded answers) |
| Code generation | Improved developer productivity |
| Personalisation | Increased conversion |
| Multimodal understanding | Improved customer experience |

**The ROI formula:** **Value** (productivity gains + cost savings + new revenue + risk reduction + strategic value) **− Costs** (development + operational + integration + **governance: compliance, monitoring, security, responsible AI practices**).

### 5.2 Choosing a solution

**Four factors to balance — "like a sound-mixing board":** **business value** (impact you're creating) · **cost** · **risk** (customer-facing/high-stakes needs more accuracy, security, control) · **constraints** (technical limits, available data, team expertise, timelines).

> *The best solution isn't the one that maximises any single factor — it's the one that balances all four.*

**Pre-built vs custom:**

| | **Pre-built** | **Custom** |
|---|---|---|
| Deployment | **Rapid** | Longer development and testing |
| Upfront cost | **Lower** | **Higher** — specialist skills, infrastructure, time |
| Ease of use | Streamlined, minimal setup | Requires expertise |
| Flexibility | Standardised | **Tailored to exact requirements** |
| Maintenance | **Vendor manages** updates | **You own it** — and are responsible for it |
| Strategic effect | Ideal for **common, repeatable** use cases | Enables **differentiation and competitive advantage** |

**The decision matrix — impact × complexity:**

| | **Low complexity** | **High complexity** |
|---|---|---|
| **High impact** | **Pre-built solution** — move fast, capture value | **Custom solution** — investment delivers differentiation |
| **Low impact** | **Don't build** — limited ROI | **Approach with caution / reconsider** — high effort, disproportionate value |

> **Exam signal: "needs a solution quickly", "strict budget constraints", "limited AI expertise" → pre-built with minimal customisation.** Building a foundation model from scratch is *always* wrong in these scenarios. So is "train a proprietary model using **all available enterprise data**" — that adds privacy and security risk on top of cost.

### 5.3 Pilot to production

> 🔴 **CORRECTION, 2026-09-15.** The five stages below are the **Pluralsight** model. **The exam uses a different five-phase framework with different names**, and it cost me 3 marks on the practice exam. Learn the exam's version first:
>
> | Phase | Goal | Signature activity |
> |---|---|---|
> | **Dream** | Ideate — what could gen AI do for us? | Exploring possibilities |
> | **Select** | Choose which use case to pursue | Prioritising by value and feasibility |
> | **Scale** | Take a *validated* pilot to broad rollout | **Infrastructure for concurrent users AND change management + training.** Both, always |
> | **Refine** | Improve the **live** solution through measurement and iteration | Feedback loops (thumbs up/down) feeding fine-tuning. **Stays in production** — never roll back |
> | **Expand** | Leverage the success to find **new** use cases elsewhere in the business | Restarts the cycle with new Dream and Select for other departments |
>
> **The discriminator: same solution getting better = Refine. New solutions elsewhere = Expand.**
>
> *Verify the phase names against the official study guide PDF and Skills Boost path 1951 — I could not find this framework in Google's public documentation, only in the exam's own rationales. Full treatment in [../practice/03-common-mistakes.md](../practice/03-common-mistakes.md).*

**The Pluralsight five stages (retained for the concepts, which are still sound):** **pilot** (test ideas, prototypes, minimal investment) → **validation** (confirm it works technically *and* in business value, accuracy, feasibility) → **integration** (embed into real workflows and systems) → **scale** (expand across teams/systems/customers with reliable infrastructure) → **optimisation** (continuously improve). **It loops** — production sends you back to validation as requirements evolve.

**Organisational readiness — people, process, technology.**
> **The key takeaway the course states explicitly: technology is only one part of the equation. People and processes ultimately determine success.** Expect a question where the right answer is about skills/adoption/governance, not tooling.

**Four success metrics:** **time saved** · **accuracy** · **cost reduction** · **customer satisfaction**.

### 5.4 Security

**Three primary risks → three attack surfaces → three business consequences:**

| Risk | Attack surface | Business consequence |
|---|---|---|
| **Prompt injection** | **User input** | Loss of trust, legal exposure |
| **Data leakage** | **Data sources** | Incorrect or harmful outputs; exposure of sensitive information |
| **Model misuse** | **Output** | Brand damage, compliance issues |

**Shared responsibility model:**

| **Customer** | **Shared** | **Google Cloud** |
|---|---|---|
| **Your data, access controls, how models are used, governance policies** | **Configuration and monitoring** | **Physical security of hardware and data centers, core services** |

> **Exam trap, straight from the course example:** asked what remains **primarily** the customer's responsibility, both *"defining user access controls and governance policies"* and *"configuring security settings and access permissions correctly"* look right. **Configuration is a *shared* responsibility.** The answer is **defining access controls and governance policies.**

**Expanding threat surfaces as systems scale:** **users** (misuse, unexpected inputs) · **data sources** (leakage or contamination) · **integrations** (insecure APIs, vulnerable dependencies) · **automation** (**cascading failures** — one issue propagates across workflows at speed).

**Regulations named:** **HIPAA** (health), **GDPR** (privacy), **ISO** and **NIST** frameworks.

### 5.5 SAIF — Google's Secure AI Framework

**Four pillars, and the Google service for each:**

| Pillar | Actions | Services |
|---|---|---|
| **1. Protect data** | Encrypt and classify sensitive information; prevent leakage and unauthorised access | **Cloud DLP** (identify/manage sensitive data) · **Cloud KMS** (encryption and key management) |
| **2. Secure models** | Guard against misuse; control how models are trained, tuned and accessed | **Vertex AI** controls · model policies |
| **3. Control access** | Enforce identity and access management; **least privilege**; boundary protections | **IAM** · **VPC controls** |
| **4. Monitor and respond** | Continuously monitor for threats and anomalies; detect, alert, respond | **Cloud Monitoring** · **Security Command Center** |

**SAIF's characteristics:** applies security **across the entire AI lifecycle** (data, training, deployment, application) · protects data, models and systems from misuse and attack · **aligns security controls with business risk and compliance** · emphasises identity, access control and data protection · supports continuous monitoring, detection and response.

**Google Cloud's defence-in-depth layers** (bottom to top): **hardware** (Google designs and builds its own; physically secured data centers) → **software** (health check at every boot; if it fails the drive won't boot) → **storage** (encrypted at rest; **data in memory broken into chunks and distributed**) → **identity** (**zero-trust** — nothing trusted by default) → **network** (encrypted in transit, multiple layers of protection) → **operations** (24/7 security teams detecting, preventing, responding).

**Security Command Center** — centralised monitoring, detection and response: **alerts** (potential issues/policy violations) · **threat indicators** (patterns of suspicious activity) · **system health** (status, vulnerabilities, misconfigurations).

### 5.6 Responsible AI

**Why it's a business imperative:** governance failures escalate from technical systems to **regulatory scrutiny, loss of customer trust, and public/media scrutiny.** *"Trust… just like a tall glass building, can appear strong right up until a small weakness begins to spread."*

**Five concrete consequences named:** unauthorised data exposure → privacy violation, fines · AI hiring bias → discrimination claims · inconsistent decisions → erosion of confidence · biased loan approval models → regulatory investigation · **unmonitored autonomous actions → operational disruption**.

**Black-box vs transparent AI:** black-box decisions are hard to explain or justify, with limited visibility into data and reasoning, reducing trust. Transparent AI makes decisions easier to understand, **provides visibility into data sources and outputs** (which documents/policies contributed), and supports accountability.

**Where bias enters — five points across the lifecycle:**
1. **Data collection** — incomplete, imbalanced, underrepresenting groups.
2. **Labelling and training** — subjective human decisions, uneven examples (historical hiring data reinforcing past imbalance).
3. **Model weighting/optimisation** — favouring overall accuracy while producing uneven results for specific groups.
4. **Deployment** — using a model in a different context than it was designed and tested for.
5. **User interaction and feedback loops** — engagement patterns amplifying existing bias over time.

**Measuring bias — four instruments:** **demographic balance** · **error rates** · **confidence scores** · **fairness indicators**.

**The bias-reduction workflow:** improve datasets (accurate, representative, diverse) → **diversify testing** (across groups, environments, edge cases) → **human review** → monitoring → feedback loops.

**Anonymisation vs pseudonymisation — a guaranteed question:**

| | **Anonymisation** | **Pseudonymisation** |
|---|---|---|
| Method | Identifying information **removed or redacted** | Identities **converted to ID numbers / replacement values** |
| Result | Fully masked identity | **Tokenised** identity |
| Reversible? | **Intentionally hard to reconnect** | **Can be re-linked** via lookup tables with authorised access |
| Strength | **Stronger pure privacy** | **More operational flexibility** |
| Typical use | Public datasets, analytics, research | **Enterprise systems** needing privacy *and* the ability to reconnect data |

**How data spreads through a gen AI system** (the privacy risk chain): **prompt** → **model processing** → **logs** (prompts containing customer information can unintentionally appear in application logs) → **analytics systems** → **integrations** (each one another place data may be processed, stored or transmitted).

**Explainability — four audiences and what each needs:** **customers** (why a decision was made; fair, consistent interactions) · **compliance officers** (evidence controls and governance are working) · **executives** (alignment with business goals; brand and reputational risk) · **auditors** (**traceability** into inputs, outputs, decision processes; **logs and records** as evidence).

**Three components of an explanation:** **contributing factors** (which inputs/variables most influenced the output) · **source references** (where the information originated) · **confidence scores** (low confidence signals the need for validation or human review).

**Human oversight** remains essential even with explainability tools: a reviewer may **approve** an output that aligns with policy, or **reject/override** one with issues or risk. And **auditability** — visibility into inputs, outputs, approvals, overrides and system behaviour over time.

---

## SECTION 6 — The product cheat sheet

**If you memorise one table, make it this one. Domain 2 is ~35% of the exam and most of it is "which product for this job?"**

| Need | Product |
|---|---|
| Discover/deploy Google, open-source **and** third-party models in one place | **Vertex AI Model Garden** |
| Train a custom model with **good data but no ML coding expertise** | **Vertex AI AutoML** |
| **RAG out of the box**, grounded in enterprise content | **Vertex AI Search** |
| Build a **production-ready agent** with connectors and governance | **Vertex AI Agent Builder** |
| **Quick prototyping** of prompts, minimal setup | **Google AI Studio** |
| **Enterprise** prompt work with evaluation, governance, deployment | **Vertex AI Studio** |
| Automate and repeat the training→deployment workflow | **Vertex AI Pipelines** |
| Detect **drift** in production | **Vertex AI Model Monitoring** |
| Consistent, current **data features** shared across models | **Vertex AI Feature Store** |
| Semantic retrieval over vectors | **Vertex AI Vector Search** |
| **Reusable Gemini persona** with saved instructions | **Gems** |
| Reason over **your own uploaded documents**; produce briefs, quizzes, audio overviews | **NotebookLM** |
| **Live, real-time help for a human agent on a call** | **Agent Assist** |
| **Post-call analysis** — trends, sentiment, bottlenecks | **Conversational Insights** |
| Virtual agent handling complex **multi-turn branching** dialog | **Conversational Agents / Dialogflow CX** |
| Help cloud teams **diagnose issues, optimise cost, manage environments** | **Gemini Cloud Assist** |
| Help **developers** write, refactor, complete code | **Gemini Code Assist** |
| Natural-language data exploration and SQL generation | **Gemini in BigQuery** |
| BI narratives, report creation, trend explanation | **Gemini in Looker** |
| Threat summarisation and incident investigation | **Gemini in SecOps** |
| Detect and **mask sensitive data** (PII, PHI, card numbers) | **Cloud DLP** |
| Encryption and **key management** | **Cloud KMS** |
| **Who can do what** — least privilege | **IAM** |
| Network-level access boundaries | **VPC controls** |
| Central security **alerts, threat indicators, system health** | **Security Command Center** |
| Data catalogue, **metadata, lineage** discovery | **Dataplex** |
| **No-code** visual data cleaning | **Dataprep** |
| Managed streaming/batch data processing | **Dataflow** |
| Spark/Hadoop large-scale data prep | **Dataproc** |
| **Real-time event ingestion** (clicks, logs, IoT) | **Pub/Sub** |
| Structured data warehouse + SQL-based prep + ML in place | **BigQuery / BigQuery ML** |
| Unstructured content lake | **Cloud Storage** |
| **Serverless** lightweight deployment | **Cloud Run** |
| Scalable container-based high-volume inference | **GKE** |
| Ready-made speech/translation | **Text-to-Speech API / Cloud Translation API** |
| KPI dashboards | **Looker** |

---

## SECTION 7 — Practice questions

*Original questions in the official style. Answers and full reasoning follow each block. Work them with the elimination method — write down why each wrong option is wrong before checking.*

### Block A — Domain 1: Fundamentals

**A1.** A retail analytics team wants to group customers into natural segments without predefined categories, and separately wants to forecast next quarter's demand from three years of labelled sales history. Which combination of ML approaches is appropriate?

A. Unsupervised learning for both tasks
B. Supervised learning for segmentation, reinforcement learning for forecasting
C. **Unsupervised learning for segmentation, supervised learning for forecasting**
D. Reinforcement learning for both tasks

> **Answer: C.** Eliminate **D** first — reinforcement learning is about an agent learning behaviour through reward and penalty in an environment; neither task is a feedback loop. **B** inverts reality: segmentation *without predefined categories* is the definition of unsupervised, and forecasting from labelled history is textbook supervised. **A** fails because the forecasting task explicitly has labelled outcomes, which is exactly what supervised learning is for — using unsupervised there wastes the labels. **C** matches each technique to the nature of the data: no labels → discover structure; labels present → predict a known outcome.

**A2.** A manufacturer's chatbot works well for common product questions but gives inconsistent and occasionally incorrect guidance for unusual warranty scenarios that appear rarely in the training data. What does this illustrate?

A. Knowledge cutoff
B. **Edge case behaviour**
C. Prompt injection
D. Semantic inconsistency

> **Answer: B.** **A** is wrong because knowledge cutoff concerns *recency* — events after training — not rarity. Nothing here suggests the warranty rules are new, only that they're unusual. **C** describes a malicious input manipulating the model, which isn't in the scenario. **D** is a *data quality* problem (terms used inconsistently), not a model behaviour pattern. **B** is the exact definition: rare, unusual or complex situations where the model has seen fewer examples, so responses become less reliable — and in enterprises this is where the highest risk sits.

**A3.** Which two are subfields of artificial intelligence that sit alongside machine learning rather than inside it?

A. Generative AI and deep learning
B. **Natural language processing and computer vision**
C. Diffusion models and reinforcement learning
D. Prompt engineering and prompt tuning

> **Answer: B.** **D** is out immediately — those are *techniques for working with* models, not subfields of AI. **C** mixes categories: diffusion models are a model architecture, reinforcement learning is an ML approach (so it's *inside* ML, not alongside it). **A** fails because generative AI is an *application of machine learning*, placing it inside ML, not beside it. **B** is correct: NLP and computer vision are subfields of AI in parallel with ML, and they combine with ML to create multimodal systems.

**A4.** A logistics company's model was trained on 2023 delivery patterns and is now producing poor route recommendations following a major change in regional distribution centres. Which data problem is this?

A. Noisy data
B. Conflicting values
C. **Out-of-date data**
D. Missing values

> **Answer: C.** **D** would mean gaps in fields — nothing suggests incompleteness. **A** means irrelevant detail and random fluctuation obscuring the signal, which isn't described. **B** is a *consistency* problem — the same field holding incompatible truths — again not what's described. **C** is precisely the case: the model learned historical patterns that no longer apply because operational conditions evolved.

**A5.** An organisation needs a model that can run on modest local hardware in a privacy-sensitive environment where data must not leave the premises, and wants the ability to fine-tune it deeply. Which Google model family fits?

A. Gemini
B. **Gemma**
C. Imagen
D. Veo

> **Answer: B.** **C** and **D** are single-purpose generative models for images and video respectively — neither addresses local hosting or deep fine-tuning of a general model. **A** is Google's flagship multimodal model, powerful but not the choice when the requirement is running on modest hardware in a local, privacy-sensitive environment. **B** is exactly it: Gemma is Google's **open**, lightweight family, optimised for modest GPUs/TPUs and even local hardware, supporting deep fine-tuning and hybrid or privacy-sensitive deployments.

**A6.** A team has built and validated the agent logic and selected an appropriate foundation model, but the system fails to serve reliably when traffic triples during a seasonal peak. Which layer of the gen AI stack requires attention?

A. Model layer
B. Agent layer
C. **Infrastructure layer**
D. Application layer

> **Answer: C.** *(Adapted from a course example.)* The stem tells you what is already working — that's the key. The **model** is "selected and appropriate", so **A** is out. The **agent logic** is "built and validated", so **B** is out. **D** is wrong because the failure occurs before the application can execute its workload — it's a serving problem, not an app-logic problem. Scaling failures under load point directly to compute, networking and serving capacity: the **infrastructure layer**.

### Block B — Domain 2: Google Cloud offerings

**B1.** A media company wants to standardise how its marketing team uses AI, so that every team member producing campaign copy gets the same brand tone and always includes a legal disclaimer, without re-explaining the requirements each time. Which capability fits best?

A. NotebookLM
B. **Gems**
C. Vertex AI Model Monitoring
D. Gemini Extensions

> **Answer: B.** **C** is out instantly — model monitoring detects drift in production models, nothing to do with reusable instructions. **A** is for grounded reasoning over *uploaded source documents*, not for creating a persistent persona. **D** connects Gemini to external tools and services; useful, but extensions don't define a saved role, tone or instruction set. **B** is the definition of a Gem: a customisable, reusable version of Gemini with saved instructions that behaves consistently every time, and which can be **shared across a team** to standardise practice.

**B2.** An insurance company's support representatives handle live phone calls. Management wants representatives to receive suggested responses and relevant policy excerpts **while the call is in progress**. Which product?

A. Conversational Insights
B. Dialogflow CX
C. **Agent Assist**
D. Vertex AI Pipelines

> **Answer: C.** **D** orchestrates ML workflows — irrelevant to live support. **B** builds the *virtual* agent that handles conversations before a human is involved; here a human is already on the call. **A** is the trap: Conversational Insights analyses **completed** interactions for trends, sentiment and bottlenecks — valuable, but retrospective. The stem says *while the call is in progress*. **C**, Agent Assist, is purpose-built to support representatives during active calls with real-time suggestions and document snippets.

**B3.** A financial services firm wants an internal assistant that answers employee questions using the company's own HR policy documents, which are updated monthly. The team wants to avoid building indexing, embedding and ranking infrastructure themselves. Which is most appropriate?

A. Fine-tune Gemini monthly on the HR documents
B. **Vertex AI Search**
C. AutoML
D. Google AI Studio

> **Answer: B.** **C** trains custom predictive models from tabular data — wrong problem entirely. **D** is a prototyping environment for quick experimentation, not a production grounding solution. **A** is the classic RAG-vs-fine-tuning trap: monthly retraining is expensive, slow, and loses source traceability — precisely the wrong tool for frequently-changing facts. **B** delivers **RAG out of the box**, handling ingestion, indexing and retrieval so the team doesn't build it, and keeps answers grounded in current documents.

**B4.** A development team wants to prototype and compare prompts against Gemini quickly, with minimal setup, before deciding whether to proceed. Later, the same organisation will need structured evaluation, access controls and deployment governance. Which pair is correct?

A. Vertex AI Studio first, then Google AI Studio
B. **Google AI Studio first, then Vertex AI Studio**
C. Model Garden first, then AutoML
D. NotebookLM first, then Vertex AI Search

> **Answer: B.** **C** and **D** name products that don't serve either purpose — Model Garden is model discovery, AutoML is no-code training, NotebookLM is document reasoning, Vertex AI Search is grounding. **A** has the right two products in the wrong order. **B** matches their design intent: **Google AI Studio** for speed, creativity and quick iteration at the experimentation stage; **Vertex AI Studio** for enterprise-scale evaluation, governance and production deployment.

**B5.** An enterprise wants to deploy a specific open-source model from Hugging Face alongside Gemini within the same managed environment. Which supports this?

A. **Vertex AI Model Garden**
B. Vertex AI Feature Store
C. Cloud Run
D. Dataplex

> **Answer: A.** *(Adapted from a course example.)* **B** centralises data features for models — not a model catalogue. **D** is data cataloguing, metadata and lineage. **C** is serverless deployment; it could *host* something but doesn't address discovering and managing models together. **A** is the centralised catalogue containing Google first-party models (Gemini, Imagen, Veo), partner models (Anthropic, Meta, Mistral, Hugging Face), fine-tunable open models and task-specific solutions — exactly the "use both together" requirement.

**B6.** A retailer has strong domain knowledge and clean historical sales data but no machine-learning engineers. They want a custom model predicting inventory needs. Which capability lowers the barrier?

A. Vertex AI Pipelines
B. **AutoML**
C. Vertex AI Studio
D. Model Garden for local fine-tuning

> **Answer: B.** *(Adapted from a course example — note the giveaway word.)* **A** assumes the team can already write and manage training code, which is the exact gap. **C** is for prompt work with foundation models, not structured prediction from tabular business data. **D** requires significant ML knowledge to download and fine-tune locally. **B** is designed for teams with **strong data and domain knowledge but limited ML coding experience**, automating training, tuning and evaluation.
>
> *Technique note: in the original version of this question, the word "manual" appeared in all three wrong answers. Scan for that pattern.*

**B7.** Which statement about Gemini in an enterprise deployment is correct?

A. Customer interactions always contribute to improving Google's public models
B. **Customer data is not used for model training unless the organisation explicitly opts in**
C. Enterprise deployments rely only on the model's public pre-trained knowledge
D. Individual users manage their own audit trails and retention rules

> **Answer: B.** **C** is backwards — enterprise deployments *can* connect Gemini to private company content so responses are grounded in internal context. **D** inverts the model: enterprise deployments introduce **centralised** administration including audit trails, governance and retention; individuals manage their own settings. **A** describes *individual/personal* usage, where interactions may contribute to improving general-purpose public models — the opposite of the enterprise guarantee. **B** is the stated enterprise protection.

### Block C — Domain 3: Techniques

**C1.** A healthcare provider's assistant must answer questions about clinic hours and insurance policies that change monthly. The IT director proposes fine-tuning. Why recommend RAG instead?

A. Fine-tuning is more cost-effective for frequently changing data
B. RAG is better for teaching a specific brand tone
C. **RAG allows near real-time updates of facts without the cost of retraining**
D. Fine-tuning provides better source attribution than RAG

> **Answer: C.** *(From a course example.)* **D** flips reality — RAG is what *enables* citations, because it pulls from identifiable documents at runtime; fine-tuning blends knowledge into weights and loses traceability. **A** doesn't hold: fine-tuning requires retraining on every update, which is expensive and inefficient for monthly changes. **B** swaps the use cases — tone and voice are fine-tuning's strength, not RAG's. **C** is the fit: RAG pulls the latest information as it changes, ideal for dynamic facts.

**C2.** A retailer's support bot is correctly grounded in the product manual, but responds to complaints in flowery, overly poetic language that customers find dismissive. What should a leader explain?

A. Grounding is failing and the manual needs more data
B. Switching to zero-shot prompting will fix the tone
C. The model's knowledge cutoff is causing the poetic language
D. **Grounding controls factual accuracy, not the creative tone or style of the output**

> **Answer: D.** *(From a course example.)* **B** confuses mechanisms — zero-shot concerns how many *examples* you supply, not stylistic control. **C** is irrelevant: knowledge cutoff affects how *current* information is, not how it sounds. **A** contradicts the stem, which says grounding is working correctly. **D** is the principle: grounding controls the *information*; tone, style and consistency are managed separately through prompts and parameters.

**C3.** A tax compliance team is using gen AI for multi-step calculations and logical deductions. Outputs are frequently wrong. Which technique should the leader insist on?

A. One-shot prompting with a single example
B. **Chain-of-thought prompting**
C. Raising temperature to 1.0
D. Removing constraints from the prompt

> **Answer: B.** *(From a course example.)* **D** would make it worse — constraints guide reasoning and keep the model focused. **C** is counterproductive: higher temperature increases randomness, the opposite of what multi-step logic needs. **A** helps with *format and pattern*, but the problem isn't a lack of examples — it's a lack of structured reasoning. **B** guides the model to work through each step explicitly, which substantially improves accuracy on multi-step logic.

**C4.** A marketing team wants twenty distinct campaign slogan options for brainstorming. Which parameter configuration is most appropriate?

A. Low temperature, low top-K, short token limit
B. **Higher temperature, broader top-P/top-K, moderate token limit**
C. Low temperature with a fixed seed
D. Maximum token limit with temperature 0

> **Answer: B.** **C** and **D** both pin the model to its most likely outputs — a fixed seed adds *reproducibility*, and temperature 0 produces near-identical results each time, which is the opposite of generating twenty distinct options. **A** is the configuration for factual, consistent tasks like support responses. **B** matches creative ideation: higher temperature and a broader token pool widen the range of outputs, and slogans don't need a large token limit.

**C5.** An organisation wants to apply appropriate oversight to a gen AI system that drafts regulatory filings — a high-consequence, low-tolerance task. According to the risk ladder, what is the appropriate control?

A. Prompt engineering alone
B. Grounding with RAG alone
C. Fine-tuning alone
D. **Human-in-the-loop review before outputs are used**

> **Answer: D.** The ladder matches control to risk. **A** suits low-risk drafting and summarising. **B** suits moderate risk where accuracy matters — support, internal knowledge. **C** suits higher risk needing consistency and domain-specific behaviour. Regulatory filings are the most critical tier, where **D** applies: human review validates outputs before use, ensuring accuracy, compliance and accountability. Note the ladder is cumulative — you'd likely use grounding *and* fine-tuning *and* human review — but the question asks what the top tier requires.

**C6.** A customer-service model that performed well six months ago is now producing less relevant answers, although the model itself has not been changed or updated. What is the most likely explanation and the appropriate response?

A. Prompt injection; add input filtering
B. **Drift; monitor KPIs against baselines and retrain or update the knowledge source**
C. Knowledge cutoff; switch model families
D. Hallucination; lower the temperature

> **Answer: B.** **A** describes a malicious manipulation, not gradual degradation. **D** misdiagnoses: hallucination is fabricating content, and temperature affects variability rather than relevance decay over time. **C** is close but wrong — knowledge cutoff is a fixed property from training, and switching model families doesn't address evolving inputs. **B** is drift: real-world inputs evolve (user behaviour, products, business processes) so the data the model encounters no longer matches its training. The response is monitoring accuracy, hallucination frequency and user feedback against baselines, then retraining or refreshing the retrieval source.

### Block D — Domain 4: Business strategies

**D1.** A mid-sized firm needs a gen AI solution quickly, has strict budget constraints and limited AI expertise. Which approach is most appropriate?

A. Build a fully custom foundation model from scratch
B. Train a proprietary model using all available enterprise data
C. **Use a pre-built gen AI solution with minimal customisation**
D. Use only open-source models hosted on-premises

> **Answer: C.** *(From a course example.)* **B** is worst: training a proprietary model already brings cost, complexity and governance requirements, and *"all available enterprise data"* adds unnecessary privacy and security risk. **A** requires major time, budget, infrastructure and specialist expertise the firm doesn't have. **D** looks budget-friendly because open source is free, but **hosting entirely on-premises** raises operational overhead and infrastructure demands — precisely what a team with limited AI resources can't absorb. **C** gives fast deployment, lower upfront cost and managed capabilities.

**D2.** Under the shared responsibility model, which remains **primarily** the customer's responsibility?

A. Securing Google's physical data centres
B. **Defining user access controls and governance policies**
C. Managing hardware-level encryption chips
D. Configuring security settings and access permissions correctly

> **Answer: B.** *(From a course example.)* **A** and **C** are plainly Google's — physical security and hardware. The genuine difficulty is **D** versus **B**: both mention access. **Configuration is a *shared* responsibility** between customer and provider, so it isn't *primarily* the customer's. **B** is: customers determine who can access systems and data, and establish the governance policies guiding secure, compliant AI use.

**D3.** A hospital group wants to use patient records to improve a gen AI assistant while reducing privacy risk. Which approach is most appropriate?

A. Role-based access controls without reducing identifiable information in the dataset
B. Remove logging and monitoring so sensitive data isn't captured
C. Encrypt the data while continuing to use directly identifiable patient information
D. **Use anonymisation or pseudonymisation before processing the data**

> **Answer: D.** *(From a course example.)* **C** protects data at rest and in transit but leaves identifiable information exposed *inside the AI processing workflow* — the exact thing to avoid. **A** limits who can view data, which is good practice, but doesn't reduce the risk of processing directly identifiable information. **B** is superficially appealing and genuinely harmful: removing logging destroys visibility into system activity and security events, making misuse harder to detect and compliance harder to maintain. **D** masks or transforms sensitive identifiers *before* the data reaches the gen AI system.

**D4.** A company has identified a use case with high potential business impact that would require substantial customisation and specialist development. Where does it sit on the decision matrix, and what follows?

A. Low impact, low complexity — don't build
B. **High impact, high complexity — custom solution justified**
C. High impact, low complexity — use pre-built
D. Low impact, high complexity — reconsider

> **Answer: B.** The matrix crosses business impact against complexity. **A** and **D** both describe low impact, which contradicts the stem. **C** would be right if the requirement were simple, but the stem specifies substantial customisation and specialist development. **B** is the quadrant where additional investment in time and resources can deliver meaningful differentiation and competitive advantage.

**D5.** A gen AI pilot demonstrated strong technical results, but six months later adoption is minimal: staff don't trust the outputs and workflows were never adjusted. What does this most illustrate?

A. Insufficient model capability — a larger foundation model is needed
B. Inadequate infrastructure scaling
C. **Organisational readiness gaps in people and process, not technology**
D. A data quality problem requiring re-ingestion

> **Answer: C.** **A** and **B** both point at technology, and the stem says technical results were strong — nothing indicates capability or scaling limits. **D** would show as poor output quality, but the issue described is *trust and workflow*, not accuracy. **C** matches the course's explicit teaching: readiness rests on **people** (skills, trust, adoption), **process** (workflows, governance) and **technology** — and **technology is only one part; people and processes ultimately determine success.**

**D6.** Which pairing correctly matches a security risk to its primary attack surface?

A. Prompt injection → data sources
B. Data leakage → user input
C. **Model misuse → output**
D. Prompt injection → output

> **Answer: C.** The mapping is fixed: **prompt injection → user input** (external prompts manipulating behaviour), **data leakage → data sources** (where sensitive information is stored, retrieved or accessed), **model misuse → output** (responses used in unintended or harmful ways). **A**, **B** and **D** all cross-wire that mapping. Only **C** is correct.

**D7.** An organisation wants to translate SAIF into concrete tooling. Which pairing is correct?

A. Protect data → IAM and VPC controls
B. Control access → Cloud DLP and Cloud KMS
C. **Monitor and respond → Cloud Monitoring and Security Command Center**
D. Secure models → Dataplex and Dataprep

> **Answer: C.** The four pillars map cleanly: **protect data → Cloud DLP + Cloud KMS**; **secure models → Vertex AI controls + model policies**; **control access → IAM + VPC controls**; **monitor and respond → Cloud Monitoring + Security Command Center**. **A** and **B** swap the first and third pillars' tooling. **D** names data-preparation and cataloguing services that have nothing to do with securing models. **C** is the correct pairing.

**D8.** A bank's loan-decision assistant must satisfy an external auditor. Which combination best supports that requirement?

A. Higher temperature and broader top-P for more nuanced answers
B. **Traceability of inputs and outputs, decision logs, contributing factors and source references**
C. A larger context window and a faster model
D. Removing confidence scores to avoid over-interpretation

> **Answer: B.** **A** increases variability — the opposite of what a regulated decision process needs. **C** improves capability and speed but provides no evidence of how decisions were produced. **D** removes a signal that auditors and reviewers rely on to judge when validation is needed. **B** is exactly what auditors require: traceability into inputs, outputs and decision processes, plus **logs and records as evidence**, with contributing factors and source references explaining *why* a recommendation was produced.

---

## SECTION 8 — Final week checklist

**Seven days out**
- Re-read Sections 3 and 6 (Domain 2 and the product cheat sheet). It is the largest domain on the exam.
- Take the **Pluralsight Practice Exam**: <https://app.pluralsight.com/assessment-pe/google-cloud-generative-ai-leader/intro> — real conditions, score **by domain**.
- Do Google's free official sample questions.

**Three days out**
- Work Section 7 again. For every question you get wrong, write **one line** saying why the right answer is right. That line is worth more than re-watching the module.
- Drill the product cheat sheet as flashcards — product name on one side, "use it when…" on the other.

**Day before**
- Section 1 (exam technique) and the [quick recall sheet](02-quick-recall-sheet.md) only. **No new material.**
- Rest the afternoon.

**The five things to have loaded on exam day**
1. **Changing facts → RAG. Changing behaviour → fine-tuning.**
2. **Agent Assist = live. Conversational Insights = after the fact.**
3. **Model Garden = discover and deploy Google + open-source + third-party together.**
4. **Grounding controls information, not tone.**
5. **Eliminate three, then justify one** — and watch for "manual", "from scratch", "all available data", and any option naming artificial general intelligence.

---

*Built 2026-09-11 from the four "(Generative AI Leader)" Pluralsight courses. Practice questions are original, written in the style of the courses' own example questions; they are not real exam items. Domain weights are approximate — verify against the current official exam guide. Google's product names change; re-check before sitting.*
