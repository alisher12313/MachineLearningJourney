# NLP / LLM Engineer Roadmap — 16 weeks

**Start:** Mon 19 Oct 2026 · **Finish:** ~7 Feb 2027 · **Budget:** 3–4 h/day
New Year falls in weeks 11–12, so expect to lose a few days there.

**Goal:** get hired as a junior/middle NLP/LLM engineer.
**Rule:** one project that grows every week. Each week ends with something committed.

---

## Where I am now

| Status | Area |
|---|---|
| ✅ | Classical ML (IBM): regression, KNN, SVM, trees, random forest, AdaBoost, cross-validation |
| ✅ | Deep learning basics (Andrew Ng), PyTorch, CS224N assignment 1 |
| ✅ | HF course ch 1–7: fine-tuning, Trainer + manual loop + Accelerate, NER, MLM, translation, summarization, causal LM from scratch, semantic search |
| ⏳ | HF ch 7 **question answering** (not done yet) |
| ⏳ | HF ch 11 chat templates / SFT (in progress; finish and park it) |
| ❌ | Engineering: FastAPI, Docker, SQL, tests, CI |
| ❌ | LLM APIs, RAG, evaluation, agents, MLOps |

---

## Weekly rhythm

| Day | What |
|---|---|
| Mon–Fri | ~1 h learning (course, docs, ML theory) + ~2 h building the project. LeetCode 30–45 min on 3 of these days |
| Sat | **Karpathy session**: video + code along (see the track below) |
| Sun | Off, or catch up. Commit and write a short note on what you learned |

---

## The project: document assistant for Russian & Kazakh

One repo that grows through all four phases:

> Upload documents → hybrid search → answers with citations → entity extraction (NER) → an agent with tools → evaluated, traced and deployed.

Pick a public corpus you can explain in an interview, for example Kazakhstan laws, university regulations, or Wikipedia articles in ru/kk.

---

## Phase 1 (weeks 1–4): close the gaps and build the skeleton

**Week 1**
- [ ] Finish the current ch 11 SFT exercise (SmolLM2 on `everyday-conversations`), commit it, then **park ch 11–12**
- [ ] HF ch 7: **question answering** (exact match / F1)
- [ ] Python: OOP (classes, dataclasses, ABCs), type hints, `src/` layout, `uv`, `ruff`

**Week 2**
- [ ] pytest: fixtures, `parametrize`, mocking an external API
- [ ] FastAPI + Pydantic v2: routes, validation, dependency injection, async basics
- [ ] Project: new repo, `/health`, `/documents` upload, first tests

**Week 3**
- [ ] Docker + docker-compose
- [ ] PostgreSQL + SQLAlchemy 2 + Alembic migrations
- [ ] SQL: joins, `GROUP BY`, window functions (`ROW_NUMBER`, `RANK`, `LAG`). Start LeetCode "SQL 50"
- [ ] Project: documents stored in Postgres; `docker compose up` runs the API and DB

**Week 4**
- [ ] LLM API: system prompts, **structured output** (Pydantic), **streaming**
- [ ] GitHub Actions: `ruff` + `pytest` on every push
- [ ] Project: `/summarize` returns structured JSON; `/chat` streams

**Done when:** `docker compose up` gives a working API + DB, CI is green, and the LLM endpoints have tests (with the LLM mocked).

---

## Phase 2 (weeks 5–8): search, RAG, evaluation

**Week 5**
- [ ] Embeddings with `sentence-transformers`: compare `bge-m3` and `multilingual-e5` on ru/kk
- [ ] Chunking strategies: fixed size, recursive, by heading
- [ ] Project: ingestion pipeline (parse → chunk → embed → store)

**Week 6**
- [ ] pgvector + an HNSW index → `/search`
- [ ] Keyword search (Postgres full-text or BM25)
- [ ] Hybrid search with Reciprocal Rank Fusion

**Week 7**
- [ ] Reranker: `bge-reranker-v2-m3`
- [ ] Project: `/ask` = retrieve → rerank → prompt → answer **with citations**, written **without** LangChain or LlamaIndex

**Week 8**
- [ ] Test set: 50–100 questions with their correct chunks (write some by hand, generate some with an LLM and check them)
- [ ] Retrieval metrics: recall@k, MRR
- [ ] Answer metrics: LLM-as-judge, RAGAS (faithfulness, answer relevancy)
- [ ] Comparison table: vector vs hybrid vs hybrid + rerank, Russian vs Kazakh

**Done when:** the README has the comparison table and one command reproduces it.

---

## Phase 3 (weeks 9–12): NER, MLOps, agent, first deploy

**Week 9**
- [ ] Fine-tune a NER model for ru/kk with the HF Trainer (you did NER in ch 7; now do it on your languages)
- [ ] **MLflow**: log parameters, seqeval F1 and artifacts; compare runs; register the best model

**Week 10**
- [ ] Project: FastAPI loads the NER model **from the MLflow registry**
- [ ] Extract entities on upload, store them in Postgres, filter search by entity

