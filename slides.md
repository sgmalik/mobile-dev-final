---
marp: true
theme: default
paginate: true
footer: "AI Flashcard Generator (Swift) — Proof of Concept"
title: "Swift POC: AI Flashcard Generator"
description: "Concise plan for a Swift-only proof of concept: what, why, how, MVP, roadmap."
---

# AI Flashcard Generator (Swift POC)
Transform notes → study cards in minutes  
- Input: text or photo  
- Output: flashcards with spaced repetition  
- Platform: iOS (Swift / SwiftUI)

---

## Problem → Opportunity
- Manual flashcard creation is tedious  
- Passive reading ≠ retention  
- Students need mobile, inclusive study tools  

**Opportunity:** One-tap capture and AI-assisted flashcards

---

## Who Benefits
- High school & university students  
- Adult learners & career upskillers  
- Educators building shareable decks

---

## What It Does (POC)
- Scan or paste notes → extract text with Vision  
- Send text to LLM → generate Q/A + cloze cards  
- Review, edit, and approve  
- Practice with simple spaced repetition

---

## MVP Scope
- Capture: camera scan (VisionKit)  
- OCR: Vision text recognition  
- Generation: call LLM API  
- Card editor: edit/approve/delete  
- Study mode: Leitner system  
- Storage: Core Data or SQLite
- Sharing & collaboration  

---

## User Flow
1. Home → Create Deck  
2. Add Source → Scan or paste text  
3. Preview text → quick cleanup  
4. Generate cards → review list  
5. Edit/approve → save deck  
6. Practice → self-grade

---

## Minimal Architecture
- SwiftUI UI + Combine for state  
- VisionKit for scan  
- Vision for OCR  
- URLSession for LLM requests  
- Core Data for persistence  
- Optional iCloud sync

---

## Data Model
- **Deck**: id, title, tags, createdAt  
- **Card**: id, deckId, type (qa/cloze), front, back  
- **Review**: cardId, lastReviewedAt, intervalDays, ease

---

## Scheduling (Simple)
- Success: 1d → 3d → 7d → 14d  
- Failure: reset to 1d  
- Optional ease factor from self-grade

---

## Prompting
"You are an expert educator. From the text below, create concise Q/A and cloze flashcards for [subject, level]. Keep each side ≤200 characters, avoid ambiguity, preserve key terms. Return JSON. Text: '<cleaned_text>'"

---

## Success Criteria
- 60% of new users generate ≥10 cards in first session  
- 35% return next day  
- 85% user-rated “useful” cards  
- <2% hallucination reports

---

## Scalable Features (Future)
- Image-labeling cards  
- Audio prompts & speech answers  
- Multiple-choice with distractors  
- Personalization (FSRS)  
- Deck sharing & educator batching

---

## Risks & Mitigations
- OCR noise → cleanup preview  
- Hallucinations → strict prompts & filters  
- Cost/latency → batch requests  
- Privacy → local OCR, minimal data sent

---

## Build Plan
- Week 1: Capture + OCR, basic data model  
- Week 2: LLM integration, editor, study loop  
- Week 3: Accessibility, telemetry, bug fixes  
- Week 4: TestFlight beta, refine prompts

---

## Next Steps
- Select LLM provider and cap costs  
- Finalize card schema  
- Implement scan → generate → practice flow  
- Ship TestFlight build, track usage metrics
