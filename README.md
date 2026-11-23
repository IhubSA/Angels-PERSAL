# Angels PERSAL · People & Payroll Hub (test system)

A working, clickable web app built from the **Angels PERSAL** design (20 screens) for Angels Resource Centres.
It runs entirely in the browser — no server, no database, no install — so it can be hosted free on **GitHub Pages** for testing.

> **Test system only.** All people and figures are fictional sample data. Everything a tester changes is saved in *their own browser* (localStorage) and can be wiped with **Reset demo data**. Do not enter real personal information.

---

## Put it on GitHub (about 5 minutes)

1. Sign in at **github.com** → click **+** (top right) → **New repository**.
2. Name it e.g. `angels-persal`, choose **Public** (GitHub Pages on a free account needs a public repo; use Private if you have GitHub Pro/Team), tick nothing else, click **Create repository**.
3. On the new repo page click **uploading an existing file**.
4. Unzip `angels-persal.zip` on your computer, open the `angels-persal` folder, select **everything inside it** (including the `css`, `js` and `assets` folders and the `.nojekyll` file) and drag it into the browser window.
   *Tip: on Mac press ⌘⇧. in Finder to show the hidden `.nojekyll` file; on Windows tick View → Hidden items. If you miss it, the site still works.*
5. Scroll down, click **Commit changes**.
6. Go to **Settings → Pages**. Under *Build and deployment* choose **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**, click **Save**.
7. Wait 1–2 minutes and refresh. The link appears at the top of the Pages screen, e.g.
   `https://<your-github-username>.github.io/angels-persal/` — share that link with testers.

To update later: open the repo → **Add file → Upload files** → drop the changed files → **Commit changes**. Pages republishes automatically.

### Run it on your own computer (optional)
Double-clicking `index.html` works in most browsers. For best results run a tiny local server in the folder:
`python -m http.server 8000` then open http://localhost:8000

---

## How testers use it

* **Switch test role** (bottom of the left menu, or bottom-left in the portals) to act as different people:
  | Role | Person (sample) | What they see |
  |---|---|---|
  | HR Administrator | Thandi Mokoena | PERSAL: captures requests, documents, imports |
  | HOD Human Resources | Dana | PERSAL: approves HR steps, discipline, EE fields, audit |
  | Head of Finance | Gerald | PERSAL: budget/payroll step, sends to SimplePay |
  | CEO | Lizelle | PERSAL: final approvals, closures |
  | Board Treasurer | Jim | Final step when the CEO is the subject |
  | Employee | Lerato Mokoena | **Leave portal** only (own leave) |
  | Direct manager | Sipho Ndlovu | **Leave portal** only (team approvals) |
  | QMS Administrator | — | **Risk tracker** only (no personal data) |
* **Reset demo data** (top bar or sidebar) restores the sample data.
* **Export / Import data** (sidebar) saves the tester's state to a JSON file and loads it again — handy for sharing a scenario.
* See **TESTING.md** for a step-by-step test script.

## What works

| Area | Highlights |
|---|---|
| Dashboard | Live tiles, "waiting for action", people by category, needs-attention checks |
| Post establishment | Filters, CSV register, create/fund/close posts through request 1.1 |
| Grading & salary scales | Step-gap slider, salary placement calculator, editable market rates → 5-step scales |
| Recruitment | Vacancies from vacant funded posts, editable/versioned templates with merge fields, replies inbox, applicant stages, start appointment |
| Internships & bursaries | Programme cards, people lists, stipend run that raises request 4.5 |
| People & person record | Search/filter, masked sensitive fields (every reveal logged), PERSAL number check-digit tool, EE fields restricted to HOD HR/CEO |
| Staff import | CSV upload, 8 pre-load checks, preview, HOD HR approval, bulk PERSAL numbers |
| Onboarding & exits | Checklists created automatically on appointment (2.2) and termination (5.1) |
| Documents | Upload with auto document codes/versions, required-documents checklist per category, verify/reject |
| Leave (HR) | All requests, entitlements, follow-ups (certificates, expiry warnings), December closure (3.7), unpaid → payroll |
| Leave portal | Apply with working-day count (SA public holidays incl. Sunday→Monday), balance checks, manager approve/decline with reason, escalation after 3 working days |
| Leave history import | Cut-over steps, per-person check, employee + HR sign-off, source CSV upload |
| Performance | HR-07 review form with reason rule (<3 or >4), register, PIP close/extend/escalate |
| Requests & approvals | 15 request types with their approval routes, approve / return / decline, resubmit, reverse (9.9), no self-approval, CEO-subject → Board |
| Payroll instructions | Approved pay changes, "sent to SimplePay", CSV batch export |
| Discipline & grievance | Confidential case register, step tracking, hearing record & grievance form, appeal, dismissal → 5.1 |
| Policies & compliance | Register, HR risk register (log/score/report/close with approvals), roll-out tracker, Board dashboard, audit packs, coverage check |
| Reports | Leave liability, cost per funder, headcount & turnover, EE counts, CSV exports, print-to-PDF |
| Roles & access, Audit log | Role matrix; filterable, exportable audit trail of every view and change |
| Risk tracker | QMS view of HR risks: alerts, QMS ID linking, trail, quarterly export |

## Project structure

```
index.html            app shell
css/app.css           styles (from the design: Manrope, brand #1F4E8C)
js/store.js           sample data, rules (routes, PERSAL numbers, leave days, holidays), saving
js/ui.js              layout, menu, role switcher, router, modals, CSV helpers
js/pages/*.js         the screens (org, people, requests, leave, hr, gov)
js/app.js             start-up
assets/               favicon and a sample staff-import CSV
SCREENS.md            design artboard → app page map
TESTING.md            test script for testers
```

## Before this becomes a live system
This prototype is for testing workflows and screens. A production version needs a real back end: Microsoft 365 sign-in, a secure database (POPIA), server-side permission checks and audit log, file storage for documents, and integrations with SimplePay, Jibble and the QMS Hub. Items marked **[to confirm]** in the screens are open policy decisions carried over from the design.
