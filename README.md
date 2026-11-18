<div align="center">

# Ayush Khati
### Systems Engineer · Program Analysis Researcher · Distributed Backend Architect

*Designing deterministic static analyzers, fault-tolerant distributed backends, and high-throughput streaming pipelines that hold up under production load.*

[![ConcurrencyGuard](https://img.shields.io/badge/ConcurrencyGuard.dev-Live-334155?style=for-the-badge&logo=googlechrome&logoColor=white)](https://concurrencyguard.dev/)
[![cguard PyPI](https://img.shields.io/pypi/v/concurrency-guard?style=for-the-badge&logo=pypi&logoColor=white&label=cguard%20PyPI&color=334155)](https://pypi.org/project/concurrency-guard/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ayush_Khati-334155?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ayush-khati-8a342821b/)
[![Portfolio](https://img.shields.io/badge/Portfolio-portfoliokhati-334155?style=for-the-badge&logo=safari&logoColor=white)](https://portfoliokhati.netlify.app/)
[![Medium](https://img.shields.io/badge/Medium-Technical_Essays-334155?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@ayushiskhati305)
[![Email](https://img.shields.io/badge/Email-ayushiskhati305%40gmail.com-334155?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ayushiskhati305@gmail.com)

</div>

---

## Engineering Telemetry

<table>
  <tr>
    <td align="center" width="25%"><h3>2,346+</h3><sub><b>Monthly cguard downloads</b><br/>v3.4.0 · 1,224+/week</sub></td>
    <td align="center" width="25%"><h3>1.2M/day</h3><sub><b>Production events</b><br/>Celery + Redis · zero loss/duplication</sub></td>
    <td align="center" width="25%"><h3>116×</h3><sub><b>Warm scan speedup</b><br/>12.80s → 0.110s · 1,000+ files</sub></td>
    <td align="center" width="25%"><h3>86%</h3><sub><b>Hot-path p99 reduction</b><br/>1.8s → 240ms · 99.8% uptime</sub></td>
  </tr>
</table>

---

## Flagship Open-Source Platform — ConcurrencyGuard (`cguard` v3.4.0)

**[concurrencyguard.dev](https://concurrencyguard.dev/)** · **[PyPI](https://pypi.org/project/concurrency-guard/)** · **[GitHub](https://github.com/AyushkhatiDev/concurrency-guard)**

ConcurrencyGuard is a deterministic Python semantic SAST, empirical race verifier, lossless LibCST auto-patcher, and LSP 3.17 engine for backend concurrency vulnerabilities (CWE-362). It analyzes FastAPI, SQLAlchemy 2.0, Django ORM, SQLModel, Tortoise ORM, Celery, Redis, `asyncio`, and `threading`.

- **Semantic analysis:** 21 concurrency rules (`CG-001`–`CG-021`) using inter-procedural call graphs and forward data-flow tracking to identify unlocked read-modify-write races, missing idempotency guards, TOCTOU collisions, lock-order deadlocks, and session-lifetime leaks.
- **Empirical verification:** `cguard verify` coordinates workers with `asyncio.Barrier` / `threading.Barrier`; `cguard simulate` models async interleavings and exports runnable pytest chaos reproducers.
- **Lossless remediation:** `cguard fix --diff/--write` produces LibCST patches for locking, atomic ORM updates, rollback handling, and related concurrency repairs.
- **Shift-left infrastructure:** zero-dependency LSP 3.17 (`cguard lsp`), real-time watch mode, GitHub PR inline review, baseline ratcheting, and OASIS SARIF v2.1.0 export.
- **Measured performance:** SHA-256 content-addressable caching reduces a 1,000+ file monorepo warm scan from `12.80s` to `0.110s` (**116×**).

```bash
pip install concurrency-guard

# Scan and emit SARIF for code scanning
cguard scan src/ --format sarif -o cguard.sarif

# Simulate an async race and export a pytest reproducer
cguard simulate src/routers/billing.py --rule CG-001 --export-test tests/test_race_repro.py

# Preview an auto-remediation or start the language server
cguard fix src/ --diff
cguard lsp
```

---

## Production Systems Engineering

**Software Engineer — Backend & Distributed Systems, Udeck Services** · Oct 2025–present
**Intern, Udeck Services** · Apr 2025–Oct 2025

Architecting multi-tenant backend systems and cloud infrastructure sustaining **99.8% uptime** for **2,500+ businesses** managing **10,000+ SKUs**.

- Replaced an `O(N)` 20-level recursive hierarchy with an indexed `O(1)` closure table, reducing endpoint latency **71%** (`3.96s → 1.15s`) and database round trips from **133 to 6**.
- Built a fault-tolerant Celery + Redis pipeline that processes **1.2M daily events** with idempotent consumers and DLQs, maintaining zero message loss or duplication.
- Eliminated race conditions under **500-request burst load** across **198 REST endpoints**, maintaining zero ledger drift with idempotency keys, transactional double-entry invariants, and row-level locks.
- Reduced hot-path read p99 latency **86%** (`1.8s → 240ms`) through query-plan optimization and composite indexing; reduced incident MTTD **93%** (`45 min → 3 min`).
- Performed a zero-downtime migration of a **38M-row** production table with expand/contract phases, batched backfills, and point-in-time recovery.
- Reduced homepage database queries **97%**, from 368 to single digits, using relational bulk preloading.

---

## Featured Systems & Research Portfolio

| System | Architecture | Outcome |
| --- | --- | --- |
| **[ConcurrencyGuard](https://github.com/AyushkhatiDev/concurrency-guard)** | Semantic SAST, empirical race verification, LibCST patching, LSP 3.17 | 21 CWE-362 rules; 116× cached warm scans |
| **MatchLens: Streaming AI Agents** | Microsoft Agent Framework, Azure Event Hubs, Microsoft Fabric reconciliation | Verified 1,728/1,728 streaming events with zero loss or duplication |
| **Sentinel: Multi-Stream Computer Vision Engine** | 15-camera RTSP/HLS workers, bounded queues, ONNX Runtime, PyAV, PostGIS | Fault-isolated ingestion with 2–30s exponential recovery backoff |
| **[VibeSec](https://github.com/AyushkhatiDev/vibesec)** | Deterministic AST security scanning with automated remediation | 1,200+ downloads, 179 unit tests, 100% rule coverage, 24 vulnerability patterns |
| **[LLM Eval & Red-Teaming](https://github.com/AyushkhatiDev/llm-eval)** | Three-tier distributed judges for factuality, safety, and adversarial robustness | 86% hallucination-detection accuracy across 27 verification checks |
| **[Data Extractor](https://github.com/AyushkhatiDev/data-extractor)** | Eight async streams with `Qwen-2.5-VL → Llama-3.1 → Regex` fallback | Deterministic graceful degradation; architecture documented in research paper |

---

## Open Source, Publications & Leadership

- **Fedora Project Contributor:** upstream bug fixes, features, and documentation merged into Fedora Linux DRI repositories.
- **Python open-source maintainer:** maintainer of `concurrency-guard` and `vibesec` on PyPI; contributor to Python/Rust ecosystem tooling.
- **Technical writing & community:** 1,000+ engineering readers on [Medium](https://medium.com/@ayushiskhati305); Technical Lead at TechFrenzy, organizing 5+ hackathons for 200+ developers.

---

## Technical Architecture & Systems Stack

| Domain | Core technologies & primitives |
| --- | --- |
| Program analysis & compilers | Python AST, LibCST, inter-procedural call graphs, forward data-flow taint analysis, LSP 3.17, OASIS SARIF v2.1.0, `asyncio.Barrier` verification |
| Languages | Python, C++, SQL, TypeScript, JavaScript, Bash, Rust tooling integration |
| Backend & distributed systems | FastAPI, Django ORM, SQLAlchemy 2.0, SQLModel, Tortoise ORM, Celery, `asyncio` / anyio, REST and event-driven architectures |
| Data & streaming | PostgreSQL, PostGIS, MySQL, Redis, Azure Event Hubs, Microsoft Fabric, SQLite WAL/content-addressable caching |
| Applied AI & computer vision | Microsoft Agent Framework, ONNX Runtime, PyAV, multi-model judge chains, Qwen-2.5-VL and Llama-3.1 fallback pipelines |
| Infrastructure & verification | Linux, Docker, AWS, Nginx, GitHub Actions CI/CD, pytest, pytest-asyncio, mypy, Ruff |

---

<div align="center">

### Open to systems engineering, backend/distributed systems, and program analysis / AI research roles.

[concurrencyguard.dev](https://concurrencyguard.dev/) · [LinkedIn](https://www.linkedin.com/in/ayush-khati-8a342821b/) · [Portfolio](https://portfoliokhati.netlify.app/) · [ayushiskhati305@gmail.com](mailto:ayushiskhati305@gmail.com)

</div>
