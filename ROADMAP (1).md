# NLP / LLM Engineer Roadmap: linear, based on real vacancies

**Start:** Mon 19 Oct 2026 · **Pace:** 3–4 h/day, 6 days/week · **Length:** ~81 working days, about 16 weeks with buffer

**How to use it:** do the steps in order. Each step uses what the previous ones built, so don't start a step until the previous step's "Done when" is true.

**The only habit outside the sequence:** 30 minutes of LeetCode a day (SQL 50 during step 4, then [NeetCode 150](https://neetcode.io/roadmap)).

**Optional companion book:** Chip Huyen, *AI Engineering* (O'Reilly, 2025). It covers most of this roadmap: prompting (ch 5) for step 6, evaluation (ch 3–4) for steps 8 and 10, RAG and agents (ch 6) for steps 7–13, fine-tuning (ch 7) for step 16, inference optimization (ch 9) for step 17, architecture (ch 10) for step 18.

---

## 1. What employers ask for (October 2026 snapshot)

These are 12 postings I could read in detail: 9 in Kazakhstan and 3 in Russia. Some are archived, but they still show what employers ask for, which is what a learning plan needs.

| # | Company | Role | Experience | Stack named in the posting |
|---|---|---|---|---|
| 1 | Dreamlab Technologies (Astana) | ML Engineer (NLP / RAG), 400–800k ₸ | 1–3 y | Python, RAG, LangGraph, MCP, vector DBs, prompting, async FastAPI, vLLM, LoRA, quantization |
| 2 | Globerce (Almaty) | AI / LLM Engineer | 3–6 y | Python, PyTorch, HF Transformers, LangChain/LangGraph, RAG (chunking, embeddings, reranking), vector DBs, CoT / few-shot / ReAct prompting |
| 3 | Globerce (Almaty) | AI Engineer, Freedom Business | 1–3 y | RAG, hallucination control, tool/function calling, backend |
| 4 | Documentolog (Astana) | Middle ML Engineer (NLP), 500–800k ₸ | 1–3 y | NLP training and evaluation, prompting, fine-tuning, LLM evaluation, clean testable Python, SQL, Git, Docker, CI/CD, model-serving API |
| 5 | Kaspi.kz (Almaty) | NLP / ML Engineer | middle | Transformers in production (BERT, Sentence-BERT, T5), SQL, CI/CD (GitLab, Docker, Kubernetes), quality monitoring |
| 6 | Bank CenterCredit (Almaty) | Voice AI / NLP / LLM Engineer | 1–3 y | Python, FastAPI, asyncio, WebSocket, ASR/TTS, LoRA/PEFT, RabbitMQ/Kafka/Redis |
| 7 | Halyk Finance | AI Engineer | 2+ y | Python, SQL, LLMs via API |
| 8 | AML Academy (Astana) | ML Engineer | — | NLP, PyTorch, Hugging Face, Qdrant / Milvus / FAISS |
| 9 | Progressive Mind (Astana) | NLP Engineer (chatbot), $4–6k | 6+ y | Fine-tuning, LoRA, RAG, SFT, RLHF/GRPO |
| 10 | Sber (Moscow) | AI Agent Engineer | 3–6 y | Python, LangChain/LangGraph, RAG, FastAPI/Flask, PostgreSQL, CI/CD, Kubernetes, PyTorch/HF |
| 11 | M-TECH (Russia, remote) | Python / LLM Engineer: RAG & agents | Python 2–3 y, LLM 6 mo | Python, LangChain or LangGraph, RAG, Docker, REST, CI/CD, Git |
| 12 | Sber (Moscow) | LLM Engineer (RecSys) | 2–3 y | Python, PySpark, PyTorch, LangChain, LangGraph, Airflow, MLflow, Kubernetes, Kafka, FastAPI |

### How often each skill appears (out of 12)

| Skill | Postings | Priority |
|---|---|---|
| Python | 12 | 🔴 |
| RAG / vector search | 7 | 🔴 |
| Agents: LangGraph / LangChain / tool calling | 6 | 🔴 |
| FastAPI / model-serving API | 6 | 🔴 |
| PyTorch + Hugging Face Transformers | 6 | 🔴 (you have this) |
| LLM integration and prompting | 5 | 🔴 |
| SQL / PostgreSQL | 4 | 🔴 (every backend needs it) |
| Docker, CI/CD, Git | 4 | 🔴 (every backend needs it) |
| Evaluation / answer quality / hallucination control | 4 | 🔴 (it's what makes a portfolio project credible) |
| Fine-tuning with LoRA / PEFT | 4 | 🟡 |
| Kubernetes | 3 | 🟢 (large companies, mid+ roles) |
| Async Python | 2 | 🟡 (needed for streaming anyway) |
| Message queues (Kafka, RabbitMQ, Redis) | 2 | 🟢 |
| MCP | 1 | 🟡 (cheap to add on top of agents) |
| vLLM / quantization | 1 | 🟡 |
| MLflow / Airflow | 1 | 🟢 |
| Voice (ASR / TTS) | 1 | 🟢 |
| RLHF / GRPO (HF ch 12) | 1 (a 6+ year role) | 🟢 |
| Extractive QA (HF ch 7) | 0 | skip |
| Gradient boosting / CatBoost | 0 | interview review only |

### What this means

- True junior NLP roles are rare in Kazakhstan; most postings ask for 1–3 years. Your project has to look like production work: tests, CI, Docker, metrics.
- Many "LLM Engineer" postings are really applied AI engineering: building RAG and agents into a product. Apply to "AI Engineer" and "Python developer (LLM)" titles too.
- Pay for the 1–3-year roles above: 400–800k ₸.

---

## 2. The project: document assistant for Russian & Kazakh

One repo that grows through every step from step 2 on:

> Upload documents → hybrid search → answers with citations → an agent with tools → entity extraction → a fine-tuned model, all evaluated, traced and deployed.

Pick a public corpus you can explain in an interview, for example Kazakhstan laws, university regulations, or Wikipedia articles in ru/kk.

---

## 3. The steps

### Step 0: Close out Hugging Face (2 days)
- [ ] Finish the ch 11 SFT exercise and commit it. The rest of ch 11 (LoRA) comes back in step 16.
- **Skip ch 12 (GRPO).** One of 12 postings asks for it, and that one wants 6+ years. Karpathy's "Deep Dive" in step 1 covers the RL idea well enough for interviews.
- HF ch 7 question answering is dropped: none of the 12 postings asks for it.

### Step 1: Karpathy block (8 days)
Code along in your own notebooks and commit them to a `karpathy/` folder. All videos are linked from [karpathy.ai/zero-to-hero](https://karpathy.ai/zero-to-hero.html) and [his YouTube channel](https://www.youtube.com/@AndrejKarpathy).

| Days | Video | What you get from it |
|---|---|---|
| 2 | The spelled-out intro to neural networks and backpropagation: building micrograd | Backprop from scratch; a classic interview question |
| 1 | The spelled-out intro to language modeling: building makemore | Language modeling, negative log-likelihood, sampling |
| 1 | Building makemore Part 2: MLP | Embeddings, train/val/test, overfitting |
| 2 | Let's build GPT: from scratch, in code, spelled out | Attention and the transformer, which you'll use from step 7 on |
| 1.5 | Let's build the GPT Tokenizer | BPE; explains the subword alignment you'll handle in NER (step 15) |
| 0.5 | Deep Dive into LLMs like ChatGPT (watch only) | Pretraining → SFT → RL; context for everything after |

- **Done when:** you can explain backprop, attention and BPE without notes.

### Part A: Engineering refresh (you've used these before)

Don't redo beginner tutorials. Build the step, and open the docs only where you get stuck.

### Step 2: Production Python (3 days)
- **Learn:** OOP (classes, dataclasses, ABCs), type hints, `uv`, `ruff`, `src/` layout, pytest (asserts, fixtures, `parametrize`)
- **Build:** new repo; a `Document` dataclass; a `DocumentStore` abstract class with an in-memory implementation; tests
- **Learn from:** [ArjanCodes](https://www.youtube.com/@ArjanCodes) (videos on dataclasses, abstract classes, dependency injection), [uv docs](https://docs.astral.sh/uv/), [ruff docs](https://docs.astral.sh/ruff/), [pytest: Get started](https://docs.pytest.org/en/stable/getting-started.html) and its fixtures guide
- **Done when:** `uv run pytest` passes and `ruff check` is clean

### Step 3: FastAPI + CI (2 days)
- **Learn:** FastAPI, Pydantic v2 models and validation, dependency injection, `TestClient`, GitHub Actions
- **Build:** `/health`, upload / list / get documents using the store from step 2 (injected, not created inside the routes); CI runs `ruff` + `pytest` on every push
- **Learn from:** [FastAPI tutorial](https://fastapi.tiangolo.com/tutorial/) (skim to "Dependencies" and "Testing"), the "Building and testing Python" guide in the [GitHub Actions docs](https://docs.github.com/en/actions). Reference project: [Full Stack FastAPI Template](https://github.com/fastapi/full-stack-fastapi-template)
- **Done when:** CI is green on GitHub

### Step 4: SQL and PostgreSQL (3 days)
- **Learn:** joins, `GROUP BY`, window functions (`ROW_NUMBER`, `RANK`, `LAG`); SQLAlchemy 2 (its syntax changed from 1.x); Alembic migrations. Start LeetCode SQL 50
- **Build:** a `PostgresDocumentStore` implementing the same abstract class. Only the injected dependency changes; the API code stays the same
- **Learn from:** [SQLBolt](https://sqlbolt.com/) (quick refresh), [PostgreSQL window functions tutorial](https://www.postgresql.org/docs/current/tutorial-window.html), [PostgreSQL Exercises](https://pgexercises.com/), [LeetCode SQL 50](https://leetcode.com/studyplan/top-sql-50/), [SQLAlchemy Unified Tutorial](https://docs.sqlalchemy.org/en/20/tutorial/), [Alembic tutorial](https://alembic.sqlalchemy.org/en/latest/tutorial.html)
- **Done when:** the API tests pass against Postgres

### Step 5: Docker (2 days)
- **Learn:** Dockerfile, multi-stage builds, docker-compose, service containers in CI
- **Build:** `docker compose up` runs the API + Postgres; CI runs tests against a Postgres container
- **Learn from:** [Docker's Python guide](https://docs.docker.com/guides/python/), the compose file and workflows in the Full Stack FastAPI Template
- **Done when:** a fresh clone runs with one command

### Step 6: Async + LLM APIs (5 days)
- **Learn:** `async` / `await`, `httpx`; an OpenAI-compatible LLM API; prompting (system prompts, few-shot, chain-of-thought); structured output with Pydantic; streaming; mocking in pytest
- **Build:** `/summarize` returns validated JSON; `/chat` streams; tests replace the LLM client with a fake
- **Learn from:** [Real Python: Async IO walkthrough](https://realpython.com/async-io-python/), [FastAPI: concurrency and async](https://fastapi.tiangolo.com/async/), DeepLearning.AI's free [ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/), OpenAI docs on [Structured Outputs](https://platform.openai.com/docs/guides/structured-outputs) and streaming. For one API key with many models, [OpenRouter](https://openrouter.ai) is OpenAI-compatible
- **Done when:** CI passes without an API key

### Part B: Retrieval and RAG

### Step 7: Embeddings and vector search (5 days)
- **Learn:** `sentence-transformers`; compare `bge-m3` and `multilingual-e5` on ru/kk; chunking (fixed size, recursive, by heading); Qdrant
- **Build:** ingestion (parse → chunk → embed → store in Qdrant, added to docker-compose); `/search`
- **Learn from:** [sentence-transformers docs](https://sbert.net) (semantic search), [MTEB leaderboard](https://huggingface.co/spaces/mteb/leaderboard) (to pick models), [Pinecone: chunking strategies](https://www.pinecone.io/learn/chunking-strategies/), [Qdrant docs](https://qdrant.tech/documentation/), your own HF ch 5 semantic search notebook
- **Done when:** searching in Russian and Kazakh returns sensible chunks

### Step 8: Measure retrieval (4 days)
- **Learn:** building a test set; recall@k, MRR
- **Build:** 50–100 questions with their correct chunks (write some by hand, generate some with an LLM and check them); an eval script that prints baseline numbers
- **Learn from:** [Hamel Husain: Your AI Product Needs Evals](https://hamel.dev/blog/posts/evals/), [Eugene Yan: Patterns for building LLM-based systems](https://eugeneyan.com/writing/llm-patterns/) (evals section), *Introduction to Information Retrieval* ch 8 ([free online](https://nlp.stanford.edu/IR-book/))
- **Done when:** one command prints recall@5 and MRR

### Step 9: Hybrid search and reranking (4 days)
- **Learn:** keyword search / BM25, Reciprocal Rank Fusion, cross-encoder rerankers (`bge-reranker-v2-m3`)
- **Build:** hybrid retrieval + reranker; re-run the eval after each change
- **Learn from:** the hybrid search pages in the [Qdrant docs](https://qdrant.tech/documentation/), "Retrieve & Re-Rank" in the [sentence-transformers docs](https://sbert.net), the `BAAI/bge-reranker-v2-m3` model card on Hugging Face
- **Done when:** a table shows vector vs hybrid vs hybrid + rerank

### Step 10: RAG answers and answer evaluation (5 days)
- **Learn:** grounded prompting, citations, refusing when the context lacks the answer (hallucination control), LLM-as-judge, RAGAS (faithfulness, answer relevancy)
- **Build:** `/ask` (retrieve → rerank → prompt → answer with citations), written without LangChain; answer-quality eval; README comparison table, Russian vs Kazakh
- **Learn from:** [RAGAS docs](https://docs.ragas.io), [Hamel Husain's blog](https://hamel.dev/) (posts on LLM-as-a-judge)
- **Done when:** the README shows retrieval and answer metrics

### Step 11: Deploy v1 (3 days)
- **Learn:** a VPS, SSH, Caddy for HTTPS, secrets in environment variables
- **Build:** the compose stack on a VPS with a public URL
- **Learn from:** [Caddy reverse proxy quick-start](https://caddyserver.com/docs/quick-starts/reverse-proxy), DigitalOcean's community tutorials "Initial Server Setup with Ubuntu" and "How To Install and Use Docker on Ubuntu". A small VPS costs about €4–6 a month (Hetzner, DigitalOcean); the GitHub Student Developer Pack includes hosting credits if you're a student
- **Done when:** the live URL works
- 📨 **Start applying.** You now cover the most-requested skills: Python, RAG, FastAPI, Docker, evaluation.

### Part C: Agents

### Step 12: Tool calling and LangGraph (6 days)
- **Learn:** function/tool calling (write the loop by hand first), then LangGraph: state, nodes, edges, memory, step limits; ReAct prompting
- **Build:** an agent with tools `search_docs`, `summarize_doc`, `sql_query` (read-only DB user)
- **Learn from:** Anthropic's article "Building effective agents" (concepts), LangChain Academy's free [Introduction to LangGraph](https://academy.langchain.com/courses/intro-to-langgraph), the [Hugging Face Agents Course](https://huggingface.co/learn/agents-course) (LangGraph unit)
- **Done when:** the agent answers a question that needs two different tools

### Step 13: MCP (3 days)
- **Learn:** the Model Context Protocol and the MCP Python SDK
- **Build:** an MCP server exposing the same tools; test it with MCP Inspector or another MCP client
- **Learn from:** [modelcontextprotocol.io](https://modelcontextprotocol.io) (quickstart: build a server), the [Hugging Face MCP Course](https://huggingface.co/learn/mcp-course)
- **Done when:** an external MCP client can call your tools

### Step 14: Safety and observability (4 days)
- **Learn:** prompt injection, guardrails (input/output validation, tool allow-lists), Langfuse tracing
- **Build:** malicious test documents the agent must ignore; tracing of every LLM and tool call (latency, tokens, cost); eval in CI that fails if recall@5 drops
- **Learn from:** [OWASP Top 10 for LLM Applications](https://genai.owasp.org), [Simon Willison on prompt injection](https://simonwillison.net/tags/prompt-injection/), [Langfuse docs](https://langfuse.com/docs) (it self-hosts with docker compose)
- **Done when:** CI blocks a change that makes retrieval worse

### Part D: Models

### Step 15: NER in production (5 days)
- **Learn:** HF token classification on ru/kk data (you did NER in the course; now on your languages); MLflow run tracking and model registry (one day; it shows up in ML-engineer roles)
- **Build:** a fine-tuned NER model; the API loads it from the MLflow registry; entities stored and used as search filters
- **Learn from:** your HF ch 7 token-classification notebooks, NER datasets on the Hugging Face Hub (KazNERD for Kazakh, WikiNEuRal for Russian), [MLflow docs](https://mlflow.org/docs/latest/) (tracking quickstart, model registry)
- **Done when:** `/search?org=...` filters by extracted entities, and MLflow shows compared runs

### Step 16: LoRA fine-tuning (6 days)
- **Learn:** PEFT / LoRA, QLoRA (4-bit), TRL `SFTTrainer` (the chat templates from step 0 come back here). Use a free Colab GPU
- **Build:** fine-tune `Qwen2.5-0.5B-Instruct` or `-1.5B-Instruct` to extract structured fields (JSON) from your documents; compare it with the prompting approach from step 6 on the same test set
- **Learn from:** [HF LLM course ch 11](https://huggingface.co/learn/llm-course/chapter11/1) (the LoRA section), [PEFT docs](https://huggingface.co/docs/peft), [TRL docs](https://huggingface.co/docs/trl), [Unsloth docs](https://docs.unsloth.ai) (fast free-Colab notebooks)
- **Done when:** a table shows prompting vs LoRA on the same test set

### Step 17: Serving and quantization (3 days, needs a GPU)
- **Learn:** quantization (4-bit, GGUF), vLLM's OpenAI-compatible server
- **Build:** serve the LoRA model with vLLM; measure latency and cost against the API model
- **Learn from:** [vLLM docs](https://docs.vllm.ai) (quickstart, OpenAI-compatible server), the quantization pages in the [Transformers docs](https://huggingface.co/docs/transformers), [llama.cpp](https://github.com/ggml-org/llama.cpp) for GGUF
- **Done when:** the README has a latency / cost comparison

### Part E: Interviews

### Step 18: Interview prep (8 days)
- [ ] ML theory review: bias/variance, overfitting, cross-validation, metrics, regularization; trees and boosting briefly (you did AdaBoost and random forests in the IBM course). Use [StatQuest](https://www.youtube.com/@statquest) for anything fuzzy
- [ ] Deep learning: go back over your Karpathy notebooks (backprop, attention, BPE)
- [ ] NLP / LLM questions: embeddings, RAG failure modes, fine-tuning vs RAG, evaluation
- [ ] System design: "design a RAG assistant for a bank"
- [ ] Project walkthrough: README with an architecture diagram, metrics and trade-offs; a 5-minute explanation out loud
- [ ] Mock interviews
- **Learn from:** Chip Huyen's free [ML Interviews book](https://huyenchip.com/ml-interviews-book/), *AI Engineering* ch 10 for system design

---

## 4. Timeline

About 81 working days at 6 days a week is roughly 13.5 weeks; plan for 16 with buffer. If you start Mon 19 Oct 2026:

| Milestone | Around |
|---|---|
| Step 1 done: Karpathy block | early November 2026 |
| Step 6 done: API + DB + LLM endpoints | late November 2026 |
| Step 11 done: RAG deployed, start applying | mid-to-late December 2026 |
| Step 14 done: agent with MCP, tracing, CI eval | mid-January 2027 (New Year falls in steps 12–13) |
| Step 18 done | early February 2027 |

---

## 5. Not now

- HF ch 12 (GRPO / RLHF): one posting, 6+ years
- Kubernetes (3/12 postings, all large companies and mid+ roles), Kafka / RabbitMQ, Airflow
- Voice (ASR / TTS), deeper computer vision
- Karpathy: makemore Parts 3–5 and "Let's reproduce GPT-2 (124M)" (good for research, not needed for the job)

---

## 6. Stack reference

| Layer | Pick |
|---|---|
| Python tooling | `uv`, `ruff`, `pytest`, type hints |
| API | FastAPI + Pydantic v2, async |
| Database | PostgreSQL + SQLAlchemy 2 + Alembic |
| Vector database | Qdrant (named in postings; Milvus and FAISS also appear) |
| Embeddings | `bge-m3` / `multilingual-e5` via `sentence-transformers` |
| Keyword search | BM25 or Postgres full-text search |
| Reranker | `bge-reranker-v2-m3` |
| LLM | Any OpenAI-compatible API |
| Agents | LangGraph + MCP Python SDK |
| Evaluation | Own recall@k / MRR scripts, RAGAS, LLM-as-judge |
| Observability | Langfuse |
| NER | HF `transformers` token classification + `seqeval` |
| Experiment tracking | MLflow |
| Fine-tuning | PEFT (LoRA / QLoRA) + TRL |
| Serving | vLLM |
| Infrastructure | Docker, docker-compose, GitHub Actions, VPS + Caddy |

---

## Sources for section 1 (searched October 2026)

- [Dreamlab Technologies: ML Engineer (NLP / RAG)](https://astana.hh.kz/vacancy/130648164)
- [Globerce: AI Engineer / LLM Engineer](https://almaty.hh.kz/vacancy/132283800)
- [Globerce: AI Engineer, Freedom Business](https://almaty.hh.kz/vacancy/130927257)
- [Documentolog: Middle ML Engineer (NLP)](https://cvhub.documentolog.com/job/4676)
- [Kaspi.kz: Middle / Senior ML Engineer](https://freehire.me/jobs/middle-senior-ml-engineer-kaspi-kz-mcm66aln)
- [Bank CenterCredit: Voice AI / NLP / LLM Engineer](https://almaty.hh.kz/vacancy/129207166)
- [THE TECH: AI and Data vacancies in Central Asia (Halyk Finance)](https://the-tech.kz/gde-rabotat-v-ai-i-data-v-czentralnoj-azii-podborka-aktualnyh-vakansij)
- [AML Academy: ML Engineer](https://astana.hh.kz/vacancy/130222393)
- [Progressive Mind: NLP Engineer](https://astana.hh.kz/vacancy/131993829)
- [Sber: AI Agent Engineer](https://hh.ru/vacancy/130659506)
- [M-TECH: Python / LLM Engineer, RAG and AI agents](https://career.habr.com/vacancies/1000167695)
- [Sber: LLM Engineer (RecSys)](https://developers.sber.ru/kak-v-sbere/vacancies/llm-engineer-recsys)
- [Habr: what's wrong with LLM Engineer vacancies](https://habr.com/ru/articles/1030534/)
