# PRD-01 — Bridge: Plain-Language Civic Translator

*Track: Best Use of Gemini (Google) · Status: concept · Last updated 2026-10-12*

## Objective
Win Best Use of Gemini at AI GENESIS 2026 with a multimodal AI app that turns
dense school and government communications into plain language — read aloud in
the family's home language.

## Problem
Schools and local governments communicate in bureaucratic English: enrollment
packets, IEP notices, utility letters, jury summons. For the ~25M US residents
with limited English proficiency — and for millions more who just don't speak
bureaucrat — these documents are effectively unreadable. Missed deadlines have
real consequences: lost benefits, truancy filings, shutoff notices.

Chris's firsthand angle: navigating Leander ISD paperwork, custody filings, and
city notices as a parent. He has lived this problem.

## Solution
**Bridge** — snap a photo of any official document (or forward an email). Gemini
multimodal reads it and returns:
1. A plain-language summary ("What this says, in normal words")
2. Action items with deadlines ("What you need to do, and by when")
3. A voice readout in the user's home language (Gemini native audio)
4. A "reply draft" for common cases (absence notes, appointment requests)

Multimodal is the point: documents arrive as crumpled paper, phone photos, PDFs,
screenshots. Gemini's document understanding + native multilingual audio is the
engine — not a wrapper around a chatbot.

## Why it wins (rubric mapping)
- **Application of Technology (5):** Gemini multimodal document understanding +
  native audio generation are the core loop. Every interaction exercises both.
- **Presentation (5):** The demo is visceral — hold up a real jury summons, watch
  it become a 30-second voice note in Spanish. Under 2 minutes to the "wow."
- **Business Value (5):** B2B2C wedge: school districts and legal-aid orgs pay
  per-seat to reduce missed-deadline caseloads. TAM: US K-12 parent comms alone
  is a $2B+ market (parent-engagement platforms). Competitors: TalkingPoints and
  Remind solve messaging, not comprehension. Roadmap: benefits-navigation,
  healthcare forms, immigration paperwork.
- **Originality (5):** Document→voice-note in home language, with action
  extraction, is not a crowded space. The "what do I actually have to do"
  layer is the differentiator.

## Architecture
- **Frontend:** Next.js on Vercel. Camera/upload → document view → summary cards
  → audio player. Mobile-first (the users photograph paper).
- **AI:** Gemini API — multimodal input (image/PDF), structured JSON output
  (summary, actions, deadlines), native audio for readout. Language auto-detect.
- **Storage:** Postgres (Neon) for documents, summaries, user language prefs.
- **No heavy infra:** serverless, free tiers throughout.

## 7-day build plan
| Day | Milestone |
|---|---|
| 1 | Repo + Vercel deploy. Upload flow working, Gemini key wired. |
| 2–3 | Document → structured summary pipeline (JSON schema: summary, actions[], deadlines[]). |
| 4 | Audio readout in home language. Language picker + auto-detect. |
| 5 | Reply-draft templates. Polish mobile UX. Real documents tested end to end. |
| 6 | Video script + record. Deck. Descriptions. |
| 7 | Submit. Buffer. |

## Business case (for video + deck)
- **Who pays:** School districts ($3–8/student/year parent-engagement budgets),
  legal-aid nonprofits (grant-funded), then direct-to-family freemium.
- **Pricing:** $49/mo per school site pilot; $6.99/mo family plan.
- **Competitors:** TalkingPoints, Remind (messaging, not comprehension);
  Google Translate (translation, not action extraction).
- **12-month roadmap:** Benefits + healthcare forms, WhatsApp bot distribution,
  district dashboard showing comprehension analytics.

## Submission checklist
Standard lablab.ai items — see `docs/win-plan.md`. Cover image: phone photo of a
real school letter becoming a voice note.

## Risks / open questions
- 2026 Gemini track not yet confirmed — re-verify after partner reveal.
- Audio quality across low-resource languages needs testing early (day 2).
- Privacy: documents contain PII — on-device redaction before upload is a
  must-have, not a nice-to-have. State it in the video.
