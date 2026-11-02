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

| Feature | Complexity | Model Tier | Cost/Req | Volume % | Weighted |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Omni-Bar Natural Language Routing** | Simple | Small | £0.0015 | 40% | £0.0006 |
| **Local Business & Tap List Lookups** | Simple | Small | £0.0015 | 20% | £0.0003 |
| **Basic Utility Status Checks** | Simple | Small | £0.0015 | 10% | £0.00015 |
| **R21 Vector Matchmaking Engine** | Medium | Mid | £0.0115 | 10% | £0.00115 |
| **Tradesman Reputation Scoring** | Medium | Mid | £0.0115 | 5% | £0.000575 |
| **Civic Status Tracking** | Medium | Mid | £0.0115 | 3% | £0.000345 |
| **Local Event Matching** | Medium | Mid | £0.0115 | 2% | £0.00023 |
| **Civic Report Structuring & API Formatting** | Complex | Frontier | £0.046 | 6% | £0.00276 |
| **Multi-Step Tradesman Dispatch Coordination** | Complex | Frontier | £0.046 | 3% | £0.00138 |
| **Municipal Data Aggregation & Telemetry Formatting** | Complex | Frontier | £0.046 | 1% | £0.00046 |
| **Blended Total** | | | | **100%** | **£0.00795** |

**How this breaks down:**
Small Tier Features (Total Volume: 70%): Dominated heavily by the Omni-Bar parser since every single app interaction starts there.
Mid Tier Features (Total Volume: 20%): Split across vector matching, contractor reputation queries, and event filters.
Frontier Tier Features (Total Volume: 10%): Concentrated tightly on high-value, complex data structuring (council reports and automated trade booking handshakes).

That pricing assumption sits comfortably in the medium-to-low range—meaning it is lean, highly realistic, and optimized for modern inference providers, but it leaves zero room for architectural bloat.

Here is how those figures stack up against industry realities:

The Small Tier (£0.0015 / ~£0.002 per request): Medium/Low. This is entirely achievable if you are routing routine Omni-Bar strings through efficient open-weights models (like Llama 3 8B) hosted via fast, low-cost inference providers or optimized edge functions. If you tried to route everything through a flagship proprietary model, this would be dangerously low; with a proper triage model, it is spot on.

The Mid Tier (£0.0115 / $0.015 per request): Medium. Vector embedding lookups and multi-attribute matchmaking require a bit more context window and reasoning, putting the cost right where standard mid-tier APIs sit.

The Frontier Tier (£0.046 / $0.060 per request): Medium-High per request, but low in volume. At roughly 4.6p per call, this assumes you are hitting a heavy reasoning model (like Claude or GPT-4 class) for complex data structuring. However, because you've tightly restricted this tier to just 10% of your total volume (civic reports and automated trade contracts), your overall risk is heavily mitigated.

The Verdict:
Because your blended cost is roughly 0.8p per request, your unit economics are extremely healthy. As long as your cascading strategy holds and you don't let complex reasoning tasks bleed into your 70% triage volume, you won't get blindsided by your cloud bill.
