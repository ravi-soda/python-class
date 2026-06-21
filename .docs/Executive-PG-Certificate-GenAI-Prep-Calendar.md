# GenAI & Agentic AI — Week-by-Week Prep Calendar

**Program:** Executive PG Certificate, IIT Kharagpur × upGrad  
**Goal:** Be ~1 week ahead of each faculty live session (Saturdays, 9:00 am – 12:00 pm IST)  
**Daily rhythm:** 2 sessions × 90 min = **~3 hrs/day** (catch-up weeks: **3.5–4 hrs**)

| Session | Block | Focus |
|---------|-------|--------|
| **A** | Morning / first block | Learn — video, reading, notes |
| **B** | Evening / second block | Do — code, exercises, flashcards, mini-quiz |

**Weekly:** 6 study days + 1 rest day (default: Wednesday or Sunday evening off).  
**Live Saturdays:** Session A = attend class; Session B = recap notes + 1 practice task.

---

## Phase 0 — Catch-Up (you are here)

Faculty Session 1 (30-May) and Session 2 (06-Jun) have passed. Use this phase to close Foundation Bridge gaps before Module 1 hands-on (20-Jun).

---

### Week 1 · 2 Jun – 8 Jun 2026 · Catch-up + Session 2 week

**Live this week:** Faculty **Session 2** — Transformer Architecture, Attention, Tokenization (6-Jun)

