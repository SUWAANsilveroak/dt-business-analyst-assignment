# Task 2 – Checklists

These checklists ensure patient communication runs smoothly while protecting doctor time and avoiding message chaos.

---

## Daily Checklist (15–20 mins)

I perform the following steps during the day:

- Pull appointment and prescription data from HMS
- Update the **Care_Control** sheet
- Verify message types are correctly assigned
- Ensure routine messages are auto-filled
- Mark messages requiring doctor input as **Waiting**
- Batch patient questions from Google Form

---

## Doctor Review Checklist (Every 3–4 Hours | 10 mins)

Before meeting the doctor, I:

- Filter **Care_Control** to:
  - Doctor Approval = Required
  - Status = Waiting
- Keep only unresolved items

During review:
- Doctor dictates or approves responses
- I update message text and approval status

After review:
- Approved messages are marked **Pending** for dispatch

---

## Message Dispatch Checklist

Before sending any message, I confirm:

- Message Text is filled
- Status = Pending
- Doctor Approval = Not Required or Approved

After sending:
- Update Status to **Sent**
- Close the item once confirmed

---

## Patient Question Handling Checklist

- Collect questions via Google Form
- Batch questions every 3 hours
- Review unanswered questions with doctor once
- Record answers in **Patient_Questions**
- Send responses and update status

---

## End-of-Day Closing Checklist (5 mins)

Before clinic closes, I:

- Filter **Care_Control** for Status = Pending
- Check for urgent or incomplete items
- Ensure nothing critical is missed
- Reschedule follow-ups if required
