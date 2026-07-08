# Campaign 01 — Ledger
**Campaign:** BigQuery cost / drop-in replacement
**Sender:** sandeep@send.firebolt.io · **Day 0 sent:** 2026-07-03
**Follow-ups:** Day 3 → 2026-07-06 · Day 7 → 2026-07-10 (skip anyone who replied/opted out)

| Prospect | Title | Company | Email | Status | Day-0 threadId |
|----------|-------|---------|-------|--------|----------------|
| Pallavi Agarwal | VP Engineering | Nextdoor | pallaviagarwal@nextdoor.com | sent_2 | e98e51aa-4678-4ac9-9dfa-4d8aa463399c |
| Vandana Mohan | Head of Data | Nextdoor | vmohan@nextdoor.com | sent_2 | d1f88999-3b46-4d33-8c68-a6d9c4b8d8bb |
| Chris Patalano | CTO | Thumbtack | cpatalano@thumbtack.com | sent_2 | f9cbb5ee-a590-4e57-a5e0-ee69c932ae0e |
| Luke Phan | Head of Data Engineering | Gusto | luke.phan@gusto.com | sent_2 | 64a0680a-b3b0-4769-8b02-119fe01e4793 |
| Chris Ferguson | Head of Data Platform | Gusto | chris.ferguson@gusto.com | sent_2 | dd512840-e503-4acc-907e-033041bf210a |
| Gene Drabkin | VP Engineering | Gusto | gene.drabkin@gusto.com | sent_2 | eaa96530-7f42-45b0-b17b-0a3dd4a26941 |
| Bharathy S. | VP Data Engineering | Chime | bs@chime.com | sent_2 | 5a0b6075-a896-4de7-be68-390d9b210afb |
| Amit Kumar | Director Data Engineering | Chime | amit.kumar@chime.com | sent_1 | 1d66b024-741c-414b-a8c4-488ff3e35bad |
| Nirmal Selvaraj | VP Engineering, Growth | Chime | nirmal.selvaraj@chime.com | sent_2 | 8fc9e617-9dd3-4923-9a2f-04013a526d30 |
| Jeff Currier | CTO | Chime | jcurrier@chime.com | sent_2 | 931699c3-c261-4db7-b414-6d548f5ef398 |
| Anil Puli | Head of BI / Data Eng | Chime | anil.puli@chime.com | sent_2 | 4856ee9c-4e7c-4cb1-8f51-74d69fe34faa |
| Juan J. Aguirre | Staff Data Eng Manager | Gusto | juan.aguirre@gusto.com | sent_1 | 1f3d172e-d9a5-4bbb-b98a-ab39966f76a8 |

**Reply sweep 2026-07-03:** 1 auto-reply only — Amit Kumar (Chime) Out-of-Office. Not a human reply → sequence continues, no lead, no suppression. 0 genuine replies, 0 opt-outs, 0 leads.

**Follow-up (Email 2) sent 2026-07-08 — WITH CORRECTION:** the automated 07-08 run drafted the 10 follow-ups correctly but mis-addressed them all to `sandeep@` (reply-to-self bug) — prospects did NOT receive them. They were re-sent the same day (~14:00 UTC) to the correct prospects, threaded onto Day-0, with `To:` verified = prospect. The 10 are now **sent_2**; next step is Day-7 (Email 3, breakup). Amit Kumar (OOO) and Juan J. Aguirre (email unresolved) were NOT in this batch and remain sent_1. Root-cause bug fixed in the skill (explicit `To:` + post-send check). Laptop `gtm-daily-maintenance` engine stopped; migrating to a cloud routine (`Firebolt GTM Daily`, 8 AM PT). Updates now post to Slack #sandeep-claude-outbound-campaign.

