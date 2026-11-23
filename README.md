## Rafraf Reza

**AI Engineer building LLM agents, RAG systems and the full-stack products around them.**
<!-- TODO: add your current city here -->
Open to relocating: Bangalore, Hyderabad, Pune, NCR

**Open to remote AI/GenAI roles · available immediately**

### What I do

- I build LLM agents that use deterministic code for anything that has to be exact, such as arithmetic, lookups and permissions.
- I measure retrieval and model quality on held-out data, and CI fails the build if those numbers regress.
- I ship the whole product: Python/FastAPI backends, React/TypeScript frontends and Postgres with row-level security.

### Featured work

#### CalorAI: agentic RAG nutrition copilot
**Problem:** LLM calorie trackers make up nutrition numbers and get the arithmetic wrong.<br>
**Built:** a LangGraph agent over a hand-built hybrid retriever (BM25 + phonetic + dense, RRF, reranker) on a 408-food knowledge base. FastAPI · Gemini · React/TypeScript.<br>
**Result:** 95.2% Hit@1 on held-out queries and 93.8% correct abstention on foods outside the KB. CI fails the build if held-out quality regresses.<br>
<!-- TODO: add a CalorAI live demo link once it is deployed -->
[Repo](https://github.com/rafrafreza/CalorAI-Agentic-RAG) · [Write-up](https://github.com/rafrafreza/CalorAI-Agentic-RAG#evaluation)

#### LabSwift: lab information system for pathology labs
**Problem:** small labs run on paper registers, Excel and Word templates, and staff spot abnormal values by eye.<br>
**Built (solo, 0 → 1):** patients, test templates with gender-specific reference ranges, auto-flagged results, in-browser PDF reports and billing. React · TypeScript · PostgreSQL (Supabase).<br>
**Result:** in production at diagnostic labs, with 10,000+ reports generated on the client's deployment. Access control is enforced in Postgres: row-level security on every table, triggers that block role self-promotion, and atomic report saves.<br>
[Repo](https://github.com/rafrafreza/labswift-lab-management-system) · [Live demo](https://labswift-demo.vercel.app) · [Write-up](https://github.com/rafrafreza/labswift-lab-management-system#engineering-deep-dive)

#### Reloop: e-waste logistics platform (team of 5)
**Problem:** household e-waste in India goes through informal channels with no price transparency or traceability.<br>
**I built:** the SQLAlchemy data model and schemas, the consumer, partner, centre and auth APIs, most of the four role-based React apps, and the Render deploy. FastAPI · PostgreSQL · React 19.<br>
**Decision:** admin accounts can't be created through the public API. They are provisioned server-side at startup.<br>
[Repo](https://github.com/rafrafreza/Reloop-E-Waste-Logistics-Platform) · [Live demo](https://ewaste-frontend-lc20.onrender.com/) · [Write-up](https://github.com/rafrafreza/Reloop-E-Waste-Logistics-Platform#readme)

#### Music genre classification under distribution shift
**Problem:** the model trains on clean single-song stems but is tested on noisy mashups of stems from different songs.<br>
**Built:** a training loop that recreates the test-set construction process, plus a benchmark of 5 architectures ending in a two-phase fine-tuned Audio Spectrogram Transformer. PyTorch · Hugging Face Transformers.<br>
**Result:** Kaggle macro F1 rose from 0.358 (MFCC baseline) to 0.890. The model is published on Hugging Face with a live demo.<br>
[Repo](https://github.com/rafrafreza/robust-audio-genre-classification) · [Live demo](https://huggingface.co/spaces/ghazi-r3/music-genre-classifier) · [Write-up](https://github.com/rafrafreza/robust-audio-genre-classification/blob/main/docs/technical-report.pdf)

**Also:** [Haqqat](https://github.com/rafrafreza/haqqat-ai-productivity-coach), an AI productivity coach [live](https://haqqat.netlify.app) with real users. It calls Gemini from a Supabase Edge Function that checks the user's JWT and enforces a per-user daily quota. Built with Lovable.

### How I build

- **The LLM proposes, code disposes.** In CalorAI the model decides *what* you ate. Deterministic code scales portions and sums macros, asks the user to confirm implausible amounts, and abstains rather than guess.
- **Evals before vibes.** 221 labelled queries, a dev/test split, an ablation table, and a CI gate on held-out Hit@1, grounding accuracy and abstention.
- **Security lives in the database.** LabSwift enforces row-level security on every table, trigger-written audit logs and least-privilege public access, so the UI is not the security boundary.
- **Report the honest number.** The audio project excludes its own baseline's 0.714 validation score because that split leaked songs from training into validation.

### Tech stack

**AI/ML:** PyTorch · Hugging Face Transformers · scikit-learn · NumPy<br>
**LLM/GenAI:** LangGraph · LangChain · Gemini API · hybrid RAG (BM25 + dense, RRF)<br>
**Backend:** Python · FastAPI · Flask · SQLAlchemy · PostgreSQL · Redis · Celery · pytest<br>
**Frontend:** TypeScript · React · Vue 3 · Tailwind CSS<br>
**Infra:** Docker · GitHub Actions · Supabase · Vercel

### Contact

<!-- TODO: add email, LinkedIn and résumé links to this row -->
Models on Hugging Face as [ghazi-r3](https://huggingface.co/ghazi-r3)
