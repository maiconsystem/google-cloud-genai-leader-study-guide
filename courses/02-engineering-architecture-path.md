# Generative AI: Engineering and Architecture — the path you do *not* need

**Pluralsight · 9 courses · ~15h18m**

I completed this path before deciding to sit the Generative AI Leader exam. It is excellent material and it is **the wrong altitude for this certification**. It is here so you can make an informed decision instead of repeating my sequencing.

---

## The honest assessment

| Exam domain | Does this path cover it? |
|---|---|
| 1. Fundamentals of gen AI (~30%) | ✅ **Yes, well** |
| 2. Google Cloud's gen AI offerings (~35%) | ❌ **No. Zero.** It is vendor-neutral. The biggest domain gets nothing |
| 3. Techniques to improve model output (~20%) | ✅ **Yes, very well** — its strongest area |
| 4. Business strategies (~15%) | 🟡 **Partly** — governance and risk yes; ROI, adoption and change management no |

**Net:** roughly half the exam, none of the half that people actually fail on. **Take it after you pass**, when the value is interview preparation rather than exam preparation.

What the exam *does* want from this material is distilled in [the quick recall sheet](../study-guide/02-quick-recall-sheet.md) — the exam-relevant subset with the engineering internals cut out.

---

## The nine courses

| # | Course | Modules |
|---|---|---|
| 1 | **GenAI System Architecture Overview** (1h45m) | Core system components · architectural patterns and trade-offs · scaling and optimising performance · designing APIs for gen AI · documenting architecture decisions |
| 2 | **GenAI Data and Knowledge Layer** (1h56m) | Embeddings and vector store fundamentals · vector database architecture and operations · knowledge graphs and structured knowledge · production pipelines, advanced preprocessing and synthetic data |
| 3 | **GenAI Retrieval and Memory Patterns** (1h12m) | Building scalable RAG architectures · optimising and scaling RAG for enterprise · context and memory management · caching, optimisation and performance monitoring |
| 4 | **GenAI Model Access Layer and Structured Outputs** (1h56m) | Production API patterns · structuring and validating output · advanced prompting for production · **function-calling architectures** · multimodal pipelines · fine-tuning and customisation · output quality and reliability |
| 5 | **GenAI Orchestration and Agent Patterns** (1h51m) | Multi-step reasoning and planning · multi-agent architectures and collaboration · tool integration and chaining · error handling and recovery · orchestration best practices |
| 6 | **GenAI Inference and Serving Architecture** (1h56m) | Model inference and efficient model selection · batching and throughput · GPU scaling and infrastructure · cost engineering · advanced inference techniques |
| 7 | **LLMOps: Evaluation, Observability, and Quality** (1h58m) | Evaluation metrics and frameworks · observability and logging · automated testing strategies · **drift detection and model monitoring** |
| 8 | **Reliability, SLOs, and Incident Management for GenAI Systems** (1h21m) | SLIs, SLOs and SLAs for gen AI services · production reliability fundamentals · incident management |
| 9 | **Platform and Governance for GenAI Systems** (1h23m) | Deployment frameworks and platform architecture · multi-tenant architecture · **enterprise governance and compliance** · auditability and transparency · regulatory landscape and future-proofing |

*(A tenth course, "Safety and Security Architecture for GenAI Systems", was unpublished when I took the path.)*

---

## What it gives you that the exam *does* reward

Four things transfer directly, and they transfer as **depth of understanding rather than recall** — which is exactly what makes scenario questions easy:

1. **Course 3 (RAG).** Retrieval, augmentation, generation as a real pipeline — chunking, embedding, ranking, caching. After this, every RAG-versus-fine-tuning question is obvious.
2. **Course 4 (function calling).** The mechanical detail that the model **emits a structured request and your code executes it** is examined directly, and the exam's most common misconception is that the model executes the call itself.
3. **Course 7 (drift and monitoring).** Drift, evaluation metrics and hallucination rates as production concerns, not definitions.
4. **Course 9 (governance).** Auditability, transparency, multi-tenancy and the regulatory landscape — the substance behind Domain 4's responsible-AI questions.

## What it gives you that the exam actively punishes

The habit of reaching for the **technically maximal** answer. This is a leadership exam: it rewards the managed service over the hand-built pipeline, and the change-management answer over the infrastructure answer. Nine hours of architecture training pushes you the other way. See [common mistakes, Pattern 3](../practice/03-common-mistakes.md).

Everything in this path about HNSW and IVF index internals, GPU memory hierarchy, VRAM arithmetic, vLLM and TensorRT-LLM, circuit breakers, Kubernetes quotas, Airflow DAGs, PromQL burn-rate alerting and LoRA mechanics is **not on this exam**. Not a single question.

---

## Verdict

**Before the exam:** skip it. If you have already done it, read [the quick recall sheet](../study-guide/02-quick-recall-sheet.md) to extract the exam-relevant half and consciously drop the rest.

**After the exam:** worth every hour, for a different purpose. This is the material that makes you credible in a technical interview, and it pairs naturally with the leadership framing the certification gives you.
