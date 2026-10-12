# PRD-03 — Civica: Ask Your City Anything

*Track: Best Use of Qdrant · Status: concept · Last updated 2026-10-12*

## Objective
Win Best Use of Qdrant at AI GENESIS 2026 with a semantic search engine over
local civic life — council agendas, school board minutes, permits, budgets —
so any resident can ask questions in plain language and get cited answers.

## Problem
Local civic information is public but practically inaccessible: PDFs of council
agendas, 4-hour meeting videos, permit databases with 1990s search. Local news
deserts mean nobody covers the school board. Result: residents can't answer
basic questions — "What's being built behind my street?", "When does the board
vote on the boundary change?", "Where does my property tax actually go?" —
and disengage from the decisions that affect them most.

Chris's firsthand angle: Leander Live (his community-events board) already
ingests local event data. Civica is the civic-knowledge layer on top of that
pattern — he has the ingestion muscle and the local context.

## Solution
**Civica** — a search box for your city:
1. **Ingest:** Council agendas + minutes, school board docs, permit filings,
   budgets, meeting transcripts — chunked, embedded, stored in Qdrant with
   hybrid (dense + sparse) search.
2. **Ask:** "Is there a vote on short-term rentals next month?" → semantic
   retrieval over all sources, reranked, answered with **citations to the exact
   document and page**.
3. **Memory:** Follow-ups work conversationally ("What did they decide last
   time?") — Qdrant powers the conversation memory and recommendations
   ("Related: the zoning case two streets over").
4. **Multimodal:** Meeting videos transcribed and embedded — ask about what was
   *said*, not just what was written.

Qdrant is the core: vector search for Search, Memory, and Recommendations over
multimodal civic data — exactly the track's stated challenge (societal impact).

## Why it wins (rubric mapping)
- **Application of Technology (5):** Qdrant vector search is the entire product
  — retrieval, conversational memory, recommendations. Named, shown, load-bearing.
- **Presentation (5):** Demo: "What's being built behind my street?" → answer
  with cited permit docs and a map. The citation UX is the wow — every claim
  traceable to a source document.
- **Business Value (5):** B2B: municipalities pay for resident-engagement
  analytics ($10–30K/yr per city); B2B2C: local newsrooms license it as their
  "ask anything" widget. TAM: 19,000 US municipalities + 3,000 newsrooms.
  Competitors: Granicus (top-down comms, not Q&A); generic chatbots (no
  citations, no civic corpus). Roadmap: 311 integration, ballot-measure
  explainers, multilingual.
- **Originality (5):** Cited-answer civic search with conversational memory is
  genuinely novel — nobody has productized the "ask your city anything" loop.

## Architecture
- **Ingestion:** Firecrawl + document parsers → chunking → embeddings →
  Qdrant Cloud (free tier) collections per city, with payload filters
  (doc type, date, district).
- **Retrieval:** Hybrid dense + sparse search, reranking, citation assembly
  (document, page/section, timestamp for video).
- **App:** Next.js on Vercel. Search-first UX, cited answer cards, source
  viewer, follow-up conversation.
- **Data (demo):** Leander, TX — real council agendas, LISD board docs, permits.
  One city, deeply covered, beats ten cities shallowly.

## 7-day build plan
| Day | Milestone |
|---|---|
| 1 | Repo + Vercel. Qdrant Cloud collection. Ingestion pipeline skeleton. |
| 2–3 | Ingest Leander corpus (agendas, minutes, permits). Chunking + embeddings tuned. |
| 4 | Ask → cited-answer loop. Source viewer. Conversation memory. |
| 5 | Meeting-video transcription + embedding. Polish search UX. |
| 6 | Video: three real questions, cited answers. Deck. Descriptions. |
| 7 | Submit. Buffer. |

## Business case (for video + deck)
- **Who pays:** Municipalities ($10–30K/yr engagement analytics + hosted Q&A);
  newsrooms ($500–2K/mo widget license).
- **Competitors:** Granicus (broadcast, not Q&A); city websites (PDF graveyards);
  general AI chat (no civic corpus, no citations).
- **12-month roadmap:** 311 service-request integration, ballot explainer mode,
  Spanish-first UX, 50-city expansion playbook.

## Submission checklist
Standard lablab.ai items — see `docs/win-plan.md`. Cover image: a cited answer
card — question, answer, and the source documents it came from.

## Risks / open questions
- 2026 Qdrant track not yet confirmed — re-verify after partner reveal.
- Corpus licensing: public documents are fine; confirm no ToS issues with
  scraped meeting videos.
- One-city depth is a strength for the demo but judges may ask about scale —
  have the 50-city playbook slide ready.