**Week 11**
- [ ] Agent: write the tool-calling loop by hand first, then rebuild it in **LangGraph**
- [ ] Tools: `search_docs`, `extract_entities`, `sql_query` (read-only DB user!)
- [ ] State, conversation memory, a step limit

**Week 12**
- [ ] **MCP** server exposing the same tools
- [ ] **Deploy v1**: VPS + docker compose + Caddy (HTTPS)
- [ ] 📨 **Start applying** with the live link

**Done when:** there's a live URL, the agent answers a multi-step question, and MLflow shows at least 5 compared runs.

---

## Phase 4 (weeks 13–16): production quality and interviews

**Week 13**
- [ ] **Langfuse**: trace every LLM and tool call (latency, tokens, cost); version your prompts

**Week 14**
- [ ] Prompt injection: put malicious instructions inside test documents and make sure the agent ignores them
- [ ] Guardrails: input/output validation, a tool allow-list
- [ ] Evaluation in CI as a regression gate (fail the build if recall@5 drops)

**Week 15**
- [ ] Gradient boosting: how it works; CatBoost on one tabular dataset (builds on your AdaBoost and random forest work)
- [ ] README: architecture diagram, metrics, decisions and trade-offs, demo GIF

**Week 16**
- [ ] Interview prep: ML theory review, NLP/LLM questions (attention, BPE, RAG failure modes), RAG system design, a mock interview
- [ ] Keep applying

---

## Karpathy track (Saturdays)

| Week | Video | Why now |
|---|---|---|
| 1–2 | The spelled-out intro to neural networks and backpropagation: building micrograd | Backprop, a classic interview topic |
| 3 | The spelled-out intro to language modeling: building makemore | Negative log-likelihood loss, sampling |
| 4 | Building makemore Part 2: MLP | Train/val/test, overfitting (matches the ML theory track) |
| 5 | Building makemore Part 3: Activations & Gradients, BatchNorm | Training stability (skip if behind) |
| 6–7 | Let's build GPT: from scratch, in code, spelled out | Attention from scratch, alongside the embeddings work |
| 8 | Catch-up | |
| 9–10 | Let's build the GPT Tokenizer | BPE (a 🔴 topic), and the subword alignment you hit in NER |
| 11–12 | Deep Dive into LLMs like ChatGPT | Pretraining → SFT → RL; ties together HF ch 11–12; a good interview overview |
| 13–16 | Free: interview prep, or the optional videos below | |

**Optional (research, or after the job):** makemore Part 4 (Becoming a Backprop Ninja), Part 5 (Building a WaveNet), Let's reproduce GPT-2 (124M) (needs a GPU).

If your research needs model internals sooner, swap the optional videos in. The job track stays the same.

---

## ML theory track (one session a week, Mon–Fri)

You've covered most of this in the IBM and Andrew Ng courses. This is review, so you can explain it clearly in interviews.

| Weeks | Topics |
|---|---|
| 1–4 | Bias/variance, overfitting, train/val/test, cross-validation |
| 5–8 | Precision/recall/F1, ROC-AUC, PR-AUC; ranking metrics (recall@k, MRR, nDCG), which you use in Phase 2 |
| 9–12 | Regularization (L1/L2, dropout, early stopping), optimizers (SGD, Adam), learning-rate schedules |
| 13–16 | Trees and boosting; review everything by explaining it out loud |

---

## LeetCode

3–5 problems a week, following the NeetCode 150 order (arrays & hashing → two pointers → sliding window → stack → binary search → linked lists → trees → graphs → basic DP). Do LeetCode "SQL 50" in weeks 3–6.

---

## Not now (after the job, or if research needs it)

HF ch 11 beyond the current exercise, HF ch 12 (GRPO), LoRA/QLoRA, DPO, vLLM, quantization, Kubernetes, deeper computer vision, reproducing GPT-2.

---

## Stack reference

| Layer | Pick |
|---|---|
| Python tooling | `uv`, `ruff`, `pytest`, type hints, `pre-commit` |
| API | FastAPI + Pydantic v2 |
| Database | PostgreSQL + SQLAlchemy 2 + Alembic |
| Vector search | pgvector (Qdrant as the alternative) |
| Embeddings | `bge-m3` / `multilingual-e5` via `sentence-transformers` |
| Keyword search | Postgres full-text search or BM25 |
| Reranker | `bge-reranker-v2-m3` |
| LLM | Any OpenAI-compatible API, or Ollama locally |
| NER | HF `transformers` token classification + `seqeval` |
| Agents | LangGraph + MCP Python SDK |
| Evaluation | Own recall@k / MRR scripts, RAGAS, LLM-as-judge |
| Experiment tracking | MLflow |
| LLM observability | Langfuse |
| Infrastructure | Docker, docker-compose, GitHub Actions, VPS + Caddy |
| Demo UI (optional) | Streamlit or Gradio |
