# Changelog

## [0.3.0] - 2026-02-14

### Added
- **SDAM Model**: Powell's Sequential Decision Analytics framework for governance scenarios
  - Maps the 5 SDAM elements (State, Decision, Exogenous Info, Transition, Objective) to CISO decision problems
  - PFA Policy (threshold rules) and CFA Policy (parameterized optimization)
  - Monte Carlo simulation: CFA outperforms PFA in 200/200 scenarios
  - Policy search via grid optimization
  - Community data pipeline: load Arena game exports → SDAM episodes → batch analysis
- **Expanded OPA Policies**: 12 deny rules, 5 modification rules, risk scoring, policy metadata
  - Healthcare pack (PHI keywords, aggregate PII detection)
  - Finance domain enforcement, content volume limits
  - Bearer/access/refresh token detection
  - Community scenario schema validation
- **20 OPA test cases** (was 10)
- **Folder README files**: dual-audience documentation for all directories
- **community_data/ directory**: Arena export collection point with SDAM integration

### Changed
- Version bump from 0.2.0 to 0.3.0

## [0.2.0] - 2026-02-14

### Added
- Rebranded from Claw to AGORA — "Collective intelligence for the governance problems no one should solve alone"
- Decision Arena game (agora-arena.html) — standalone interactive HTML
- Nuclear False Positive scenario (nfp-001) with multi-constitutional ethical tensions
- Vedic Dharmic constitutional framework (vedic-dharmic.json)
- Scenario template for community contributions
- CONTRIBUTING_SCENARIOS.md guide
- Community governance documentation (GOVERNANCE.md)
- arena/scenarios/ and arena/frameworks/ directory structure

### Inherited from Claw v0.2.0
- 6-stage governance pipeline (PII → OPA → Knowledge Hub → Argumentation → Assembly → Inference)
- Knowledge Hub with temporal decay and domain reputation
- Argumentation Engine (Dung's AAF — grounded, preferred, stable extensions)
- Rego Bridge for OPA-to-AAF conflict resolution
- 28 Python tests, 10 OPA tests, CI/CD pipeline
- Security: API auth, rate limiting, CORS, non-root Docker

## [0.1.0] - 2026-02-11

### Origin
- Claw v0.1.0 — 4-stage pipeline (PII → OPA → Assembly → Inference)
- OPA policy packs (standard/finance/strict/research)
- Firefox extension, audit logging, Docker Compose
