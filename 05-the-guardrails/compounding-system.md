# Compounding System Design

## Feedback Loops

## Compounding System Architecture

Map your product's compounding architecture, which loops learn, which just scale, and where the gap between them creates vulnerability[cite: 5].

### Loop Matrix

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Live user queries failing LLM-as-a-judge scoring on N21 slang/typos | Automated generation of 8 semantic test variants added to GitHub Golden Dataset | Y | active |
| Cross-Domain Transfer | Enfield Council API schema rejections & dropped telemetry payloads | Dynamic adjustment of Vercel edge validation rules & routing confidence thresholds | Y | active |
| Network Intelligence | Resident reports on Green Lanes & Ringwood Way combined with merchant pings | Automated synchronization of verified local merchant vector anchors in Supabase | Y | active |

**Broken loop identified by partner:** Cross-Domain Transfer between external municipal API telemetry updates and static local merchant vector anchors.
**Fix plan:** Supabase database webhooks that automatically trigger vector re-indexing whenever municipal status changes or merchant profile updates occur, eliminating manual data grooming.

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** Between dynamic external council/Google API endpoints and static proprietary N21 community datasets.

**Where it silos:** A unified Vercel edge runtime middleware that merges real-time external API payloads with Supabase vector anchor lookups into a single, cohesive prompt context window before inference.

| | | | Y/N | active / broken / missing |

**Broken loop identified by partner:**
**Fix plan:**

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

## Governance Policy

**Scope:**
**Autonomy boundaries:**
**Escalation triggers:**
**Audit cadence:**
**Regulatory exposure (EU AI Act / other):**

## Agent Topology
<!-- If using agents: what can each agent do? What can't it do? Who approves what? -->

## Shadow AI Audit

| Tool | Owner | Risk Level | Decision |
|------|-------|-----------|----------|
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |
| | | H / M / L | keep / govern / kill |

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**


# WiHi (Radius21) AI Governance Policy
*Target: One-page operational compliance for N21 local utility routing, civic reporting, and merchant network nodes.*

---

### 1. Scope
* **What this policy covers:** All AI routing models, Vercel edge functions, Supabase vector databases, automated LLM-as-a-judge evaluation pipelines, and third-party API payload integrations (Enfield Council, Google Places, TfL) deployed within the WiHi N21 community platform.

### 2. Autonomy Boundaries & Emergency Hard-Stops
* **OK solo (Autonomous execution):** 
  * Standard local utility routing (`SEARCH`, non-emergency `REPORT`, `CONNECT`).
  * Factual retrieval from verified N21 civic metadata and vector anchor databases.
  * Formatting and synthesizing live external JSON payloads from approved municipal APIs.
  * Automated synthetic test variant generation for the CI/CD evaluation harness.
  * Generating pre-filled municipal report payloads and draft text templates (leaving final user review and click-to-submit to the resident).
* **Needs human / System hard-stop:**
  * **Emergency & Crisis Intercepts (Zero Autonomy):** Any prompt or input containing emergency descriptors (e.g., gas leaks, active fires, violent crimes, or medical emergencies requiring 999 or 111). The system must completely bypass normal municipal ticket generation and instantly display a hard-stop advisory screen directing the user to dial emergency services immediately.
  * **Direct Council Ticket Submission:** Prevention of automated ticket creation from the user to ensure that the council is not spammed with tickets which are not sent with consideration and human interaction
  * **Direct Data Modifications:** Writing directly to core Supabase user tables or merchant subscription records without explicit authorization gates.

### 3. Escalation Triggers
* **When humans must enter:**
  * **Safety & Security Intercepts:** Any prompt triggering adversarial guardrails, prompt injection attempts, or systemic data exfiltration flags.
  * **Emergency Dispatch Intercepts:** Automatic routing to emergency advisory protocols for 999/111 scenarios.
  * **Low Confidence Routing:** Any user query scoring below the Vercel edge runtime confidence threshold, requiring fallback clarification prompts or human moderation review.

### 4. Audit Cadence
* **How often we review:** 
  * **Real-time:** Continuous automated LLM-as-a-judge scoring on every pull-request and CI/CD deployment against the 225-row Golden Dataset.
  * **Daily:** Automated log aggregation of Vercel edge traces and Supabase evaluation telemetry.
  * **Weekly:** Human-in-the-loop review of flagged edge cases, false-positive refusals, and routing drift anomalies.
  * **Monthly / Quarterly:** Full systematic re-evaluation of tier-routing costs, latency thresholds, and API rate-limit compliance.

### 5. Regulatory Exposure (EU AI Act / GDPR / Sector)
* **Regimes that apply:** 
  * **UK GDPR & Data Protection Act 2018:** Strict handling of user chat logs, PII, and merchant subscription data.
  * **EU AI Act Alignment:** Classified as a **Limited Risk** generative utility interface, requiring transparency notices when users interact with AI routing agents and robust technical documentation against hallucinations.
  * **Local Municipal Compliance:** Adherence to Enfield Council digital service integration standards for civic reporting telemetry.
* **Risk tier:** `limited`

---

### Agent Topology
* **What each agent can do:**
  * *Router Agent (Small Tier / Edge):* Classifies incoming user intent (`SEARCH`, `REPORT`, `CONNECT`), detects multi-lingual inputs, and screens for prompt injection or emergency overrides.
  * *Synthesis & Formatting Agent (Mid/Frontier Tier):* Merges live external API JSON payloads with local Supabase vector anchors to construct clean UI cards and structured municipal report payloads.
* **What it can't do:**
  * Execute unvalidated SQL queries, modify database schemas, bypass safety guardrails, or automatically submit official council enforcement tickets without user interaction.
* **Who approves:**
  * System administrators and engineering leads review CI/CD evaluation gate passes, model weight adjustments, and Supabase security policy updates.
