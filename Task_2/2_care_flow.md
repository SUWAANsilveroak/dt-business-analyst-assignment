# Task 2 – Patient Care & Communication Flow

This document describes the exact daily execution steps for managing patient communication using HMS and Google Sheets, while ensuring doctor review time stays within 10 minutes per session.

---

## STEP 1 — Message Type Classification (One-time | 20 mins)

I create a fixed **Message Type List** with a clear rule on doctor involvement.

| Message Type | Example | Doctor Input Needed |
|-------------|---------|---------------------|
| Follow-up Reminder | “Please visit on Aug 5” | No |
| Post-Procedure Care | “Mild swelling is normal” | No |
| Side-Effect Advisory | “Nausea may occur” | No |
| Custom Instruction | “Avoid sun exposure for 7 days” | Yes |
| Patient Question Response | “Regarding itching…” | Yes |

This list is shared with staff and used consistently.

---

## STEP 2 — Care Control Sheet (Daily Working Sheet)

I maintain one Google Sheet named **Care_Control**.

Columns:
- Patient Name
- Phone Number
- Visit Type
- Message Type
- Message Text
- Doctor Approval (Required / Not Required)
- Status (Pending / Waiting / Sent / Closed)

### How rows are created:
- Appointment and prescription data comes from HMS
- Routine message rows are auto-filled
- Custom messages are left blank for doctor review

---

## STEP 3 — Doctor Review Window (Every 3–4 Hours)

I filter **Care_Control** to:
- Doctor Approval = Required
- Status = Waiting

I sit with the doctor for **10 minutes**.

Doctor actions:
- Dictates or approves message content

My actions:
- I type the message once
- I update approval status

Doctor never:
- Types messages
- Opens WhatsApp
- Replies individually to patients

---

## STEP 4 — Patient Question Handling (Google Form Flow)

Patients submit questions using a Google Form with:
- Name
- Phone
- Question
- Urgency (Routine / Urgent)

Responses auto-fill a sheet named **Patient_Questions**.

Columns:
- Patient
- Phone
- Question
- Answer
- Status

Execution:
- I batch questions every 3 hours
- I review only unanswered questions with the doctor
- I record answers once and update status

---

## STEP 5 — Message Dispatch Logic

Messages are sent only when:
- Message Text is filled
- Status = Pending
- Doctor Approval = Not Required or Approved

Status flow:
- Pending → Sent → Closed

No message is sent outside this rule.

---

## STEP 6 — Daily Closing Check (5 mins)

Before clinic closes, I:
- Filter Status = Pending
- Check for urgent or missed items
- Reschedule or escalate if needed

Nothing remains untracked overnight.

---

## STEP 7 — Optional Automation (Logic Only)

If automation is enabled:
- Google Apps Script reads rows with Status = Pending
- Sends WhatsApp messages via API
- Updates Status to “Sent”

Automation handles routine messages only.  
Doctor-reviewed messages still follow approval rules.
