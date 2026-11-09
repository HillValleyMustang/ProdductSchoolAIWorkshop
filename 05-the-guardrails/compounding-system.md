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

# WiHi (Radius21) Shadow AI Audit
*Target: Identifying user workarounds, classification signals, operational frequencies, and build/partner/ignore decisions for N21 community utility flows.*

---

## Audit Table

| Workaround | Signal | Frequency | Decision |
| :--- | :--- | :--- | :--- |
| **1. Copying WiHi's local council report text and pasting it into external LLMs to rewrite it into formal legal complaints about repeat missed bin collections.** | `workflow` | High | **build** (Add a built-in "Formalize Complaint" tone selector directly into the reporting module). |
| **2. Taking WiHi merchant search results and pasting them into ChatGPT to build structured weekend errand or shopping itineraries around Green Lanes.** | `workflow` | Medium | **build** (Introduce a native "AI Itinerary / Errand Planner" for local Winchmore Hill stops). |
| **3. Taking WiHi social connection prompts (like tennis partners or running groups) and using external AI tools to draft multi-person scheduling polls.** | `capability` | Medium | **ignore** (Too niche; best left to external chat apps once the initial connection is made). |
| **4. Exporting WiHi local tradesman recommendations and running them through external chat tools to cross-reference fair pricing benchmarks in N21.** | `trust` | Medium | **partner** (Embed estimated local pricing tier indicators directly into the tradesman directory). |
| **5. Pasting WiHi community noticeboard alerts into external chat apps to translate them into different languages for non-English speaking family members.** | `capability` | Low | **ignore** (Already covered by WiHi's native multi-lingual edge translation pipeline). |

---

## Audit Summary & Strategic Actions

### Build Candidates
* **Formalized Complaint Generator:** Streamline civic reporting by allowing users to instantly refine municipal feedback text without relying on external chat windows.
* **Local Errand Itinerary Planner:** Convert raw merchant search results into structured, chronological neighborhood stops along Green Lanes and Winchmore Hill Green.

### Partner Integrations
* **Tradesman Pricing & Trust Benchmarks:** Integrate verified external metrics to boost trust in local recommendations.

### Ignored Workarounds (Out-of-Scope)
* P2P scheduling polls and translation workarounds remain excluded from direct product scope because external chat apps already solve scheduling and WiHi's native multi-lingual edge translation already handles language barriers.

Stack & Spend Metrics

Total tools found: 14 (across Vercel edge functions, Supabase vector triggers, React Native UI components, Enfield Council APIs, TfL live feeds, Google Places endpoints, GitHub CI/CD evaluation harnesses, and external resident chat/translation apps).

Tools after triage: 6 (retaining core Vercel routing edge runtime, Supabase vector anchors, automated LLM-as-a-judge CI/CD evaluation pipeline, official council API gateway, native multi-lingual translation service, and local merchant directory sync engine).

Estimated hidden spend: £280 / mo (driven by external municipal API rate-limit overages, high-frequency LLM-as-a-judge evaluation token consumption during synthetic variant generation, and Vercel edge execution spikes).

Strategic Takeaway

By capturing these workarounds and tracking hidden spend in GBP, WiHi avoids redundant feature development while funding high-value additions—such as native formal-complaint formatting—that keep local residents inside the platform rather than migrating to generic chat wrappers.


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
 
  
