# Task 1 – Sample Tables & Supporting Logic

This document contains sample tables and simple logic used to support the daily inventory micro-audit system.

All examples are based on the **sample data provided in the assignment** and are meant to demonstrate execution, not reconciliation.

---

## 1. High-Risk Medicine List (One-time Setup)

| Medicine (Master Name) | Reason for High Risk |
|------------------------|---------------------|
| Dolo 650 | High daily sales volume and multiple name variants |
| Azithromycin 500 | Common abbreviations and similar names |
| Pantoprazole 40 | Frequently prescribed medicine |

This list is reviewed monthly and updated if patterns change.

---

## 2. Name-Variation Mapping Table

This table is used to normalize manually entered sales names.

| Entered Name Variant | Mapped Master Name |
|---------------------|-------------------|
| Dolo | Dolo 650 |
| Dolo kind | Dolo 650 |
| Azithro 500 | Azithromycin 500 |
| Azithromycin | Azithromycin 500 |

New variants are added only when observed during daily checks.

---

## 3. Daily Usage Reasonableness Check (Example)

| Medicine | Opening Stock | Purchases | Sales | Expected Closing | Actual Closing | Difference |
|---------|---------------|-----------|-------|------------------|----------------|------------|
| Dolo 650 | 1000 | 500 | 40 | 1460 | 1440 | -20 |

Tolerance is predefined and the for better visuals i can add filter if it goes beyond 2% slab it will automatic turned into red.  
Differences beyond tolerance trigger a review of sales entries.

---

## 4. Error Log (Pattern Tracking)

| Date | Medicine | Error Type | Repeated |
|------|----------|------------|----------|
| Aug 1 | Dolo 650 | Name variant | Yes |
| Aug 3 | Dolo 650 | Quantity mismatch | No |

This log is reviewed weekly to decide retraining or SOP updates.

---

## 5. Data Validation Logic (Preventive Control)

To reduce name-related errors at the source, I apply data validation wherever direct control is possible and suggest system-level controls where it is not.

---

### A. Validation in Sheets-Based Systems (Direct Control)

For **Opening Inventory**, **Purchase Register**, and **Closing Inventory**, which are typically maintained in Excel or Google Sheets:

- The **Medicine (Master Name)** column acts as the single source of truth
- This master list is used as the data validation range
- Staff can select medicine names only from this list
- The list is sorted alphabetically for ease of use

Supporting controls:
- A simple SOP is shared with staff
- No free-text medicine entry is allowed
- New medicines are added only through the master list

---

### B. Validation in Sales Register (HMS – Indirect Control)

The Sales Register is generated from the **HMS**, where direct sheet-level validation may not be available.

In this case, my approach is:
- Engage with the HMS vendor or internal tech team
- Request configuration of medicine names as a selectable master list
- Disable or restrict free-text medicine entry where possible
- Align HMS medicine names with the clinic master list

Until HMS-level validation is implemented:
- Daily name-variation checks act as a temporary control
- New variants are logged and corrected at the source

---

### Outcome

- Name-variation errors reduce significantly across systems
- Dependency on daily name-mapping reduces over time
- Inventory mismatches become less frequent
- Manual follow-up with billing staff is minimized
