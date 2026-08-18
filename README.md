<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=180&section=header&text=Gunakarthik%20Naidu%20Lanka&fontSize=40&fontColor=fff&animation=twinkling&fontAlignY=32&desc=Builder.%20Thinker.%20Occasional%20Debugger%20at%203am.&descAlignY=55&descSize=16" width="100%"/>

<a href="https://github.com/Gunakarthik1">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1000&color=6E9FFF&center=true&vCenter=true&width=650&lines=BS+%2B+MS+CS+%40+ASU+%E2%80%94+Accelerated+%F0%9F%8E%93;Minor+in+Business+%7C+GPA+4.0+%E2%AD%90;I+ship+things+that+actually+work+%F0%9F%9A%80;Product-minded+engineer+%7C+OPT+%2F+H-1B+Ready+%F0%9F%8C%8E;From+idea+to+production+%E2%80%94+fast." alt="Typing SVG" />
</a>

<br/>

<img src="https://komarev.com/ghpvc/?username=Gunakarthik1&label=Profile%20Views&color=6e9fff&style=flat-square" />
&nbsp;
<a href="https://www.linkedin.com/in/gunakarthik-naidu-lanka"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white"/></a>
&nbsp;
<a href="mailto:gunakarthiknaidu@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white"/></a>
&nbsp;
<img src="https://img.shields.io/badge/GPA-4.0%2F4.0-brightgreen?style=flat-square"/>
&nbsp;
<img src="https://img.shields.io/badge/BS%20%2B%20MS-Accelerated%20%40%20ASU-blueviolet?style=flat-square"/>

</div>

---

## 👋 About Me

```python
class Gunakarthik:
    education  = "BS + MS CS @ Arizona State University (Accelerated)"
    minor      = "Business"
    gpa        = 4.0
    location   = "Tempe, Arizona 🌵"
    vibe       = ["ship fast", "think in systems", "build for real users"]
    background = ["engineering", "product thinking", "a little business brain"]
    open_to    = ["SWE", "Product Engineering", "Founding Eng", "OPT / H-1B"]

    def say_hi(self):
        print("I like building things end-to-end — from the idea to prod.")
```

---

## 🚀 Things I've Built

<div align="center">

