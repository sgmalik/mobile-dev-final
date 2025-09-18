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
- Output: flashcards

---

## What It Does (POC)
- Scan or paste notes → extract text with Vision  
- Send text to LLM → generate Q/A + cloze cards  
- Review, edit, and approve  
- Practice with simple spaced repetition

---

<img width="780" height="1768" alt="screen" src="https://github.com/user-attachments/assets/1907107b-f212-43f6-9a38-b4468ecc21a7" />

<img width="780" height="1768" alt="screen" src="https://github.com/user-attachments/assets/6896a69a-40b4-4a80-8202-42acdc705eb3" />

<img width="780" height="1768" alt="screen" src="https://github.com/user-attachments/assets/b8556e4e-d775-4bf1-adac-98b3e9389e83" />

---

## MVP Scope
- Capture: camera scan (VisionKit)  
- OCR: Vision text recognition  
- Generation: call LLM API  
- Card editor: edit/approve/delete  
- Study mode: Leitner system?
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

