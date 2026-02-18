# AGORA

### Collective intelligence for the governance problems no one should solve alone.

---

> *In ancient Athens, the Agora was not a building. It was an agreement — that any citizen could stand in the open square, present an argument, and have it weighed on its merits. No rank. No privilege. Just the strength of your reasoning.*
>
> *Security governance deserves the same promise.*

---

## The Problem No One Talks About

Every day, a CISO makes decisions that ripple across millions of lives. Block this domain. Allow that access. Override a policy because a hurricane just knocked out three data centers and the backup authentication server is in the flood zone.

These decisions are **sequential**. Each one reshapes the landscape for the next. And they happen under conditions that no policy document ever anticipated.

We write static rules for a dynamic world. We build access control systems that work perfectly — until the moment they encounter something extraordinary. And in that moment, the human behind the console is alone with a decision that has no good answer.

**AGORA exists because those moments shouldn't be faced alone.**

---

## What Is AGORA?

AGORA is an open-source governance engine and **Decision Arena** where security professionals, researchers, and anyone who cares about how decisions get made can come together to reason about the hardest problems in AI and security governance.

At its core, AGORA is three things:

### 🏛️ A Governance Engine

A 6-stage pipeline that sits between your systems and your AI, enforcing access control through formal argumentation — not just static rules.

```
 Your System
      │
      ▼
┌─────────────────────────────────────────────┐
│                                             │
│   1. PII Scan ──────── detect & mask        │
│   2. Policy Gate ────── OPA/Rego ABAC       │
│   3. Knowledge Hub ──── domain memory       │
│   4. Argumentation ──── Dung's AAF          │
│   5. Context Assembly ─ prompt enrichment   │
│   6. Model Inference ── risk analysis       │
│                                             │
│   Every decision logged. Every argument     │
│   traceable. Every override justified.      │
│                                             │
└─────────────────────────────────────────────┘
```

When policies conflict — and they will — AGORA doesn't pick the loudest rule. It constructs a formal **argumentation framework** where arguments attack and defend each other based on evidence, strength, and context. The winning position emerges from the logic itself.

This is how Dung's Abstract Argumentation Frameworks (1995) work. This is how the Nyaya school of Indian logic formalized debate thousands of years before that. AGORA brings both traditions into your governance stack.

### ⚔️ A Decision Arena

The Arena is where the community comes alive. Real-world governance scenarios — contributed by CISOs, researchers, red teams, ethicists, anyone — become interactive challenges where you navigate sequential decisions under pressure.

**How it works:**

You start with a scenario. A nuclear facility's monitoring system flags a potential false positive. A pandemic response AI needs to reallocate ventilators while under cyber attack. A whistleblower's identity is about to be exposed by an automated compliance report.

Each decision you make feeds into the argumentation engine. The framework shifts. New arguments emerge. Previous certainties get defeated. You see, in real-time, how your reasoning holds up — not against a test suite, but against formal logic.

Your decisions are scored. Your frameworks are preserved. The community learns from every path taken.

### 🌍 A Research Collective

AGORA is built on the conviction that the hardest governance problems sit at the intersection of traditions no single person masters alone. We draw from:

- **Dung's AAF & ASPARTIX** — formal argumentation semantics (grounded, preferred, stable extensions)
- **OPA/Rego & ABAC** — attribute-based access control as declarative policy
- **Vedic Logic (Nyaya/Tarka)** — millennia of formalized debate and valid reasoning
- **Confucian Ethics** — role-based obligations and contextual harmony
- **Islamic Jurisprudence (Ijtihad)** — independent reasoning when precedent fails
- **Western Liberal Tradition** — rights-based frameworks and adversarial testing
- **Powell's SDAM** — Sequential Decision Analytics for modeling decisions that unfold over time

No single tradition has the complete answer. The governance problems of the AI age demand **multi-constitutional reasoning** — and AGORA is where those constitutions meet, argue, and forge something stronger together.

---

## Quick Start

### Run the Engine

```bash
git clone https://github.com/Leeladitya/agora.git
cd agora
cp .env.example .env          # add your ANTHROPIC_API_KEY
docker compose up              # starts OPA + AGORA server
```

### Try the Decision Arena

The Arena is a standalone interactive experience. Open it directly in your browser — no server required:

```bash
# Open the nuclear false positive scenario
open arena/agora-arena.html        # macOS
xdg-open arena/agora-arena.html   # Linux
```

Navigate 3 stages of sequential decisions under 12-minute pressure. Watch the argumentation framework shift in real-time. Export your playthrough to JSON for community analysis.

### Try the Governance Engine

The server exposes the full 6-stage pipeline via API:

