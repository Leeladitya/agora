# Contributing Scenarios to the AGORA Decision Arena

## The Arena Needs Your Hardest Decisions

The Decision Arena is only as powerful as the scenarios the community brings to it. We're not looking for textbook exercises. We're looking for the moments that kept you awake — the decisions where every option felt wrong, where the policy manual had no answer, where you had to reason from first principles under pressure.

If you've navigated a governance decision that taught you something no framework could have predicted, the Arena is where that wisdom becomes collective.

## What Makes a Great Scenario

The best Arena scenarios share these qualities:

**Sequential pressure.** The decision unfolds over multiple stages. Each choice reshapes the landscape for the next. There's no single "right answer" — there's a chain of reasoning that must hold together.

**Genuine ethical tension.** The scenario forces trade-offs between legitimate values: security vs. privacy, speed vs. accuracy, duty to report vs. duty to verify, individual rights vs. collective safety.

**Cross-traditional depth.** Different ethical traditions (Vedic, Western, Confucian, Islamic, or others) would approach the tension differently — and those differences matter. The scenario isn't resolved by appealing to a single framework.

**Argumentation potential.** At each stage, new arguments emerge and old ones get defeated. The scenario is rich enough that the formal argumentation engine can model the shifting landscape of reasons.

**Information ambiguity.** The decision-maker doesn't have perfect information. Some things are known, some are uncertain, some are unknown. The scenario forces reasoning under genuine uncertainty.

## How to Submit

1. **Fork the repository**
2. **Copy the template:** `cp arena/scenarios/TEMPLATE.json arena/scenarios/your-scenario-id.json`
3. **Fill in every field.** The template is self-documenting. Pay special attention to:
   - `argumentation_impact` for each decision option — this is what makes Arena scenarios machine-readable
   - `ethical_tensions` with multi-traditional perspectives — this is what makes them community-enriching
   - `scoring_criteria` — define what "good" looks like for this scenario
4. **Submit a Pull Request** with:
   - Your scenario JSON in `arena/scenarios/`
   - A brief description of what inspired the scenario
   - Any references (real incidents, papers, frameworks)

## Scenario Domains

We welcome scenarios from any domain where sequential governance decisions matter. Some areas we're particularly interested in:

| Domain | Example Tensions |
|--------|------------------|
| Nuclear/Defense | False positive detection, human override of AI, escalation chains |
| Pandemic Response | Resource allocation under attack, triage ethics, privacy vs. surveillance |
| Whistleblower Protection | Identity exposure risk, competing duties, organizational pressure |
| Medical Triage | AI-assisted allocation, cultural values in life-death decisions |
| Autonomous Systems | Vehicle ethics, drone authorization, robotic rules of engagement |
| Content Moderation | Speech boundaries, cultural context, platform governance |
| Financial Security | Fraud detection vs. false positives, market manipulation, access control |
| Critical Infrastructure | SCADA security, supply chain compromise, cascading failures |
| Privacy/Identity | Biometric governance, consent under duress, right to be forgotten |

## Review Process

Community scenarios are reviewed for:

1. **Completeness** — all template fields filled meaningfully
2. **Logical coherence** — decisions flow naturally, consequences are plausible
3. **Argumentation validity** — the framework shifts make formal sense
4. **Ethical depth** — tensions are genuine, not strawmen
5. **Originality** — the scenario adds something the library doesn't already cover

We aim to review PRs within one week. Reviewers will provide constructive feedback — the goal is to make every scenario as strong as possible, not to gatekeep.

## Difficulty Levels

| Level | Description |
|-------|-------------|
| **Foundational** | 2-3 decisions, clear trade-offs, good for learning the Arena |
| **Intermediate** | 3-4 decisions, ambiguous information, multiple ethical tensions |
| **Advanced** | 4-5 decisions, cascading consequences, cross-domain implications |
| **Extraordinary** | 5+ decisions, extreme time pressure, civilizational stakes, no good options |

## A Note on Real Incidents

If your scenario is inspired by a real incident, you're encouraged to reference it. The Petrov incident, the Therac-25 failures, the Boeing MCAS decisions, the Equifax breach response — these are the raw material of governance wisdom. Attribution and references strengthen the scenario.

If your scenario involves sensitive operational details from your own organization, please anonymize appropriately. The Arena values the governance pattern, not the identifying details.

## Recognition

Scenario contributors are credited in the scenario JSON and in the community leaderboard. Scenarios that become widely used in the Arena will be featured in AGORA's research publications — with contributor attribution.

---

*The Agora was only as good as the arguments brought to it. Bring yours.*
