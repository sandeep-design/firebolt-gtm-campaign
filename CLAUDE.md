# Firebolt GTM Outbound — Cloud Routine Contract

You run once daily as a scheduled cloud routine (replacing the laptop
gtm-daily-maintenance engine). Follow the firebolt-gtm-campaign skill, drawing
messaging from firebolt-product-marketing.

## State lives in the repo — read it, then commit it back
- `Campaign-01_Ledger.md` is the source of truth (waves, per-prospect status,
  suppression list, inbox warmup state).
- Read it at the START of every run.
- At the END: write updates back and
  `git add Campaign-01_Ledger.md && git commit -m "run <date>" && git push`.
  If you skip this, tomorrow's run repeats today's sends. Never skip it.

## Daily procedure (maintenance engine)
1. Reply sweep via AgentMail across sandeep@ and tech@. For each reply:
   genuine reply → stop that sequence, de-dupe + create Salesforce Lead
   (LeadSource="GTM Outreach (Cowork)"), surface to Slack. Opt-out → suppress
   permanently. Auto-replies (OOO) → ignore, sequence continues.
2. Send due follow-ups (Day-3 / Day-7). Thread onto the prospect's Day-0
   (set In-Reply-To / References to that message-id) and send from the SAME
   inbox as their Day-0.
   - Follow-ups go `to:` the prospect's email from the ledger — NEVER to the
     sending inbox. Do not "reply" to your own sent message (that mails
     yourself; it caused the 2026-07-08 misfire). Use an explicit send with the
     recipient set.
   - After each send, read the sent message back and verify `to:` = the
     prospect. If it equals the sending inbox, abort, do NOT mark sent, and
     flag to Slack.
3. Fresh prospecting via Clay within the current ramp cap; enrich; apply the
   mandatory email-quality filter (drop "no results", non-primary domains, and
   1–2 char local parts like bd@/s@/bs@; prefer firstname.lastname@).
4. Personalize 3-email sequences per the product-marketing craft rules
   (50–110 words, one pillar, Calendly CTA, one-line opt-out, no fake hooks).
5. Send Day-0 within cap via AgentMail (same recipient + verification rule as
   step 2). Respect the conditional ramp: step up only if hard-bounce <3% and
   complaints <0.1%; else hold/cut and flag to Slack.
6. Update + commit the ledger. Post a summary to Slack #sandeep-claude-outbound-campaign:
   sent / queued / replies / leads created / bounces / cap status, plus any
   aborted sends caught by the recipient check.

## Never
- Email anyone already at that step, suppressed, bounced, or an open opp.
- Address any email to the sending inbox instead of the prospect.
- Fabricate personalization — use a persona-level opener or skip.