```bash
# Full pipeline analysis (PII → Policy → Knowledge → Argumentation → Assembly → Inference)
curl -X POST http://localhost:8787/v1/analyze \
  -H "Content-Type: application/json" \
  -d '{"content": "Contact john@example.com at 555-0123", "url": "https://example.com"}'

# Zero-cost dry run — stages 1-4 only, no model call
curl -X POST http://localhost:8787/v1/policy/evaluate \
  -H "Content-Type: application/json" \
  -d '{"content": "Patient MRN 12345 diagnosis: pneumonia", "url": "https://hospital.org"}'

# Check a domain's reputation from the Knowledge Hub
curl http://localhost:8787/v1/knowledge/reputation/example.com
```

### Install the Browser Extension (Firefox)

1. Navigate to `about:debugging#/runtime/this-firefox`
2. Load Temporary Add-on → `extension/manifest.json`
3. Click the AGORA icon on any page → **Scan & Analyze**

The extension runs the full 6-stage pipeline against any web content — PII detection, policy evaluation, knowledge lookup, argumentation resolution, and AI risk analysis — all before anything reaches the model.

---

## The Argumentation Engine

This is the heart of AGORA. When policies conflict, the engine doesn't pick winners by priority number. It reasons.

**The Rego-to-AAF Bridge** converts your policy world into a formal argumentation framework:

| Source | Becomes | Strength |
|--------|---------|----------|
| OPA deny rule | Deny argument | 0.9 |
| Critical PII (SSN, credit card) | Deny argument | 0.95 |
| OPA modification rule | Modify argument | 0.7 |
| Knowledge Hub "trusted" entry | Trust argument (attacks deny) | varies |
| Knowledge Hub "suspicious" entry | Suspicion argument (attacks allow) | varies |
| Baseline | Allow argument | 0.3 |

Stronger arguments attack weaker ones when decisions conflict. The engine computes:

- **Grounded extension** — the unique, most skeptical position. What survives when you doubt everything you can. This is the default for security decisions.
- **Preferred extensions** — maximal admissible sets. Every defensible worldview.
- **Stable extensions** — complete coverage. No argument left unaddressed.

The CISO sees not just a decision, but the **argument map** — which positions won, which were defeated, and why.

---

## Knowledge Hub

AGORA remembers. Every domain it evaluates builds a reputation over time through a persistent Knowledge Hub:

- Decisions are stored with domain, outcome, matched rules, and timestamp
- Temporal decay (1-week halflife) ensures recent knowledge weighs more than stale memory
- Domain reputations aggregate as: **trusted**, **suspicious**, **mixed**, or **unknown**
- Knowledge entries feed directly into the argumentation engine as contextual arguments

This means AGORA's second decision about a domain is better than its first. Its hundredth is better still. The system learns — not through opaque neural weights, but through **auditable, arguable knowledge**.

---

## Community Pillars

AGORA is not a product. It's infrastructure for collective reasoning. The community is built on five pillars:

### 📚 Open Scenario Library

Anyone can contribute a governance scenario. A real incident you navigated. A hypothetical that keeps you up at night. An edge case your policy framework can't handle.

Scenarios live in `arena/scenarios/` as structured JSON. Each includes the situation, available decisions, ethical tensions, and the argumentation framework that emerges.

**[→ How to contribute a scenario](docs/CONTRIBUTING_SCENARIOS.md)**

### 🏆 Decision Leaderboard

When you navigate a scenario in the Arena, your decisions are scored against formal criteria: consistency, proportionality, reversibility, auditability, and how well your argumentation framework holds under adversarial examination.

Over time, the community builds a collective picture of which governance approaches work — not in theory, but under pressure.

### 🔬 Research Collective

AGORA is a launchpad for research. The argumentation engine, the multi-constitutional debate mechanism, the CISO decision modeling — all of it is publishable, forkable, and built to be extended.

We actively seek co-authors. If you're working on formal argumentation, AI governance, ABAC, Prolog-style reasoning, or cross-cultural ethics in computing — this is your home.

### 🌐 Multi-Constitutional Debate

The hardest governance problems don't have answers within a single ethical tradition. AGORA's framework supports loading multiple "constitutions" — ethical frameworks drawn from different traditions — and letting them argue.

What does Vedic dharma say about overriding access control during an emergency (apad-dharma)? How does that argument fare against a Kantian categorical imperative? What would Islamic ijtihad conclude when no precedent exists?

These aren't academic exercises. They're the actual tensions that surface when you govern AI systems used across cultures.

### 🔓 Decentralization & Open Source

AGORA's source is open. Its scenarios are open. Its argumentation frameworks are open. Because governance decisions that affect everyone should be reasoned about by everyone.

The code is MIT licensed. The scenarios are CC-BY-SA. The research is for the commons.

---

## Security Architecture

