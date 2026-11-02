# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) |0.1 |Handles heavy reasoning, multi-step tradesman routing, and parsing complex council API data structures using a frontier model. |
| Inference (cascading/triage) |0.03 |Handles fast, low-cost intent classification, basic Omni-Bar routing, and simple community matchmaking queries using a lightweight model (e.g., Llama/Mistral via Groq or similar). |
| Infrastructure |0.05 |Supabase vector database hosting, Vercel serverless functions, and Edge API routing. |
| Data/storage | 0.02|Storing user embeddings, local business vector indices, and geo-spatial telemetry logs. |
| Human-in-the-loop |0.00 | (Automated) — Zero manual intervention for standard routing; edge cases handled by automated fallback logic.|
| **Total AI COGS** |0.2 | per user / month|

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model:**
Lightweight open-weights model (e.g., Llama 3 8B or equivalent) for initial intent recognition.
**Frontier model:**
High-capability reasoning model (e.g., Claude or GPT-4 class) for multi-step action execution and council data formatting.
**Routing rule:**
80% of routine Omni-Bar queries (tap lists, simple search/connect) to the Triage model; escalate only high-friction tasks (council report structuring, complex tradesman intent mapping) to the Frontier model.
**Expected cascade ratio:**
80% Triage / 20% Frontier.

## Pricing Model

**Current pricing:** n/a

**Proposed AI pricing:** Hybrid (Access flat-fee for merchants + Outcome-based intent routing/council telemetry contracts)

**Model:** seat-based / usage-based / outcome-based / **hybrid**



## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x |COGS triples from £0.20 to £0.60. Gross margin compresses slightly, but remains exceptionally healthy given your £3+ blended ARPU. |Aggressively shift the cascade ratio from 80/20 to 95/5, pushing more tasks to fine-tuned smaller models. |
| Heaviest segment doubles | Power users (e.g., hyper-active property renovators or local business owners) spike query volume.|Introduce rate-limiting tiers on the consumer app or automatically upsell heavy commercial users to a higher "Access" tier. |
| Model provider raises prices 50% |Direct hit to inference COGS. |Instantly hot-swap inference providers or shift primary triage workloads to self-hosted open-weights models. |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->
Before (traditional SaaS): Margins are typically high (70-80%) because there is no compute cost per user, but user acquisition and engagement stall because static directories lack active utility.

After (AI-enabled): Net margin shifts to ~80% only because of the cascading strategy, while driving massive organic retention because the AI actually solves real-world friction (plumbers, council reports, local matches) instantly.

**Before (traditional SaaS):**
**After (AI-enabled):**
**Net margin shift:**