| Project | What it does | Stack | Live |
|--------|-------------|-------|------|
| ⚡ [**GPU Cluster Telemetry**](https://github.com/Gunakarthik1/gpu-cluster-telemetry) | Distributed telemetry daemon for AI/HPC nodes — collects GPU & host metrics, runs Pandas analytics, fires automated remediation | Python · FastAPI · Pandas · Prometheus · Docker | [↗ Demo](https://gunakarthik1.github.io/gpu-cluster-telemetry/frontend/) |
| 🤖 [**HireAgent**](https://github.com/Gunakarthik1/HireAgent) | Scrapes 8+ job boards, scores roles, rewrites your resume, and auto-applies — end to end | Python · DeepSeek · Playwright · LaTeX | — |
| 🚗 [**VinSight**](https://github.com/Gunakarthik1/Vin-Sight) | Point a VIN at it, get back market value, recall history, and a 12-month price curve | React · TypeScript · Express · Ollama | [↗ Live](https://vin-sight.onrender.com/) |
| 💼 [**Portfolio**](https://github.com/Gunakarthik1/portfolio) | This very website. Smooth, fast, no fluff. | Next.js · Tailwind · Framer Motion | [↗ Live](https://gunakarthik-naidu-lanka-portfolio.vercel.app/) |
| 🔍 [**Hybrid-RAG Gateway**](https://github.com/Gunakarthik1/hybrid-rag-gateway) | Production RAG API with BM25 + FAISS retrieval, Reciprocal Rank Fusion reranking, and a semantic cache (cosine threshold 0.96) that eliminates redundant LLM calls — streams via SSE | Python · FastAPI · FAISS · BM25 · Docker | — |
| 🧠 [**LLM Inference Engine**](https://github.com/Gunakarthik1/llm-inference-engine) | High-throughput serving engine with PagedAttention KV-cache simulation, continuous batching scheduler, real-time WebSocket dashboard, and p50/p95/p99 TTFT tracking | Python · FastAPI · WebSocket · Prometheus · asyncio | — |
| 🏗️ [**Lakehouse ETL Pipeline**](https://github.com/Gunakarthik1/lakehouse-etl-pipeline) | Medallion architecture ETL (Bronze/Silver/Gold) with 6 configurable data quality rules, quarantine layer, lineage tracking, and Parquet-backed aggregations | Python · FastAPI · Pandas · Parquet · SQLite | — |
| 🔒 [**AI Privacy Gateway**](https://github.com/Gunakarthik1/ai-privacy-gateway) | 7-stage AI proxy: rate limiting, budget enforcement, prompt injection detection, PII masking (SSN/email/phone/card with Luhn), LLM call, unmasking, and structured audit logging | Python · FastAPI · SQLite · Pydantic · Docker | — |
| 📊 [**LLM Eval Harness**](https://github.com/Gunakarthik1/llm-eval-harness) | Rubric-based LLM-as-a-Judge framework scoring faithfulness, relevance, coherence, and completeness with adversarial test generation and HTML/JSON reporting | Python · FastAPI · Pydantic · asyncio · Docker | — |
| 🏘️ [**NeighborhoodPulse**](https://github.com/Gunakarthik1/neighborhood-pulse) | Concurrent multi-agent platform gathering FEMA flood data, zoning codes, and climate risk in parallel — synthesizes weighted risk scores (0–100) with citations and recommendations | Python · FastAPI · asyncio · Pydantic · SQLite | — |

</div>

<details>
<summary><b>⚡ GPU Cluster Telemetry — how it works</b></summary>
<br>

```
pynvml + psutil → POST /api/v1/telemetry → Pandas analytics → Prometheus → Grafana
                                                    ↓
                                         ISOLATE_NODE / FLUSH_TEMP_CACHE → Agent
```

- **pynvml** samples GPU temp, VRAM, power draw every 5s — falls back to a realistic H100 simulation on non-NVIDIA machines
- **FastAPI** gateway validates payloads with Pydantic v2, persists to SQLite via SQLAlchemy
- **Pandas sliding-window** detects thermal breaches (>80°C), VRAM saturation (>95%), TCP TIME_WAIT spikes (>100)
- Automatically dispatches `ISOLATE_NODE` or `FLUSH_TEMP_CACHE` back to the agent over HTTP
- **Prometheus** scrapes `/metrics` every 10s — 7 gauges/counters across GPU and host dimensions
- **60 pytest tests** — unit, integration, mocked HTTP — zero external dependencies needed

</details>

<details>
<summary><b>🤖 HireAgent — how it works</b></summary>
<br>

```
Discover → Enrich → Score (1-10) → Tailor Resume → Cover Letter → Auto-Apply
```

- Hits **8+ job boards**, filters for entry-level / OPT-eligible roles
- **DeepSeek-V3** scores, **DeepSeek-R1** rewrites resume bullets to match JD
- Vision model fills forms — handles CAPTCHAs, SSO gates, email walls
- Sends **Telegram pings** when an app goes through

</details>

<details>
<summary><b>🚗 VinSight — under the hood</b></summary>
<br>

- Runs a **local LLM** (DeepSeek-R1 / Gemma 3) via Ollama — zero data leaves your machine
- **TTL cache** (VinCache) skips repeat NHTSA calls — same VIN = instant response, ~30% TTFT reduction
- Pulls **live NHTSA recall data**, translates raw component codes into plain English with severity triage (high/medium/low)
- **Confidence-weighted valuation bands**: ±12% with real MSRP data, widens to ±18% on fallback estimates
- Brand-specific depreciation rates across 40+ makes; 12-month value projection curve
- Gives you a **hold vs sell recommendation** generated by the local LLM, with rule-based fallback when Ollama isn't running

</details>

<details>
<summary><b>🔍 Hybrid-RAG Gateway — how it works</b></summary>
<br>

```
Query → BM25 (sparse) + FAISS (dense) → RRF merge → CrossEncoder rerank → Semantic Cache → SSE stream
```

- **BM25Okapi** runs keyword recall; **FAISS** dense embeddings do semantic similarity — both over the same 27-doc corpus
- **Reciprocal Rank Fusion** (k=60) combines both ranked lists into a single unified score
- **CrossEncoder reranker** applies IDF-weighted token overlap + positional decay for final ordering
- **Semantic cache** (cosine similarity ≥ 0.96) returns cached answers instantly — skips retrieval entirely on near-duplicate queries
- FastAPI streams ranked context chunks over **SSE**; cache evicts by TTL + LRU
- **61 pytest tests** — retrieval math, RRF formula, cache TTL boundary, LRU eviction

</details>

<details>
<summary><b>🧠 LLM Inference Engine — how it works</b></summary>
<br>

```
Request → PriorityQueue scheduler → PagedAttention KV allocator → Token generator → WebSocket stream → Prometheus
```

- **PagedAttention** allocates 16-token pages from an 80GB VRAM pool — prevents fragmentation, enables higher concurrency
- **Continuous batching**: 50ms drain loop pulls up to 8 requests by priority (HIGH/NORMAL/LOW) with no head-of-line blocking
- Rolling window tracks true **p50/p95/p99 TTFT percentiles** across the last 100 requests
- **10-second rolling window** for tok/s throughput; 10 Prometheus gauges + 1 counter
- WebSocket dashboard streams live metrics without polling
- **43 pytest tests** — page allocator, scheduler priority, batch sizing, metric percentiles

</details>

<details>
<summary><b>🏗️ Lakehouse ETL Pipeline — how it works</b></summary>
<br>

```
Raw events → Bronze (schema + metadata) → Quality Gate → Silver (transforms + dedup) → Gold (4 aggregations)
                                                ↓
                                         Quarantine (reason-coded rows)
```

- **Bronze layer** checks 13 schema fields, enriches with `_bronze_id`, `_ingested_at`, `_source_file`, `_batch_id`
- **6 quality rules**: NonNull, Range, Type, DateRange, Uniqueness, Categorical — failures quarantined with reason codes
- **Silver** deduplicates on `event_id` (keep latest), normalises timestamps to UTC, casts types, adds quality score per row
- **Gold** produces 4 Parquet tables: revenue by category, user cohort retention, conversion funnel, channel mix
- `MetadataCatalog` tracks full **lineage** (upstream + downstream) across all layers
- **85 pytest tests** — schema validation, all 6 quality rules, dedup logic, lineage chains

</details>

<details>
<summary><b>🔒 AI Privacy Gateway — how it works</b></summary>
<br>

```
Request → Rate Limit → Budget → Injection Detect → PII Mask → LLM → PII Unmask → Audit Log → Response
```

- **Token-bucket** rate limiter: 100 capacity, 10 tok/s refill — per API key, thread-safe with monotonic clock
- **Budget enforcer**: free 10k/day · standard 100k/day · enterprise unlimited — SQLite-backed atomic UPSERT
- **20 injection patterns** across jailbreak, role override, data exfiltration, social engineering, delimiter injection
- **PII masking**: SSN, email, phone, credit card (Luhn-validated), API keys, IP, DOB — positions preserved for exact unmask
- Full **structured audit trail**: SHA-256 prompt hashing, per-stage timing, threat classification
- **73 pytest tests** — Luhn validation, injection scoring, budget enforcement, mask/unmask round-trip

</details>

<details>
<summary><b>📊 LLM Eval Harness — how it works</b></summary>
<br>

```
Scenario → LLM-as-a-Judge (faithfulness + relevance + coherence + completeness) → Weighted score → HTML/JSON report
```

- **LLM-as-a-Judge rubric**: 4 criteria, each 0–1 float with configurable weights
- **Adversarial generator** injects context hijacking, negation, irrelevant context, and delimiter injection to stress-test robustness
- Scenario runner executes evaluations **concurrently** with asyncio; captures latency per evaluation
- **Reporter** aggregates pass rates, score distributions, per-criteria breakdowns into HTML and JSON
- **78 pytest tests** — rubric math, adversarial patterns, reporter formatting, scenario loading

</details>

<details>
<summary><b>🏘️ NeighborhoodPulse — how it works</b></summary>
<br>

```
Location → asyncio.gather([FEMA Agent, Zoning Agent, Climate Agent]) → Synthesis Agent → Risk Report
```

- Three specialized agents run **in parallel** — FEMA flood zones, municipal zoning codes, 30-year climate projections
- Each agent returns `AgentResult` with structured data, citations, status (SUCCESS/DEGRADED/FAILED), and latency_ms
- **Weighted risk score** (0–100) across 6 factors: flood 30% · wildfire 20% · heat 15% · sea level 15% · drought 10% · air quality 10%
- Inline **citations with global indices** across all agent sources; data gaps surface clearly when an agent degrades
- **Recommendations engine** generates up to 6 actionable items based on risk score, SFHA status, wildfire level, AQI
- **35 pytest tests** — agent schemas, risk score math, citation aggregation, graceful degradation

</details>

---

## 🛠️ Stack

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)

![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)

</div>

---

## 📊 Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Gunakarthik1&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" height="165"/>
&nbsp;
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Gunakarthik1&layout=compact&theme=tokyonight&hide_border=true&langs_count=6" height="165"/>

</div>

<div align="center">

<img src="https://streak-stats.demolab.com?user=Gunakarthik1&theme=tokyonight&hide_border=true" width="55%"/>

</div>

---

## 🐍 Contributions

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Gunakarthik1/Gunakarthik1/output/github-contribution-grid-snake-dark.svg"/>
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Gunakarthik1/Gunakarthik1/output/github-contribution-grid-snake.svg"/>
    <img alt="Snake animation" src="https://raw.githubusercontent.com/Gunakarthik1/Gunakarthik1/output/github-contribution-grid-snake.svg"/>
  </picture>
</div>

---

## 🌱 Open Source

<table>
<tr>
<td width="60px" align="center">🔬</td>
<td>

**[scikit-learn Contributor](https://github.com/scikit-learn/scikit-learn/pull/34685)** — Python ML library · 60k+ ⭐

Added `elimination_order_` attribute to `RFECV` ([PR #34685](https://github.com/scikit-learn/scikit-learn/pull/34685)) exposing per-step feature elimination order — previously discarded information the library offered no way to access. Set up the dev environment via Docker + micromamba, debugged a BLAS/aarch64 incompatibility on Apple Silicon, built from source, and submitted following scikit-learn's contribution guidelines (changelog, docstring conventions). **60/60 tests passing, all CI checks green.**

</td>
</tr>
</table>

---

## 🏅 Certifications

<div align="center">

<a href="https://catalog-education.oracle.com/ords/certview/sharebadge?id=D6E7676E2A49E0DC47E89DF8FB620DBC8DE1C3AAF8F18097DE768EF2809FBAC7">
  <img src="https://img.shields.io/badge/Oracle-Agentic%20AI%20Foundations%20Associate-F80000?style=for-the-badge&logo=oracle&logoColor=white" alt="Oracle Agentic AI Certified Foundations Associate"/>
</a>

</div>

| Badge | Certification | Issuer | Expires |
|-------|--------------|--------|---------|
| 🤖 | [**Agentic AI Certified Foundations Associate**](https://catalog-education.oracle.com/ords/certview/sharebadge?id=D6E7676E2A49E0DC47E89DF8FB620DBC8DE1C3AAF8F18097DE768EF2809FBAC7) | Oracle | Aug 2028 |

> Built agents from scratch using LangChain, OpenAI Agents SDK, and real MCP servers. Deployed on OCI Enterprise AI Agents and Oracle AI Database.

---

## 🎯 Right Now

- 🎓 Wrapping up **BS + MS CS @ ASU** (Accelerated, Minor in Business — May 2026)
- 🔨 Building things that feel like products, not side projects
- 🌎 Open to roles — **SWE, product-eng, founding team** — OPT / H-1B
- 📬 **gunakarthiknaidu@gmail.com**

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%"/>
</div>
