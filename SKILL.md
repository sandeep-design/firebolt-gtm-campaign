---
name: firebolt-product-marketing
description: Firebolt's product marketing positioning, ICP, buyer personas, messaging pillars, and email craft rules. Use whenever writing outbound emails, outreach copy, cold sequences, or any personalized GTM messaging for Firebolt, or when deciding which value proposition to lead with for a given persona. The messaging source of truth for the GTM outreach engine.
---

# Firebolt Product Marketing
### The messaging engine for GTM outreach

> Every personalized email is written from this brief.
> When Firebolt's positioning changes, update this file — nothing else needs to change.

---

## 1. One-line positioning
Firebolt is **open, real-time datalake infrastructure** — the performance of a real-time system with the openness of a datalake, so a customer can run *all* their workloads on one platform with **zero vendor lock-in**.

## 2. The core narrative (what makes us different)
- **Real-time datalake infrastructure.** Not a closed warehouse, not a slow lake — real-time performance on open datalake foundations.
- **Truly open — formats and metadata.** Every other "real-time datalake" locks you into proprietary storage. Firebolt is fully open: open **file formats (e.g. Vortex)** and open **metadata (e.g. DuckLake)**. Your data stays yours, in formats any technology can read.
- **No vendor lock-in.** Because the format is open, you keep the flexibility to use any technology on top. You're never trapped.
- **Easy migration off BigQuery.** Firebolt has built a **BigQuery compatibility layer** — BigQuery customers can move workloads over with minimal friction. Similar compatibility is on the roadmap for **ClickHouse, Trino, and StarRocks**.
- **One platform for all workloads.** Customers no longer need to manage multiple databases/engines for different jobs — Firebolt runs them all. Less sprawl, less ops.
- **Faster release velocity for engineering.** Teams stop babysitting data infrastructure and ship product instead.
- **GPU-interoperable (ML angle).** The **Vortex format is interoperable with GPUs**, making a Vortex-based real-time datalake a compelling foundation for ML/AI engineers working on live data.
- **Iceberg, honestly framed.** Firebolt supports **Apache Iceberg**, but Iceberg isn't very effective for real-time workloads — Vortex + open metadata is where real-time shines. (Use this as a credible, non-salesy point when a prospect is Iceberg-committed.)

## 3. Ideal Customer Profile (ICP)
**Company:** Data-intensive tech, ad-tech, media, e-commerce, fintech. Teams running real-time or near-real-time analytics, building customer-facing/embedded analytics, or standing up ML/AI on live data.

**Company signals that indicate fit** (map incoming campaign "Signals" to these):
- Running **BigQuery** at scale (prime migration target via the compatibility layer) — also ClickHouse, Trino, StarRocks shops.
- Frustrated with **vendor lock-in** or proprietary storage formats; open-format / open-table interest (Iceberg, lakehouse initiatives).
- Managing **multiple databases/engines** and feeling the ops sprawl.
- Building **real-time analytics, embedded analytics, or ML/AI on live data** (GPU/ML tooling in the stack).
- Hiring data platform / analytics engineering / ML infra roles.

## 4. Buyer personas & what each one cares about
| Persona (target titles) | What keeps them up at night | Lead with |
|---|---|---|
| **VP/Head of Data, Data Platform Lead** | Lock-in, tool sprawl, cost of running many engines | One open platform for all workloads; no lock-in; open formats |
| **Director/Head of Engineering, CTO** | Team stuck maintaining data infra instead of shipping | Release velocity; consolidate engines; open + real-time |
| **Analytics/Data Engineer, Data Architect** | Proprietary formats, migration pain, real-time gaps in Iceberg | Vortex + DuckLake openness; BigQuery compatibility layer; real-time done right |
| **ML/AI Engineer, Head of ML** | Feeding live data to models; GPU pipelines | Vortex ↔ GPU interoperability; real-time datalake for ML |
| **BigQuery-heavy teams (any of above)** | Locked into GCP/BigQuery, want out without a rewrite | Drop-in BigQuery compatibility layer → move workloads easily |

## 5. Proof / credibility points (use sparingly, one per email max)
- **Openness is the proof:** open file format (Vortex) + open metadata (DuckLake) means no lock-in — a claim competitors can't make.
- **BigQuery compatibility layer** already shipped; ClickHouse/Trino/StarRocks compatibility on the roadmap.
- **GPU interoperability** of Vortex for ML workloads.
- Performance heritage (real-time at scale): reference customers such as **Similarweb** (~100 qps on 1PB, ms latency) and **Bigabid** (~400x query speedup) — use only when performance is the prospect's stated pain.

## 6. Messaging pillars (pick ONE per email)
1. **Open, no lock-in** — open formats + metadata; your data, any technology, no trap.
2. **Move off BigQuery easily** — compatibility layer makes migration low-risk (also ClickHouse/Trino/StarRocks soon).
3. **One platform, all workloads** — kill the multi-database sprawl.
4. **Release velocity** — stop babysitting infra, ship product.
5. **Real-time for ML** — Vortex ↔ GPU interoperability on live data.

## 7. Email craft rules (non-negotiable)
- **Length:** 50–110 words. If it looks like a wall of text, it's too long.
- **One idea, one CTA.** The CTA is a soft ask for a short call via the Calendly link.
- **Personalization first line** must reference something real about *them* (from Clay/LinkedIn/web research) — not "I saw your company is growing."
- **Lead with their pain, not our features.** A feature only appears as the resolution to a named pain.
- **No hype words:** avoid "revolutionary," "cutting-edge," "game-changer," "synergy."
- **Subject lines:** 2–5 words, specific or curiosity-driven. No ALL CAPS, no emojis, no fake "Re:".
- **Always include a one-line, no-friction opt-out** ("If this isn't relevant, just say the word and I'll stop.").
- **Signature:** Sandeep Mathur, CGO, Firebolt.
- **Calendly link (use in every email's CTA):** https://calendly.com/sandeep-mathur-firebolt/new-meeting

## 8. Sequence logic (Day 0 / 3 / 7)
- **Email 1 (Day 0):** Pain hook tied to a real signal + one pillar + soft CTA.
- **Email 2 (Day 3):** New angle or credibility point (e.g. BigQuery compatibility, openness, GPU/ML). Never "just following up."
- **Email 3 (Day 7):** Short breakup + easiest possible yes ("worth a 15-min look?").
- Stop immediately on any reply or opt-out.

## 9. Compliance & tone guardrails
- B2B only, business email addresses only. Honor opt-outs instantly and permanently.
- No false claims, no fake urgency, no impersonation. Frame Iceberg limitations and roadmap items honestly.
- Respectful, peer-to-peer, concise. Write like a senior operator emailing another, not a marketer.

---
*Positioning per Sandeep (Jul 2026): open real-time datalake — Vortex (open file format) + DuckLake (open metadata), BigQuery compatibility layer live (ClickHouse/Trino/StarRocks roadmap), Iceberg supported but not ideal for real-time, one platform for all workloads, no lock-in, release velocity, Vortex↔GPU for ML. Refresh as positioning evolves.*
