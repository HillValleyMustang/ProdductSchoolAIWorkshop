

# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
| :--- | :--- | :--- | :--- |
| **Provider** | Single primary LLM provider for synthesis & LLM-as-a-judge evals, paired with OpenAI/Supabase embeddings. | **H** | Abstract model endpoints behind a unified gateway (e.g., LiteLLM / Vercel AI SDK) and pre-validate secondary fallback model weights against the 225-row Golden Dataset. |
| **Abstraction** | Direct SDK calls inside Vercel edge functions and Supabase triggers without a standardized prompt/schema wrapper. | **M** | Decouple prompt templates and structured JSON output schemas from provider-specific SDK syntax into provider-agnostic configuration files. |
| **Routing** | Static tier routing (Small edge classifier vs. Mid/Frontier synthesis) hard-coded to primary vendor model IDs. | **M** | Implement dynamic fallback routing rules so traffic automatically fails over to an open-weights or secondary vendor endpoint if latency spikes or rate limits trigger. |
| **Eval** | Automated LLM-as-a-judge CI/CD harness relies on the same vendor family used in production synthesis. | **L** | Configure cross-family judging (e.g., judging Frontier outputs with an independent secondary model) to eliminate self-bias and prevent single-vendor eval lock-in. |

## Portability Score

**3.5 / 5 (Moderate-High Portability)** — Core state, civic vector anchors, and user data live in portable PostgreSQL/pgvector (Supabase) and standard JSON schemas rather than proprietary vendor thread APIs, allowing full model swap within 48 hours once SDK calls are abstracted.

## If OpenAI / Anthropic doubles pricing tomorrow:

* **Immediate Circuit Breaker:** Shift 90%+ of routine `SEARCH` and `CONNECT` synthesis traffic down to smaller, cost-efficient open-weights or secondary-tier models via Vercel edge routing flags, restricting Frontier-tier calls strictly to complex multi-intent municipal `REPORT` formatting.
* **Margin Protection:** Increase semantic caching TTLs in Supabase for repeat N21 queries (e.g., bin collection schedules, Winchmore Hill station disruptions, Green Lanes merchant hours) to cut redundant inference calls by ~40% within 24 hours.

## If OpenAI / Apple ships a competing product:

* **Pivot Away from Generic Chat:** Avoid competing head-on with generic local search or map summaries; double down on deep, authenticated local workflows that Big Tech won't maintain at the postcode level (e.g., pre-filled Enfield Council civic compliance payloads, verified N21 tradesman pricing benchmarks, and human-governed street-level community trust).
* **Accelerate H2 Shadow Features:** Immediately ship native workflow shortcuts identified in our Shadow AI Audit—such as one-click formal council complaint drafting and multi-stop Winchmore Hill errand itineraries—locking in daily utility habits before platform defaults reach N21.
