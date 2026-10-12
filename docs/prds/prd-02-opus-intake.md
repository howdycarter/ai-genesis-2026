# PRD-02 — Intake: The AI Front Desk for Contractors

*Track: Best Opus Workflow (AppliedAI) · Status: concept · Last updated 2026-10-12*

## Objective
Win Best Opus Workflow at AI GENESIS 2026 with an agentic intake system that
answers every contractor call, qualifies the job, and drafts the quote — with
human review before anything goes out.

## Problem
Home-service contractors (HVAC, plumbing, electrical, roofing) miss 60%+ of
inbound calls — they're on a roof, under a sink, on another job. Every missed
call is a lost job worth $300–$5,000. Existing "AI receptionists" are dumb IVR
trees or hallucination-prone chatbots with no audit trail. Contractors don't
trust them because they can't see what the AI decided or why.

## Solution
**Intake** — a voice + text front desk built on the Opus
Intake → Understand → Decide → Review → Deliver pattern:
1. **Intake:** Answers the call (voice AI) or text. Captures: who, where, what's
   broken, urgency, photos of the problem.
2. **Understand:** Classifies job type, estimates scope, checks service area and
   calendar availability.
3. **Decide:** Routes — emergency → dispatch now; standard → quote draft;
   out-of-area → polite decline + referral.
4. **Review:** Two checkpoints — agentic self-review (confidence scores,
   policy checks) then **human review**: the contractor sees the call summary,
   quote draft, and AI reasoning in a mobile feed, approves/edits in one tap.
5. **Deliver:** Sends the quote via SMS/email. Every step emits a
   provenance/audit artifact (JSON + PDF): what was heard, what was decided,
   what the human changed.

The audit trail is the product. Trust is the moat.

## Why it wins (rubric mapping)
- **Application of Technology (5):** The full Opus workflow pattern is the
  architecture — not a feature. Agentic + human review checkpoints and the
  audit artifact map 1:1 to the track's stated requirements.
- **Presentation (5):** Demo: live call comes in, AI handles it, contractor's
  phone shows the review card, one tap approves, customer gets the quote. Real
  phones, real voices, under 3 minutes.
- **Business Value (5):** Clear ROI math: one saved job/month pays for a year.
  TAM: 500K+ US home-service contractors; $200–400/mo SaaS = $1.2B+ SAM.
  Competitors: Smith.ai (human answering, expensive), generic voice AI (no
  audit trail, no contractor-specific workflow). Roadmap: dispatch integration,
  payments, multi-trade.
- **Originality (4):** AI receptionists exist; the human-in-the-loop audit
  artifact as a first-class product surface is the novel move.

## Architecture
- **Voice:** Telephony via Twilio (or track-equivalent), speech-to-text,
  Gemini/LLM for understanding, TTS for response.
- **Workflow engine:** Opus platform (per track) orchestrating the five stages;
  state machine with checkpoint gates.
- **Review app:** Next.js on Vercel — contractor mobile feed: call summary,
  transcript, quote draft, confidence scores, approve/edit.
- **Audit:** Every run emits JSON + PDF provenance artifact, stored in Postgres.
- **Delivery:** SMS/email via Twilio/Resend.

## 7-day build plan
| Day | Milestone |
|---|---|
| 1 | Repo + Vercel. Opus account + credits. Twilio number provisioned. |
| 2–3 | Intake → Understand → Decide pipeline. Test calls handled end to end. |
| 4 | Review checkpoints: agentic self-review + human approval feed (mobile). |
| 5 | Audit artifact (JSON/PDF). Delivery via SMS. Polish. |
| 6 | Video: real call → review → quote. Deck. Descriptions. |
| 7 | Submit. Buffer. |

## Business case (for video + deck)
- **Who pays:** Home-service contractors, $249/mo per line.
- **ROI:** One $800 job saved per month = 3x return.
- **Competitors:** Smith.ai ($300+/mo, human-only, no automation); generic AI
  voice agents (no trade-specific workflow, no audit trail).
- **12-month roadmap:** Dispatch + scheduling, integrated payments, review
  solicitation, multi-location.

## Submission checklist
Standard lablab.ai items — see `docs/win-plan.md`. Cover image: contractor's
phone showing the one-tap approval card.

## Risks / open questions
- 2026 Opus track not yet confirmed — re-verify after partner reveal.
- Live telephony in a demo is risky — pre-record the call path, show the live
  review feed genuinely. Never fake the AI's work.
- Track may require the Opus platform specifically; confirm the required
  stack at kickoff before building on alternatives.
