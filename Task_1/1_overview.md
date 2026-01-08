
# Task 1 – Daily Clinic Inventory Micro-Audit

The sections below may be detailed, but they are intentionally practical and grounded in my domain experience to keep the solution realistic and executable.

## Purpose of This Task

This task simulates the role of a **Clinic Business Analyst** responsible for maintaining inventory accuracy and billing discipline in a small clinic pharmacy where:

- Medicines are not barcoded
- Sales entries are typed manually
- Errors are small but frequent
- Doctor time is extremely limited

The goal is to design a **daily micro-audit system** that:
- Keeps staff alert
- Detects errors early
- Prevents inventory shocks at month-end
- Runs in 20–30 minutes per day
- Protects doctors time

---

## What This System Is and Is not

### This system **is**:
- A daily control mechanism
- Focused on behavior correction, not punishment
- Designed for real clinic constraints
- Runnable by a non-technical analyst or hospital staff

### This system **is not**:
- A full inventory reconciliation process
- A technology-heavy or automated solution
- A statistical or audit-heavy framework

---

## Data Assumptions

The system operates using four daily data sources already available in the clinic:

1. Opening Inventory (day start)
2. Purchase Register (invoice-verified)
3. Sales Register (from HMS, manually entered)
4. Closing Inventory (day end)

All examples and tables in this task use **sample data provided in the assignment** to demonstrate logic and execution steps.

---

## Design Principles

The design of this micro-audit follows these principles:

- **High-risk focus**: Only medicines most likely to cause errors are checked daily
- **Small, frequent checks**: Catch errors early instead of reconciling later
- **Random verification**: Encourage staff discipline without constant supervision
- **Clear action rules**: Every finding leads to a defined next step
- **Minimal escalation**: Doctor involvement only when truly necessary

---

## What Follows in This Folder

This folder contains:

- `daily_micro_audit.md`  
  → Step-by-step execution of the daily micro-audit routine

- `checklists.md`  
  → Daily and weekly checklists for running the system

- `sample_tables.md`  
  → Example tables for high-risk medicines, name mapping, stock checks, and error logs

Together, these documents describe a system that a clinic can **start running immediately**.

---

## Expected Outcome

If run consistently, this system should:
- Reduce sales-entry mistakes
- Improve billing discipline
- Minimize month-end inventory surprises
- Free up doctor time from routine operational issues
