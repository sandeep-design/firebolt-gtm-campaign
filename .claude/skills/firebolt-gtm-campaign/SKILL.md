---
name: firebolt-gtm-campaign
description: Runbook for executing Firebolt daily GTM cold-outreach campaigns end to end. Use when the user provides "Target titles", "Signals", and a "Messaging Brief" and wants to run an outreach campaign — pulling target companies/contacts in Clay, researching and personalizing a 3-email Day 0/3/7 sequence, sending from AgentMail, monitoring replies, honoring opt-outs, and creating Salesforce leads. Pairs with the firebolt-product-marketing skill for messaging.
---

# Firebolt GTM Campaign Runbook
### Daily personalized outreach engine

This is the operating manual. To launch a campaign, the user gives three inputs and you execute the pipeline below. Always draw messaging from the `firebolt-product-marketing` skill.

---

## User's daily input (the prompt)
```
Target titles:   e.g. VP Data, Head of Data Platform, Director of Analytics Engineering
Signals:         e.g. using BigQuery at scale + open-format/lakehouse interest + hiring analytics engineers
Messaging Brief: e.g. lead with "no lock-in" pillar; reference their recent migration project; angle = open formats
```
That's all the user provides. Everything below runs off these three fields + the product marketing brief.

---

## The pipeline (per campaign run)

### Step 1 — Build the target list (Clay)
- Translate **Signals** into an ICP filter and combine with the Firebolt ICP.
- `find-and-enrich-company` → pull target companies matching signals.
- `find-and-enrich-contacts-at-company` → within each company, pull contacts matching **Target titles**.
- Enrich each contact (name, title, company, LinkedIn, email, recent context).
- Check `get-credits-available` first; if low, cap the pull and flag it.
- **Output:** a clean prospect list with verified business emails only.
- **Email-quality filter (mandatory):** drop "no results", non-primary domains,
  and 1–2 char local-parts (e.g. bd@, s@, bs@). Prefer firstname.lastname@.

### Step 2 — Research & personalize
- For each prospect, use Clay enrichment + targeted web/LinkedIn research to find ONE genuinely specific hook (recent role change, funding, product launch, tech-stack signal, a talk/post).
- Match the prospect's persona to the right messaging pillar.
- Write a **3-email sequence** per the craft rules and the day's **Messaging Brief** angle.
- Every email carries the **Calendly link** (https://calendly.com/sandeep-mathur-firebolt/new-meeting) and a one-line opt-out.

### Step 3 — Schedule the sequence (Day 0 / 3 / 7)
- Respect the **warmup cap** (below). Only as many Day-0 sends as the cap allows; overflow rolls to next day.
- Email 1 sends Day 0; Emails 2 & 3 queue for Day 3 and Day 7.
- Track state in the campaign ledger: `queued → sent_1 → sent_2 → sent_3 → replied/opted_out/done`.

### Step 4 — Send (AgentMail)
- Send Day-0 from **sandeep@send.firebolt.io** (single-inbox mode for now).
- Space sends across the working day; never blast all at once.
- **Recipient rule (CRITICAL):** every email — Day-0 AND every follow-up — must
  be addressed with `to:` = the prospect's email taken from the ledger. NEVER
  send to the sending inbox.
- **Threading for Emails 2 & 3:** thread onto Email 1 by setting `In-Reply-To`
  and `References` to Email 1's message-id, using an explicit send with the
  recipient set to the prospect. Do NOT use a "reply" action on your own
  previously-sent message — replying to a message whose `from:` is the sending
  inbox addresses the follow-up back to yourself (this caused the 2026-07-08
  misfire where 10 follow-ups landed in sandeep@ instead of the prospects).
- **Post-send verification:** after each send, read the sent message back and
  confirm `to:` equals the prospect's email. If `to:` equals the sending inbox
  (or anything other than the prospect), ABORT: do NOT advance the ledger status
  for that prospect, and flag it to Slack #sandeep-claude-outbound-campaign.

### Step 5 — Monitor replies (handled by the gtm-daily-maintenance scheduled task)
- Sweep the inbox each morning. For any prospect who replied:
  - **Stop the sequence immediately** (cancel queued Day-3/Day-7 sends).
  - If **opt-out/unsubscribe**, mark permanently suppressed — never contact again.
  - If **genuine reply/interest**, create a **Salesforce Lead** (Step 6) and surface it to Sandeep.
- Ignore automated auto-replies (e.g. Out-of-Office) — not human replies; sequence continues.

### Step 6 — Salesforce lead creation
- On a positive/neutral reply, `createSobjectRecord` on **Lead** with:
  `FirstName, LastName, Company, Title, Email, LeadSource="GTM Outreach (Cowork)", Status="Working - Contacted", Description=` (reply + campaign context + pillar/signal that converted).
- De-dupe first: SOQL check for existing Lead/Contact by email before creating.
- First real run: confirm required custom fields on Lead; adjust mapping.

---

## Warmup & deliverability guardrails (IMPORTANT)
Single new inbox on a new domain. Sending hundreds/day now = blacklist. Ramp:

| Week | Safe cold sends/day (Day-0 new prospects) |
|---|---|
| 1 | 15–20 |
| 2 | 25–35 |
| 3 | 40–50 |
| 4+ | 50–75 (single-inbox practical ceiling) |

- Follow-ups (Day 3/7) don't count against the Day-0 cap but do count toward total daily volume — keep total under ~2x the cap.
- **To reach hundreds/day:** flip to multi-inbox rotation across benjamin@, paurush@, asaph@, ciso@, sandeep@ (5 inboxes → 5x ceiling), and/or add inboxes. Follow-ups always from the same inbox as that prospect's Day-0.
- Watch bounce rate (<3%) and spam complaints (<0.1%). If either climbs, auto-pause and alert. Ramp is CONDITIONAL: step up only if hard-bounce <3% and complaints <0.1%; else hold/cut and flag.

## Approval mode
- **Week 1:** Review-first. Prep the batch + a summary; Sandeep approves; then send Day-0 and schedule follow-ups.
- **Week 2+:** Auto-send within caps, with a daily summary and any replies surfaced.

## State & suppression
- Master **suppression list**: anyone who opted out, bounced, or is already an open opportunity. Checked before every send.
- Campaign **ledger** per campaign: prospect, company, persona, pillar, signal, send timestamps, status, reply.

## Guardrails recap
- Business emails only. Instant, permanent opt-out. No contacting existing customers/open opps.
- Never fabricate personalization. If no real hook is found, use a persona-level (not fake-personal) opener or skip the prospect.
- Every send is `to:` the prospect, verified after sending. Never mail the sending inbox.