| Layer | Mechanism |
|-------|-----------|
| Authentication | Bearer token, constant-time comparison |
| Rate Limiting | Per-IP token bucket (30-60 req/min) |
| CORS | Configurable allowlist, no wildcards |
| Input Validation | Max content size enforcement |
| PII Masking | SSN, credit card, email, phone, IP detection |
| Policy Gate | OPA/Rego attribute-based access control |
| Argumentation | Formal conflict resolution via Dung's AAF |
| Audit Trail | Immutable JSONL decision log |

See [SECURITY.md](SECURITY.md) for vulnerability disclosure and full architecture.

---

## API Reference

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/v1/analyze` | Full 6-stage pipeline |
| `POST` | `/v1/policy/evaluate` | Dry-run (stages 1-4, no model call, zero cost) |
| `GET` | `/v1/policy/packs` | List policy packs |
| `POST` | `/v1/knowledge/store` | Store a knowledge entry |
| `POST` | `/v1/knowledge/query` | Query Knowledge Hub |
| `GET` | `/v1/knowledge/reputation/{domain}` | Domain reputation |
| `GET` | `/v1/knowledge/stats` | Hub statistics |
| `GET` | `/v1/audit/decisions` | Audit trail |
| `GET` | `/v1/health` | Component health |

---

## Project Structure

```
agora/
├── server/                         # Governance Engine
│   ├── app.py                      #   FastAPI, 6-stage pipeline
│   ├── middleware/                  #   Auth, rate limiting, PII, OPA
│   ├── knowledge/                  #   Knowledge Hub (JSONL-backed)
│   ├── argumentation/              #   Dung's AAF engine + Rego bridge
│   └── utils/                      #   Audit logging
├── opa/                            # Policy Layer
│   ├── policies/                   #   Rego rules + tests
│   └── data/                       #   Domain lists, config
├── arena/                          # Decision Arena
│   ├── scenarios/                  #   Community-contributed scenarios
│   └── frameworks/                 #   Constitutional frameworks
├── extension/                      # Browser Extension (Firefox)
│   ├── content/                    #   DOM extraction
│   └── popup/                      #   UI (knowledge + argumentation)
├── community/                      # Community Infrastructure
├── docs/                           # Guides & research
├── tests/                          #   65 test cases (28 pipeline + 37 SDAM)
├── .github/workflows/ci.yml       # CI/CD pipeline
├── Dockerfile                      # Non-root container
├── docker-compose.yml              # OPA + AGORA orchestration
└── requirements.txt                # Pinned dependencies
```

---

## Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `ANTHROPIC_API_KEY` | *(required)* | Claude API key |
| `CLAW_MODEL` | `claude-sonnet-4-5-20250514` | Model for analysis |
| `CLAW_POLICY_PACK` | `standard` | Active policy pack |
| `CLAW_API_KEYS` | *(empty = auth off)* | API keys (comma-separated) |
| `CLAW_CORS_ORIGINS` | localhost + extensions | CORS allowlist |
| `CLAW_MAX_INPUT_CHARS` | `60000` | Max input size |

---

## Development

```bash
pip install -r requirements.txt

# Run tests
pytest tests/ -v                              # 65 Python tests (28 pipeline + 37 SDAM)
opa test opa/policies/ opa/data/ -v           # 20 OPA policy tests

# Lint
ruff check server/ tests/
```

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full development guide.

---

## Intellectual Lineage

AGORA stands on the shoulders of traditions that span millennia and continents:

- **Dung, P.M. (1995)** — "On the acceptability of arguments" — the foundational paper on abstract argumentation frameworks
- **Nyaya Sutras** — Indian logic tradition formalizing valid reasoning, debate structure, and epistemic warrant
- **Open Policy Agent** — declarative policy-as-code that makes ABAC programmable
- **ASPARTIX** — answer-set programming for argumentation, computing extensions via logic programming
- **Powell's SDAM** — Sequential Decision Analytics and Modeling for decisions that unfold over time
- **Prolog & Logic Programming** — the computational tradition that makes formal reasoning executable

---

## Join the Agora

This is an open square. The only credential you need is a willingness to reason honestly.

- **Contribute a scenario** — What's the hardest governance decision you've faced? [Template →](arena/scenarios/TEMPLATE.json)
- **Challenge a framework** — Load a constitutional perspective and test it against the Arena
- **Publish with us** — We're building toward papers on formal governance. Co-authors welcome.
- **Build on the engine** — The argumentation core is designed to be embedded. Take it somewhere we haven't imagined.

**Start a discussion. Open an issue. Submit a scenario. The Agora is open.**

---

<p align="center">
<em>Security is not a policy. It's an argument you must win.<br/>
Win it together.</em>
</p>

---

**License:** MIT (code) · CC-BY-SA 4.0 (scenarios & research)

**Maintained by:** [saatvix.com](https://saatvix.com)