## Rules for the daily maintenance task
- **Reply → stop sequence** (cancel Day-3/Day-7), create Salesforce lead, surface to Sandeep.
- **Opt-out → suppress permanently**, no lead.
- **No reply → send Day-3 (2026-07-06) then Day-7 (2026-07-10)** follow-ups into the same thread; new angle each time (BigQuery compatibility layer / open formats / one platform / Vortex-GPU).
- Juan Aguirre: send Day-0 once his email resolves (then his Day-3/Day-7 shift accordingly).

## Warmup
Day-0 volume, first send day: 12 (within week-1 cap ~15–20).

---

## Wave 2 — SENT 2026-07-05 (from sandeep@) · one-time task now disabled
Day-3 → 2026-07-08 · Day-7 → 2026-07-12 (handled by daily engine). All 8 status: sent_1.

| Prospect | Title | Company | Email | Status |
|----------|-------|---------|-------|--------|
| Evan Ettinger | VP Eng, Reddit Ads | Reddit | evan.ettinger@reddit.com | queued |
| Matthew Snelham | VP Eng, Infra & Core Platforms | Reddit | matthew.snelham@reddit.com | queued |
| Meghana Narasimhan | Data Engineering Leader | NerdWallet | mnarasimhan@nerdwallet.com | queued |
| Bryan Downs | VP Engineering | NerdWallet | bd@nerdwallet.com | queued |
| Amy Aldredge | Data Engineering Manager | NerdWallet | aaldredge@nerdwallet.com | queued |
| Utkarsh Sengar | VP Engineering | Webflow | utkarsh.sengar@webflow.com | queued |
| Jin Lim | VP Engineering | Webflow | jin.lim@webflow.com | queued |
| Tanvi Kothari | Sr EM, Data Platform | Webflow | tanvi.kothari@webflow.com | queued |
| ~~Nico Huang~~ | VP Engineering | Reddit | *excluded — Clay returned non-corporate email (onlyalad.net)* | dropped |

## Wave 3 — SENT 2026-07-05 (from tech@) · one-time task now disabled
Day-3 → 2026-07-08 · Day-7 → 2026-07-12 (from tech@). All 7 status: sent_1.

| Prospect | Title | Company | Email | Status |
|----------|-------|---------|-------|--------|
| Will Robinson | CTO | Plaid | wrobinson@plaid.com | queued |
| Milav Shah | Head of Data Platform | Plaid | mshah@plaid.com | queued |
| Sudarshan S. | Head of Data & AI | Plaid | s@plaid.com | queued |
| Sumeet Marwaha | Head of Data | Brex | smarwaha@brex.com | queued |
| Katherine Livins | Head of Data Science & Eng | Samsara | katherine.livins@samsara.com | queued |
| Sandeep Agarwal | VP Engineering | Samsara | sandeep.agarwal@samsara.com | queued |
| Lance Bradley | Dir Eng, Data Platform | Discord | lance.bradley@discordapp.com | queued |
| ~~Nitesh Kumar~~ | VP Eng | Affirm | *no email found* | dropped |
| ~~Kanak Chavda~~ | Head of Data Eng | Plaid | *no email found* | dropped |
| ~~James Reggio~~ | CTO | Brex | *off-domain (brexcard.net)* | dropped |
| ~~Stanislav Vishnevskiy~~ | CTO | Discord | *off-domain (hammerandchisel.com)* | dropped |

## Wave 4 — SENT 2026-07-05 (all from sandeep@; tech@ paused this run)
Day-3 → 2026-07-08 · Day-7 → 2026-07-12 (from sandeep@). All 10 status: sent_1.