| Day | Session A (Learn) | Session B (Do) |
|-----|-------------------|----------------|
| Mon | Python refresher: variables, loops, functions | ~~Kaggle Learn Python — exercises 1–3~~ |
| Tue | Python: pandas, NumPy basics | Small data wrangling notebook (CSV → summary stats) [click here](https://middcs.github.io/data-science-notes/source/13-data-wrangling.html) |
| Wed | **Rest or light review** | — |
| Thu | ML I: train/test split, regression, accuracy | Kaggle Intro to ML — first 2 lessons [fast.ai course on CNN](https://github.com/fastai/courses/tree/master) |
| Fri | Transformers overview (3Blue1Brown NN + HF Ch 1 skim) | Draw attention diagram; define token, embedding |
| **Sat** | **Attend Session 2 live** | Rewrite notes in your own words; 10 flashcards |
| Sun | Catch Session 1: CNN/RNN/DL essentials (recording or fast.ai L1) | Run a pretrained model via Hugging Face pipeline |

**Hours:** 3.5–4 hrs/day Mon–Fri · 3 hrs Sat · 2 hrs Sun  
**Assess:** Explain “attention” in 3 sentences without notes.

---

### Week 2 · 9 Jun – 15 Jun 2026 · Prep for Session 3

**Live this week:** Faculty **Session 3** — Context Window, Decoding, Metrics (13-Jun)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | ML II: trees, overfitting, cross-validation | Kaggle ML — finish remaining lessons |
| Tue | Deep Learning basics: loss, epochs, backprop (concept) | Train a tiny classifier in scikit-learn |
| Wed | NLP basics: tokenization, BPE, word embeddings | Tokenize text manually; compare token counts |
| Thu | Context window & positional encoding | Read one “Attention Is All You Need” summary blog |
| Fri | Decoding: greedy, beam, temperature, top-p | Generate text with different decoding settings in HF |
| **Sat** | **Attend Session 3 live** | Metrics drill: perplexity, BLEU, ROUGE — define each |
| Sun | Foundation Bridge catch-up: Data Engineering (recording) | Build a simple ETL script (read → clean → save) |

**Hours:** 3.5 hrs/day · **Assess:** Compare greedy vs temperature=0.8 output on same prompt.

---

### Week 3 · 16 Jun – 22 Jun 2026 · Prep for Hands-on + consolidate M1

**Live this week:** **Hands-on** — Sessions 1–3 (20-Jun)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Re-watch Session 1–2 highlights / notes | Implement scaled dot-product attention (numpy or torch) |
| Tue | Context window limits & truncation strategies | Experiment: same prompt at 512 vs 4k context |
| Wed | **Rest** | — |
| Thu | Decoding & sampling deep dive | Log 5 outputs per decoding strategy |
| Fri | Metrics & evaluation for LLMs | Mini-quiz: 20 flashcards from Module 1 |
| **Sat** | **Attend Hands-on live** | Complete any unfinished lab exercises |
| Sun | Fix weak areas from hands-on | Write a 1-page Module 1 summary |

**Hours:** 3 hrs/day · **Assess:** Run end-to-end: tokenize → model → decode → score.

---

## Phase 1 — Module 1: Foundations of GenAI LLMs

---

### Week 4 · 23 Jun – 29 Jun 2026 · Prep for Session 4

**Live:** **Session 4** — Models & APIs: OpenAI, Anthropic, HuggingFace, structured outputs (27-Jun)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | OpenAI API docs: chat completions, models | First API call; log request/response |
| Tue | Anthropic API docs: messages API | Same task via two providers; compare |
| Wed | Hugging Face Inference API & local models | Load `transformers` model; generate text |
| Thu | Structured outputs (JSON mode, schemas) | Return JSON matching a Pydantic schema |
| Fri | API keys, env vars, rate limits, cost basics | Wrap calls in a reusable Python module |
| **Sat** | **Attend Session 4 live** | Build a CLI that calls 2 APIs |
| Sun | Review assignments | Submit / draft assignment if due |

**Assess:** One script, two providers, structured JSON output.

---

### Week 5 · 30 Jun – 6 Jul 2026 · Prep for Session 5

**Live:** **Session 5** — Prompting: zero-shot, few-shot, role-prompting, optimization (4-Jul)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Zero-shot vs few-shot prompting | 10 prompts × 2 styles; score quality 1–5 |
| Tue | Role / system prompts & persona design | Build a “ tutor / critic / editor ” trio |
| Wed | Prompt patterns (chain, template, variables) | Template library in a markdown file |
| Thu | Prompt optimization basics (iterate, evaluate) | A/B test 3 prompt variants on same task |
| Fri | OpenAI / Anthropic prompting guides | One optimized prompt for a real work task |
| **Sat** | **Attend Session 5 live** | Document best prompt from the week |
| Sun | Light review | Rest evening |

**Assess:** Show before/after prompt with measurable improvement.

---

### Week 6 · 7 Jul – 13 Jul 2026 · Prep for Session 6

**Live:** **Session 6** — Prompt security, performance evaluation, budgeting (11-Jul)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Prompt injection & jailbreaks (OWASP LLM Top 10) | Try safe guardrails on a vulnerable prompt |
| Tue | Input/output filtering & moderation APIs | Add pre/post filters to your API wrapper |
| Wed | Latency, throughput, batching | Benchmark 20 calls; record p50/p95 latency |
| Thu | Token counting & cost estimation | Spreadsheet: tokens × price × monthly volume |
| Fri | Evaluation harness design (golden set) | 10 test cases with pass/fail criteria |
| **Sat** | **Attend Session 6 live** | Cost report for one use case |
| Sun | Module 1 assignment work | Peer-style review of your own submission |

**Assess:** Security checklist + cost estimate for 1 app idea.

---

### Week 7 · 14 Jul – 20 Jul 2026 · Module 1 revision

**Live:** **Doubt-clearing** — assignments & grading (18-Jul)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Thu | Revisit weakest Module 1 topics | Redo labs; fix assignment gaps |
| Fri | Prepare 5 questions for doubt-clearing | Mock explain: transformers + prompting |
| **Sat** | **Attend doubt-clearing live** | Note all instructor answers |
| Sun | Module 1 capstone-style mini-project | 1-page write-up |

**Hours:** 3 hrs/day · **Assess:** Can you teach Module 1 to a friend in 15 min?

---

## Phase 2 — Module 2: Advanced Prompting & RAG

---

### Week 8 · 21 Jul – 27 Jul 2026 · Prep for Session 7

**Live:** **Session 7** — Chain-of-Thought, Self-consistency, ReAct (25-Jul)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Chain-of-Thought (CoT) papers & examples | CoT vs direct on 5 math/word problems |
| Tue | Self-consistency sampling | Run n=5 samples; majority vote |
| Wed | ReAct: reasoning + acting loop | Manual ReAct trace on a search task |
| Thu | Tool-use mental model for agents | Pseudocode a ReAct agent |
| Fri | LangChain agents intro (docs) | Minimal ReAct agent in LangChain |
| **Sat** | **Attend Session 7 live** | Log one full ReAct trace |
| Sun | Review | Flashcards |

**Assess:** CoT + self-consistency on one hard reasoning task.

---

### Week 9 · 28 Jul – 3 Aug 2026 · Prep for Session 8

**Live:** **Session 8** — Prompt optimization, security, Verbalized Sampling (1-Aug)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Automatic prompt optimization (APE, DSPy intro) | DSPy or manual opt on one task |
| Tue | Advanced prompt security (indirect injection) | Red-team your Week 6 app |
| Wed | Verbalized sampling & diversity | Compare sampling strategies |
| Thu | Meta-prompting & critique loops | Prompt → critique → revise pipeline |
| Fri | Consolidate Module 2 prompting | 30-min timed quiz |
| **Sat** | **Attend Session 8 live** | Update prompt library |
| Sun | Rest | — |

---

### Week 10 · 4 Aug – 10 Aug 2026 · Prep for Session 9

**Live:** **Session 9** — RAG: motivation, architecture, sparse retrieval (8-Aug)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | RAG architecture (index → retrieve → generate) | Diagram your RAG pipeline |
| Tue | Document chunking strategies | Chunk one PDF 3 ways; compare |
| Wed | Sparse retrieval: BM25, TF-IDF | Build BM25 index with `rank_bm25` |
| Thu | Vector vs sparse — when to use which | Same query on sparse index |
| Fri | LangChain / LlamaIndex RAG quickstart | Minimal RAG on 5 documents |
| **Sat** | **Attend Session 9 live** | Log retrieval hits for 5 queries |
| Sun | Read about hybrid search | Optional prep for Session 10 |

**Assess:** Working sparse RAG on a small doc set.

---

### Week 11 · 11 Aug – 17 Aug 2026 · Prep for Session 10

**Live:** **Session 10** — RAG: Dense Retrieval, Semantic Search (15-Aug)*

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Embeddings: models, dimensions, normalization | Embed 100 sentences; inspect neighbors |
| Tue | Dense retrieval & FAISS / Chroma | Build vector store |
| Wed | Hybrid sparse + dense retrieval | Combine BM25 + embeddings |
| Thu | Re-ranking intro | Add cross-encoder re-ranker |
| Fri | Evaluate retrieval: MRR, recall@k | Measure your RAG retrieval quality |
| **Sat** | **Attend Session 10 live** | Compare sparse vs dense on same queries |
| Sun | Review | *Note: date may shift (public holiday)* |

---

### Week 12 · 18 Aug – 24 Aug 2026 · Prep for Session 11

**Live:** **Session 11** — RAG for Production: query routing, retrieval gateways (22-Aug)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Query routing & intent classification | Route queries to 2 indexes |
| Tue | Retrieval gateways & metadata filters | Filter by date/category in retrieval |
| Wed | Caching embeddings & responses | Add cache layer; measure speedup |
| Thu | Failure modes: hallucination, stale docs | Test adversarial / missing-doc queries |
| Fri | Production RAG checklist | Harden your RAG demo |
| **Sat** | **Attend Session 11 live** | Deployment notes |
| Sun | Assignment / project work | — |

---

### Week 13 · 25 Aug – 31 Aug 2026 · Prep for Session 12

**Live:** **Session 12** — Agentic Orchestration: planners vs executors, context & memory (29-Aug)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Planner vs executor agent patterns | Sketch agent architecture |
| Tue | Short-term vs long-term memory | Add conversation buffer + summary memory |
| Wed | LangGraph basics | State graph with 3 nodes |
| Thu | Multi-step workflows | Planner → retriever → writer chain |
| Fri | Module 2 full review | Mock test: 25 questions |
| **Sat** | **Attend Session 12 live** | Extend graph with one new tool |
| Sun | **Test 1 prep begins** | Review all Module 1–2 notes |

---

### Week 14 · 1 Sep – 7 Sep 2026 · Proctored Test 1 prep

**Live:** **Proctored Test 1** (5-Sep)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Thu | Module 1–2 concept review | Timed practice problems |
| Fri | Weak-topic drill | Full 3-hr mock (self-timed) |
| **Sat** | **Attend Test 1** | Rest |
| Sun | Review mistakes | Update flashcards |

**Hours:** 4 hrs/day Mon–Fri

---

## Phase 3 — Module 3: Fine-Tuning & Alignment

---

### Week 15 · 8 Sep – 14 Sep 2026 · Prep for Session 13

**Live:** **Session 13** — Decision Frameworks, Fine-tuning Approaches, Full Fine-Tuning (12-Sep)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | When to fine-tune vs RAG vs prompt | Decision flowchart for 3 use cases |
| Tue | Full fine-tuning: data, compute, risks | Read HF fine-tuning guide |
| Wed | LoRA theory intro | Identify trainable params in a model |
| Thu | Training loop: loss curves, checkpoints | Run a tiny training script (subset) |
| Fri | GPU / Colab / cloud setup | Verify your training environment |
| **Sat** | **Attend Session 13 live** | Log hyperparameters used in demo |
| Sun | Review Test 1 gaps | — |

---

### Week 16 · 15 Sep – 21 Sep 2026 · Prep for Session 14

**Live:** **Session 14** — Data Preparation & Training Mechanisms (19-Sep)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Dataset formats: instruction, chat, JSONL | Convert 20 examples to chat format |
| Tue | Data cleaning & deduplication | Audit a dataset for quality |
| Thu | Tokenization for training | Inspect token lengths; filter outliers |
| Fri | Training args: lr, batch, epochs, warmup | Document a training config |
| **Sat** | **Attend Session 14 live** | Prepare a 100-row training set |
| Sun | Practice | — |

*Wed: rest*

---

### Week 17 · 22 Sep – 28 Sep 2026 · Prep for Session 15

**Live:** **Session 15** — Additive & Soft Prompting PEFT (26-Sep)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | PEFT overview: adapters, prompts, LoRA | Compare parameter counts |
| Tue | Prompt tuning & soft prompts | HF PEFT soft prompt example |
| Wed | Prefix tuning | Run prefix-tuning demo |
| Thu | When PEFT beats full fine-tune | Case study write-up |
| Fri | Review | Exercises |
| **Sat** | **Attend Session 15 live** | Notes + code snapshot |
| Sun | Light review | — |

---

### Week 18 · 29 Sep – 5 Oct 2026 · Prep for Session 16

**Live:** **Session 16** — Reparameterization-based PEFT (3-Oct)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | LoRA & QLoRA deep dive | LoRA fine-tune small model |
| Tue | IA³, AdaLoRA (survey level) | Compare LoRA ranks (r=4 vs r=16) |
| Wed | Quantization basics (4-bit, 8-bit) | QLoRA training run |
| Thu | Merge adapters & inference | Export merged weights |
| Fri | PEFT evaluation | Before/after benchmark on holdout set |
| **Sat** | **Attend Session 16 live** | Save training artifacts |
| Sun | Rest | — |

---

### Week 19 · 6 Oct – 12 Oct 2026 · Prep for Session 17

**Live:** **Session 17** — LLM Alignment: RLHF, DPO (10-Oct)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Alignment problem & reward hacking | Examples of misaligned outputs |
| Tue | RLHF pipeline: SFT → reward model → PPO | Diagram each stage |
| Wed | DPO vs RLHF | Read DPO paper summary |
| Thu | Preference datasets | Inspect HH/RLHF-style data format |
| Fri | TRL library intro | Run SFT or DPO tutorial |
| **Sat** | **Attend Session 17 live** | Alignment tradeoffs notes |
| Sun | Module 3 review start | — |

---

### Week 20 · 13 Oct – 19 Oct 2026 · Buffer / deep practice (no live session)

**No faculty session this Saturday (17-Oct gap before Session 18)**

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Fri | Re-run weakest PEFT lab | Fine-tune or align a small LM end-to-end |
| Sat | Self-paced project day | Document results |
| Sun | Prepare for Session 18 | Read about SLMs (Phi, Gemma, etc.) |

**Hours:** 3 hrs/day · **Assess:** One fine-tuned model + eval metrics.

---

### Week 21 · 20 Oct – 26 Oct 2026 · Prep for Session 18

**Live:** **Session 18** — Revision & hands-on Small Language Models (24-Oct)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | SLM landscape & use cases | Run a SLM locally (Ollama / HF) |
| Tue | Module 3 concept sprint | Timed revision quiz |
| Wed | Hands-on: full fine-tune workflow review | Repeat pipeline with SLM |
| Thu | Alignment recap | DPO vs RLHF comparison table |
| Fri | Mock practical exam | 3-hr self test |
| **Sat** | **Attend Session 18 live** | Complete lab |
| Sun | Fix gaps | — |

---

### Week 22 · 27 Oct – 2 Nov 2026 · Module 3 wrap-up

**Live:** **Doubt-clearing** (31-Oct)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Thu | Assignment / module 3 gaps | Redo labs |
| Fri | 5 questions for doubt session | Teach-back recording (5 min) |
| **Sat** | **Attend doubt-clearing live** | Update notes |
| Sun | **Module 4 preview:** vision + multimodal intro | Watch VLM overview video |

---

## Phase 4 — Module 4: Multimodal Agentic AI

---

### Week 23 · 3 Nov – 9 Nov 2026 · Prep for Session 19

**Live:** **Session 19** — VLM Architectures (14-Nov)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | CNN + ViT recap | Image embedding exercise |
| Tue | CLIP & contrastive vision-language | Zero-shot image classification with CLIP |
| Wed | LLaVA / GPT-4V style architectures | Run a open VLM demo |
| Thu | Image tokenization & patch embeddings | Compare text vs image tokens |
| Fri | Multimodal encoder-decoder patterns | Diagram VLM stack |
| **Sat** | **Attend Session 19 live** | Screenshot architecture notes |
| Sun | Rest | — |

---

### Week 24 · 10 Nov – 16 Nov 2026 · Prep for Session 20

**Live:** **Session 20** — Applications & Multimodal Prompting (21-Nov)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Image captioning & VQA | Prompt a VLM on 10 images |
| Tue | Multimodal prompt design | System prompts for vision tasks |
| Wed | Document AI (PDFs, charts, tables) | Extract table from image/PDF |
| Thu | Audio/video multimodal (survey) | Optional: Whisper transcription demo |
| Fri | Build multimodal prompt library | 5 task templates |
| **Sat** | **Attend Session 20 live** | Best prompt of the week |
| Sun | Review | — |

---

### Week 25 · 17 Nov – 23 Nov 2026 · Prep for Session 21

**Live:** **Session 21** — Multimodal RAG (28-Nov)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Multimodal embeddings | Index text + images together |
| Tue | Cross-modal retrieval | Query text → retrieve images (or reverse) |
| Wed | ColPali / multimodal indexing (concept) | Hybrid multimodal index |
| Thu | RAG over slides, diagrams, scans | Build multimodal RAG on 10 pages |
| Fri | Evaluate multimodal RAG | Qualitative eval rubric |
| **Sat** | **Attend Session 21 live** | Demo script |
| Sun | Agents preview | Read tool-use overview |

---

### Week 26 · 24 Nov – 30 Nov 2026 · Prep for Session 22

**Live:** **Session 22** — RAG to Assistants and Agents (5-Dec)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Assistants API / agent abstractions | Define tools for an assistant |
| Tue | From RAG pipeline to agent loop | RAG + memory + tools sketch |
| Wed | OpenAI Assistants / custom agent | Build minimal assistant |
| Thu | State management in agents | Persist conversation + retrieved docs |
| Fri | Error handling in agent loops | Test failure recovery |
| **Sat** | **Attend Session 22 live** | Agent architecture doc |
| Sun | LangChain agents review | — |

---

### Week 27 · 1 Dec – 7 Dec 2026 · Prep for Session 23

**Live:** **Session 23** — Tool Use & Function Calling (12-Dec)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Function calling schema design | 3 tools: search, calc, weather (mock) |
| Tue | Parallel vs sequential tool calls | Agent that chains tools |
| Wed | Validation & sandboxing tools | Reject unsafe tool args |
| Thu | MCP intro (preview for Module 5) | Read MCP spec overview |
| Fri | Integrate tools into your RAG agent | Working tool-calling agent |
| **Sat** | **Attend Session 23 live** | Log tool traces |
| Sun | LangGraph prep | Tutorial L1 |

---

### Week 28 · 8 Dec – 14 Dec 2026 · Prep for Session 24

**Live:** **Session 24** — LangChain & LangGraph (19-Dec)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | LangGraph: nodes, edges, state | 3-node graph |
| Tue | Conditional routing & cycles | Router node by intent |
| Wed | Human-in-the-loop patterns | Approval step in graph |
| Thu | Persistence & checkpoints | Save/restore graph state |
| Fri | Module 4 review | Mock test |
| **Sat** | **Attend Session 24 live** | Production-ready graph |
| Sun | **Test 2 prep** | Review Modules 3–4 |

---

### Week 29 · 15 Dec – 21 Dec 2026 · Test 2 prep

**Live:** **Proctored Test 2** (26-Dec)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Thu | Module 3–4 review | Timed problems + labs |
| Fri | Full mock exam | Fix weak areas |
| **Sat** | **Attend Test 2** | Rest |
| Sun | Celebrate / light review | Plan capstone |

**Hours:** 4 hrs/day Mon–Fri

---

## Phase 5 — Module 5: Deployment & Capstone

---

### Week 30 · 22 Dec – 28 Dec 2026 · Holiday buffer + Session 25 prep

**Live:** **Session 25** — REST APIs with FastAPI; Real-time vs Batch Inference (2-Jan-27)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Wed | Rest / catch breath (1 hr light review only) | — |
| Thu | FastAPI fundamentals | Hello World API |
| Fri | Sync vs async inference; batch endpoints | `/predict` endpoint wrapping your model |
| **Sat** | **Attend Session 25 live** *(2-Jan)* | Dockerize API (intro) |
| Sun | Capstone ideation | 3 problem statements |

*Note: Week spans Dec 22–28; Session 25 is Jan 2 — use Dec 29–Jan 1 for extra FastAPI practice.*

---

### Week 31 · 29 Dec 2026 – 4 Jan 2027 · Prep for Session 26

**Live:** **Session 26** — Model Context Protocol & Orchestration Frameworks (9-Jan-27)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | FastAPI deployment patterns | Deploy locally with uvicorn |
| Tue | Batch vs streaming responses | SSE streaming endpoint |
| Wed | MCP architecture & servers | Run sample MCP server |
| Thu | MCP clients & tool exposure | Connect agent to MCP tool |
| Fri | Orchestration comparison (LangGraph, CrewAI survey) | Pick stack for capstone |
| **Sat** | **Attend Session 26 live** | MCP integration notes |
| Sun | Capstone outline v1 | — |

---

### Week 32 · 5 Jan – 11 Jan 2027 · Prep for Session 27

**Live:** **Session 27** — Responsible & Trusted AI Essentials (16-Jan-27)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Bias, fairness, toxicity in LLMs | Test model on bias prompts |
| Tue | Privacy & PII handling | Redact PII pipeline |
| Wed | Explainability & transparency | Document model limitations |
| Thu | Governance, audit trails, logging | Add logging to your API |
| Fri | Regulatory landscape (EU AI Act survey) | Risk checklist for capstone |
| **Sat** | **Attend Session 27 live** | Ethics section for capstone doc |
| Sun | Capstone build sprint | — |

---

### Week 33 · 12 Jan – 18 Jan 2027 · Prep for Session 28

**Live:** **Session 28** — Public Case Studies & Pitfalls (23-Jan-27)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon | Case study: successful GenAI deployment | Write lessons learned |
| Tue | Case study: failures (hallucination, cost blowout) | Failure mode matrix |
| Wed | Production pitfalls checklist | Apply to your capstone |
| Thu | Monitoring & observability (LangSmith / custom) | Add basic metrics |
| Fri | Capstone progress review | MVP demo |
| **Sat** | **Attend Session 28 live** | Update pitch deck |
| Sun | Build sprint | — |

---

### Week 34 · 19 Jan – 25 Jan 2027 · Prep for Session 29

**Live:** **Session 29** — Capstone Feedback (30-Jan-27)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Wed | Capstone implementation | Core features complete |
| Thu | Prepare demo script & slides | Rehearse 10-min pitch |
| Fri | Anticipate reviewer questions | Q&A doc |
| **Sat** | **Attend Session 29 live** | Capture all feedback |
| Sun | Implement feedback | — |

**Hours:** 3–4 hrs/day + extra build time as needed

---

### Week 35 · 26 Jan – 1 Feb 2027 · Capstone final prep

**Live:** **Session 30** — Evaluation of Capstone Challenge (6-Feb-27)

| Day | Session A | Session B |
|-----|-----------|-----------|
| Mon–Thu | Final capstone polish | End-to-end testing |
| Fri | Full dress rehearsal | Record demo video |
| **Sat** | **Attend Session 30 — Capstone Evaluation** | Rest |
| Sun | Reflect & archive project | GitHub README + demo link |

**Top 10 teams:** Present at IIT Kharagpur — prep travel/presentation if selected.

---

## Quick reference — Faculty session dates

| # | Date | Topic |
|---|------|-------|
| 1 | 30-May-26 | AI & Deep Learning Essentials |
| 2 | 06-Jun-26 | Transformer Architecture |
| 3 | 13-Jun-26 | Context Window, Decoding, Metrics |
| — | 20-Jun-26 | Hands-on (Sessions 1–3) |
| 4 | 27-Jun-26 | Models & APIs |
| 5 | 04-Jul-26 | Prompting |
| 6 | 11-Jul-26 | Prompt Security & Budgeting |
| — | 18-Jul-26 | Doubt-clearing |
| 7 | 25-Jul-26 | Advanced Prompting (CoT, ReAct) |
| 8 | 01-Aug-26 | Advanced Prompting II |
| 9 | 08-Aug-26 | RAG: Sparse Retrieval |
| 10 | 15-Aug-26 | RAG: Dense Retrieval |
| 11 | 22-Aug-26 | RAG for Production |
| 12 | 29-Aug-26 | Agentic Orchestration |
| — | 05-Sep-26 | **Proctored Test 1** |
| 13 | 12-Sep-26 | Fine-tuning Frameworks |
| 14 | 19-Sep-26 | Data Prep for Finetuning |
| 15 | 26-Sep-26 | Additive / Soft PEFT |
| 16 | 03-Oct-26 | Reparameterization PEFT |
| 17 | 10-Oct-26 | RLHF, DPO |
| 18 | 24-Oct-26 | SLM Revision & Hands-on |
| — | 31-Oct-26 | Doubt-clearing |
| 19 | 14-Nov-26 | VLM Architectures |
| 20 | 21-Nov-26 | Multimodal Prompting |
| 21 | 28-Nov-26 | Multimodal RAG |
| 22 | 05-Dec-26 | RAG → Agents |
| 23 | 12-Dec-26 | Tool Use & Function Calling |
| 24 | 19-Dec-26 | LangChain & LangGraph |
| — | 26-Dec-26 | **Proctored Test 2** |
| 25 | 02-Jan-27 | FastAPI & Inference |
| 26 | 09-Jan-27 | MCP & Orchestration |
| 27 | 16-Jan-27 | Responsible AI |
| 28 | 23-Jan-27 | Case Studies & Pitfalls |
| 29 | 30-Jan-27 | Capstone Feedback |
| 30 | 06-Feb-27 | Capstone Evaluation |

---

## Practice resources (use all year)

| Area | Resource |
|------|----------|
| Python | [Kaggle Learn – Python](https://www.kaggle.com/learn/python) |
| ML | [Kaggle Learn – Intro to ML](https://www.kaggle.com/learn/intro-to-machine-learning) |
| Math / DL intuition | [3Blue1Brown](https://www.3blue1brown.com/) |
| Deep Learning | [fast.ai](https://course.fast.ai/) (Lessons 1–4) |
| Transformers / NLP | [Hugging Face NLP Course](https://huggingface.co/learn/nlp-course) |
| Fine-tuning | [Hugging Face PEFT / TRL docs](https://huggingface.co/docs) |
| RAG / Agents | [LangChain tutorials](https://python.langchain.com/docs/tutorials/) |
| API practice | OpenAI, Anthropic, HF Inference docs + playground |
| Self-assessment | Anki flashcards · weekly 30-min quiz · teach-back (3 min aloud) |

---

## Weekly success checklist

- [ ] Completed 12 sessions (2 × 6 days)?
- [ ] Built or ran code in every Session B?
- [ ] Added ≥10 flashcards this week?
- [ ] Can explain next Saturday’s topic in 3 minutes without notes?
- [ ] Logged blockers for doubt-clearing / office hours?

*Dates marked tentative per official schedule — adjust if IIT KGP announces changes.*
