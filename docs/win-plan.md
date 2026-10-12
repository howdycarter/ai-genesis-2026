# Win Plan — AI GENESIS 2026

*Strategy derived from 2023–2026 lablab.ai winner patterns. Updated 2026-10-12.*

## The thesis

Judges score four criteria 1–5: Application of Technology, Presentation, Business
Value, Originality. Past winners show the bar clearly: **a working product solving
a real problem, with the partner's technology at its core, pitched like a startup
— not a demo.**

RSoft Agentic Bank (2026) is the proof: judges called the top builds "viable
businesses, not just prototypes" and Google raised the prize pool mid-event.

## Strategic choices

### 1. Pick ONE partner track and go deep
You are judged *within the partner category*. A shallow integration across two
partners loses to a deep integration in one. Choose the track after the 2026
partner reveal (before kickoff), then commit fully.

**Track ranking for Chris (pre-reveal, based on 2025):**
1. **Best Use of Gemini** — biggest prize pool ($30K in credits in 2025), multimodal
   plays directly to voice/IVR + design strengths. Highest expected value.
2. **Best Opus Workflow** — cash prizes ($3K 1st in 2025), agentic workflows with
   human-in-the-loop are his consulting bread and butter.
3. **Best Use of Qdrant** — societal-challenge framing suits civic/community
   concepts; hardware prizes are nice but cash is better.

### 2. Build for the rubric, explicitly
| Criterion | How we max it |
|---|---|
| Application of Technology (1–5) | Partner tech is the *engine*, not a feature. Demo shows it doing work no template could. Public repo is clean, documented, runnable. |
| Presentation (1–5) | Sub-5-min video: problem → solution → value prop → market → revenue → competitors → future. One continuous screen recording, no slides-reading. |
| Business Value (1–5) | Real pricing, real TAM/SAM/SOM, named competitors, 12-month roadmap. The PRDs in `docs/prds/` carry this. |
| Originality (1–5) | Firsthand problem (his life, his work) + a novel interaction model. Not another chatbot wrapper. |

### 3. Ship a live URL on day one of the build window
Deploys are scored. Get *something* on Vercel within 24 hours of kickoff, then
iterate. A dead link on submission day is disqualification-adjacent.

### 4. The video is the pitch, not a tour
Under 5 minutes. Script it before recording:
- 0:00–0:45 — the problem, with a real human moment
- 0:45–2:30 — the product working, end to end, on real inputs
- 2:30–3:30 — why the partner tech makes this possible (name it, show it)
- 3:30–4:30 — business: who pays, how much, market size, competitors
- 4:30–5:00 — what's next (roadmap, ask)

### 5. Solo is a feature, not a limitation
Solo builders have won 1st place repeatedly (WebIndexer, AI Brand Intel).
No coordination overhead in a 7-day window. If a teammate appears on Discord
with a *specific* missing skill, consider it — otherwise run solo.

## Timeline (assuming Oct 26 – Nov 2 build window)

| When | What |
|---|---|
| Now – Oct 25 | Register on lablab.ai + Discord. Read PRDs, pick concept + track after partner reveal. Set up repo skeleton, deploy pipeline, design system tokens. Pre-build anything track-agnostic (auth, landing page shell, video script template). |
| Oct 26 (Day 1) | Kickoff. Lock concept. Live URL deployed by EOD, even if skeletal. |
| Oct 27–29 | Core build. Partner tech integrated deeply. Real data flowing end to end. |
| Oct 30–31 | Polish, edge cases, business-case materials (pricing, market slides). |
| Nov 1 | Record video. Write descriptions. Freeze code. |
| Nov 2 | Submit: repo + URL + video + deck + descriptions + partner tag. Buffer for the 6-hour manual-submission grace window if needed. |

## Submission checklist (from the rule book)
- [ ] Title, short + long descriptions written
- [ ] Correct partner technology tag selected
- [ ] Cover image (PNG/JPG, 16:9)
- [ ] Demo video (MP4, <5 min)
- [ ] Slide deck (PDF)
- [ ] Public GitHub repo (this repo) — clean, licensed MIT, runnable
- [ ] Working application URL (Vercel)
- [ ] Chris explicitly approves the submission before anything is posted

## Anti-patterns (what loses)
- Chatbot wrapper with a system prompt and no real integration
- Partner tech as a logo on the landing page
- Video that tours features instead of telling a story
- "Coming soon" anywhere in the demo
- Submitting in the last hour with an untested deploy
