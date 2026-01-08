# Task 2 – Patient Care & Communication System

## Purpose of This Task

This task simulates the role of a **Clinic Business Analyst** responsible for designing a patient communication system in a busy clinic where:

- Doctors are frequently interrupted by patient queries
- Many questions are repetitive or non-clinical
- Responses are sometimes delayed or inconsistent
- Doctor time needs to be protected for clinical decisions

The goal is to design a **structured communication system** that ensures patient care continuity while minimizing unnecessary doctor involvement.

---

## What This System Is (and Is Not)

### This system **is**:
- A practical workflow for handling patient messages
- Focused on clarity, ownership, and response discipline
- Designed to run daily with minimal effort
- Aligned with real clinic staffing constraints

### This system **is not**:
- A chatbot or automated AI system
- A replacement for doctor judgment
- A technology-heavy solution

---

## Core Problem Being Solved

Without structure:
- Doctors get interrupted for routine questions
- Patient messages pile up or get missed
- Response quality depends on who is available
- No clear ownership or tracking exists

This system introduces:
- Message categorization
- Clear decision boundaries
- Tracking of patient communication
- Controlled doctor escalation

---

## Data Assumptions

The system operates using:
- Patient messages (calls, WhatsApp, in-clinic queries)
- Visit type information (first visit / follow-up)
- Doctor availability windows

All examples and tables use **sample scenarios** to demonstrate execution logic.

---

## Design Principles

- **Doctor time is protected by default**
- **Non-clinical queries are handled without escalation**
- **Doctor input is requested only when necessary**
- **Every message has a clear owner and status**
- **No patient query is lost or forgotten**

---

## What Follows in This Folder

This folder contains:

- `care_flow.md`  
  → Step-by-step execution of the patient communication workflow

- `checklists.md`  
  → Daily operating checklist for managing patient messages

- `sample_tables.md`  
  → Message classification tables and care control tracking examples

Together, these documents define a system that a clinic can **start using immediately**.