| Prospect | Title | Company | Email |
|----------|-------|---------|-------|
| Anirban Kundu | CTO | Instacart | anirban.kundu@instacart.com |
| Radhika Anand | Head of Data (Caper/Connected Stores) | Instacart | radhika.anand@instacart.com |
| Matt Madrigal | CTO | Pinterest | mmadrigal@pinterest.com |
| Ang Zhang | Sr Dir Eng, Big Data Platform | Pinterest | angzhang@pinterest.com |
| Greg King | Head of Insights Data Eng & Analytics | Pinterest | gking@pinterest.com |
| Sui Huang | VP, Head of Data Science & Analytics | Roblox | shuang@roblox.com |
| Haoji Liu | Head of Data Platform | Roblox | hliu@roblox.com |
| Anupam Singh | VP Eng, AI Platform | Roblox | anupam@roblox.com |
| Jia He | VP Eng, Freight Tech | Flexport | jhe@flexport.com |
| Yong (Leo) Li | VP Engineering | Flexport | lli13@flexport.com |
| Rahul Bhardwaj | Head, Data Engineering | Instacart | *email still resolving — deferred to engine* |

## Wave 5 — SENT 2026-07-05 (all from sandeep@)
Day-3 → 2026-07-08 · Day-7 → 2026-07-12. All 6 status: sent_1.

| Prospect | Title | Company | Email |
|----------|-------|---------|-------|
| Vaibhav Jajoo | Head of Data Eng, Platform & BI | DoorDash | vaibhav.jajoo@doordash.com |
| Matan Amir | VP Eng, Foundations | DoorDash | matan.amir@doordash.com |
| Jacopo Himberg | Director, Data Platform | DoorDash | jacopo@doordash.com |
| Jeremy Rishel | CTO | SoFi | jrishel@sofi.com |
| Kate Matsudaira | Head of Tech / CTO SoFi Bank | SoFi | kmatsudaira@sofi.com |
| Carl Schmidt | Director, Data Platform Eng | SoFi | cschmidt@sofi.com |

## Deliverability events ⚠️
- **BOUNCE (tech@):** lance.bradley@discordapp.com — "address not found." SUPPRESSED.
- **BOUNCE (sandeep@):** bd@nerdwallet.com (Bryan Downs, Wave 2) — invalid ("group bd may not exist"). SUPPRESSED.
- **Pattern:** both bounces were Clay-returned short-alias / off-primary-domain addresses (bd@, discordapp.com). Rough bounce rate ~2/31 ≈ 6% — above the 3% comfort line.
- **Action taken:** engine held tech@ new-sends earlier; Wave 5 filtered to clean full-name primary-domain emails only.
- **RESOLVED (config):** engine now enforces a mandatory email-quality filter — drops "No results found", non-primary domains, and 1–2 char local-parts (bd@, s@, bs@); prefers firstname.lastname@. No external verify tool added (per Sandeep). s@plaid.com and bs@chime.com are already out — watch for their bounces; engine will auto-suppress if they bounce.
- **Mode:** fully autonomous, 7 AM ET (4:30 PM IST) daily.
- Auto-replies (Amit Kumar OOO) ignored — not human replies.

## Sending inboxes
- **sandeep@send.firebolt.io** — warming since 2026-07-03. ACCELERATED caps: wk1 ≤40 → wk2 ≤65 → wk3 ≤100 → wk4+ ≤125/day.
- **tech@send.firebolt.io** — warming since 2026-07-05. ACCELERATED caps: wk1 ≤20 → wk2 ≤45 → wk3 ≤75 → wk4+ ≤125/day.
- Combined mature ceiling ≈ 250/day. Ramp is CONDITIONAL: step up only if hard-bounce <3% and complaints <0.1%; else hold/cut and flag. Follow-ups always from the same inbox as that prospect's Day-0.

## Automation now live
- **Daily engine** `gtm-daily-maintenance` → 4:30 PM IST (≈7 AM ET) daily: reply sweep + SF leads, follow-ups, AND fresh prospecting + sending within the ramping cap (wk1 ≤20 → wk2 ≤35 → wk3 ≤50 → wk4+ ≤75), sandeep@ only.
- **Wave 2** `gtm-wave2-send` → one-time, 2026-07-06 07:00 ET.
- DST note: cron is fixed IST; 4:30 PM IST = 7 AM Eastern *Daylight* time. When US clocks fall back (Nov), shift to 5:30 PM IST to stay at 7 AM ET.
