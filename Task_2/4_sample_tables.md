# Task 2 – Sample Tables

This document contains sample tables used to run the patient care and communication system.  
All tables are designed to work with **HMS data + Google Sheets/Forms** and support daily execution.

---

## 1. Message Type Classification Table (One-time Setup)

This table defines which messages require doctor input.

| Message Type | Example Message | Doctor Input Needed |
|-------------|----------------|---------------------|
| Follow-up Reminder | “Please visit on Aug 5” | No |
| Post-Procedure Care | “Mild swelling is normal for 2–3 days” | No |
| Side-Effect Advisory | “Mild nausea may occur” | No |
| Custom Instruction | “Avoid sun exposure for 7 days” | Yes |
| Patient Question Response | “Regarding itching…” | Yes |

This table is fixed and reused daily.

---

## 2. Care_Control Sheet (Primary Working Sheet)

This Google Sheet tracks **every patient interaction**.

| Patient | Phone | Visit Type | Message Type | Message Text | Doctor Approval | Status |
|--------|-------|------------|--------------|--------------|-----------------|--------|
| Ramesh K | 9XXXX | OPD | Follow-up Reminder | Auto-filled | Not Required | Pending |
| Sita P | 9XXXX | Procedure | Post-Procedure Care | Auto-filled | Not Required | Pending |
| Arjun M | 9XXXX | OPD | Custom Instruction | — | Required | Waiting |

### Notes:
- One row = one patient message
- No message exists outside this sheet
- Status controls message flow

---

## 3. Doctor Review Filter (Working View)

During review sessions, I apply the following filter on **Care_Control**:

| Condition | Value |
|----------|-------|
| Doctor Approval | Required |
| Status | Waiting |

Only rows matching these conditions are shown to the doctor.

---

## 4. Patient_Questions Sheet (Google Form Output)

Patient questions are collected via Google Form and auto-populated here.

| Patient | Phone | Question | Answer | Status |
|--------|-------|----------|--------|--------|
| Lakshmi | 9XXXX | Is itching normal? | — | Pending |
| Ravi | 9XXXX | Can I take medicine after food? | — | Pending |

### Notes:
- Questions are batched every 3 hours
- Doctor answers are recorded once
- Responses are sent and then closed

---

## 5. Status Flow Reference

The following status values are used consistently:

| Status | Meaning |
|-------|---------|
| Waiting | Requires doctor input |
| Pending | Ready to be sent |
| Sent | Message delivered |
| Closed | No further action required |

No message is sent unless it reaches **Pending** status.

---

## 6. Message Dispatch Eligibility Rule

A message is eligible to be sent only if:

| Condition | Required Value |
|---------|----------------|
| Message Text | Filled |
| Status | Pending |
| Doctor Approval | Not Required / Approved |

This rule prevents accidental or incomplete messages.

---

## 7. Optional Automation Reference (Logic Only)

If automation is enabled later:

| Trigger | Action |
|-------|--------|
| Status = Pending | Send WhatsApp message |
| Message Sent | Update Status → Sent |

Automation handles **routine messages only**.  
Doctor-reviewed messages always follow approval rules.
