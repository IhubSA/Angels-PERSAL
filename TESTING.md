# Test script

Start each session with **Reset demo data** so everyone tests from the same point. Switch roles with **Switch test role** in the left menu (bottom-left box in the leave portal and risk tracker).

## 1. Salary increase through the full approval route
1. Role **HOD Human Resources** → Approvals → open **PR-26-0412** (Nomsa Dlamini) → *Approve and send to Head of Finance*.
2. Role **Head of Finance** → same request → *Approve and send to CEO*.
3. Role **CEO** → *Give final approval*. ✔ Nomsa's person record now shows the new salary and step; the History and Audit log show each step.
4. Try **Return for revision** without a comment — it should refuse.

## 2. New appointment → PERSAL number → onboarding
1. Role **Head of Finance** → approve **PR-26-0410** (Precious Maseko); role **CEO** → final approval.
2. ✔ A new person exists with an 8-digit PERSAL number (check it with *Check a number* on the person record), post 0400004 shows *Filled*, and an onboarding checklist appears under Onboarding & exits.

## 3. Leave portal
1. Role **Employee** → apply for annual leave over 27 April 2027 (Freedom Day is skipped from the day count).
2. Role **Direct manager** → *Team approvals* → Approve (or Decline — a reason is required).
3. ✔ Lerato's annual balance drops. Apply for **Unpaid** leave and approve it: a payroll instruction (3.8) appears for HOD HR → Head of Finance.

## 4. Self-approval and the Board
1. Role **HR Administrator** → People → Lizelle (CEO) → *Salary increase (4.2)* → Submit.
2. ✔ The route ends with **Board Treasurer** instead of the CEO. Role **CEO** cannot approve it.

## 5. Staff import
1. Role **HR Administrator** → Staff import → *Load sample file* (or upload `assets/samples/sample-staff-import.csv`).
2. ✔ Row "Lwazi Dube" fails two checks. *Send for HOD HR approval* → role **HOD HR** → *Approve and load*.

## 6. Documents, performance, discipline, risks
* Documents: choose a person, attach any PDF/JPG, upload → *Verify* or *Reject* (reason required).
* Performance: give a KPA a 5 without a reason → blocked; add a reason → saved to the register. A rating of 1–2 opens a PIP.
* Discipline & grievance (HR roles only): complete the hearing record for DC-26-005 and issue the outcome.
* Policies → Risk register → *+ Log a risk*; change its status; role **QMS Administrator** sees it in the risk tracker without names.

## 7. Restricted data
* Person record → *Show* on ID, tax, account or salary → each view is written to the Audit log.
* Employment Equity fields open only for **HOD HR** and **CEO**.

Please note anything confusing, missing or wrong (screen, role, what you did, what you expected).
