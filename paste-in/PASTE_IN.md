# Paste-in mode (use only if Cursor does not work)

Copy everything below the line into any AI chat your firm allows; all the data is fictional.
If you picked another direction, change the Audience, Artifact and File name lines first.
Save the HTML the chat returns as a file ending in .html, then double-click it.

---

Imagine your client: their SAP program is facing challenges, and you need to create a view and an artifact to communicate with your executive clients. What would you build?

Our client is Corvalis Medical Devices (fictional). Its SAP S/4HANA program, Project Keystone, is in trouble, and the steering committee meets on 28 Oct 2026. The program office's data is at the end of this message, as JSON. Every record has an ID.

Audience: the steering committee, chaired by the CFO
Artifact: a one-page steering-committee view built around one clear decision ask
File name: steerco_onepager.html

1. Read all of the program data first.
2. Give me five lines: the so-what in one sentence, the decision you would ask for, and the three facts that support it, each with its record ID.
3. Then write the artifact as one self-contained HTML file:
   - do not copy the data into the page; write in the numbers you use, each taken from the data below;
   - lead with the so-what and the decision ask, then the evidence;
   - put the record ID next to every fact, like [M2], [D-02], [R-07], [budget], [V-03], [team OTC];
   - label anything you calculate or judge as "inference" and show the arithmetic;
   - working days are Monday to Friday with no holidays; money is in USD millions;
   - write for a busy executive: plain words, short sentences, no unexplained acronyms;
   - no external libraries, fonts or network calls.
   Return the whole file in one code block.
4. Then tell me the two questions this audience is most likely to push back with.

PROGRAM DATA (JSON):

```json
{
  "meta": {
    "client": "Corvalis Medical Devices",
    "clientNote": "Fictional mid-size medical device maker, about $1.4B revenue, US and Canada.",
    "program": "Project Keystone",
    "scope": "Replace Oracle E-Business Suite 12.1.3 with SAP S/4HANA for order to cash, source to pay, plan to produce, record to report and quality. 3 plants, 2 distribution centers, about 1,900 users.",
    "approach": "New implementation (greenfield), delivered with a systems integrator (the SI partner).",
    "currentPhase": "Design",
    "reportingCutoff": "2026-10-16",
    "previousCutoff": "2026-10-09",
    "compiledBy": "Program office, from the integrated plan, RAID log, staffing plan, budget tracker and value case.",
    "dataNote": "All data is fictional, made up for training."
  },

  "governance": {
    "programOffice": { "id": "PMO", "name": "Program office", "lead": "Lena Hoffmann, Program director", "note": "Records with team PMO belong to the program office, not to a delivery team." },
    "steeringCommittee": {
      "next": "2026-10-28",
      "chair": "Dana Whitfield, CFO (executive sponsor)",
      "members": [
        "Dana Whitfield, CFO (chair, executive sponsor)",
        "Owen Castellano, CIO",
        "Grace Adeyemi, COO (owns order to cash and the plants)",
        "Tomas Lindqvist, VP Quality",
        "Lena Hoffmann, Program director",
        "SI partner engagement lead"
      ]
    },
    "rules": [
      { "id": "G-1", "text": "A phase gate that slips more than 10 working days goes to the steering committee with a recovery plan." },
      { "id": "G-2", "text": "A team that has signed off its own design may start Build before the program gate (conditional start), with the program director's approval." }
    ],
    "calendar": [
      { "id": "C-01", "text": "No go-live during fiscal quarter-end close: 14 Jun to 9 Jul 2027 (Q2 FY2027 close).", "noGoLiveFrom": "2027-06-14", "noGoLiveTo": "2027-07-09", "source": "Finance calendar FY2027" },
      { "id": "C-02", "text": "Planning basis: five working days a week, no holiday adjustment.", "source": "Integrated plan" }
    ]
  },

  "milestones": [
    { "id": "M1", "phase": "Prepare", "name": "Prepare complete", "phaseStart": "2026-03-02", "baseline": "2026-04-24", "forecast": "2026-05-15", "status": "Done", "note": "Finished 15 working days late; the overrun was funded from contingency." },
    { "id": "M2", "phase": "Design", "name": "Design approval (program gate)", "phaseStart": "2026-04-27", "baseline": "2026-10-30", "forecast": "2026-11-20", "status": "Current", "note": "Forecast driven by overdue order to cash design work and decision D-02. Quality design (decision D-08) is the next constraint." },
    { "id": "M3", "phase": "Build", "name": "Build complete", "phaseStart": "2026-11-02", "baseline": "2027-02-12", "forecast": "2027-03-05", "status": "Not started", "note": "Build baseline starts 2 Nov 2026." },
    { "id": "M4", "phase": "Test", "name": "Test complete (user acceptance sign-off)", "phaseStart": "2027-02-15", "baseline": "2027-04-30", "forecast": "2027-05-21", "status": "Not started", "note": "Test baseline starts 15 Feb 2027." },
    { "id": "M5", "phase": "Deploy", "name": "Go-live", "phaseStart": "2027-05-03", "baseline": "2027-06-07", "forecast": "2027-06-28", "status": "Not started", "note": "Cutover baseline 3 May to 4 Jun 2027." },
    { "id": "M6", "phase": "Hypercare", "name": "Hypercare exit", "phaseStart": "2027-06-07", "baseline": "2027-07-30", "forecast": "2027-08-20", "status": "Not started", "note": "" }
  ],
  "phaseStartNote": "phaseStart is the baseline start of each phase. Design actually started on 18 May, after the Prepare overrun.",
  "forecastBasis": "Forecasts after M2 assume the Design slip carries through unchanged. No recovery and no calendar limits are applied.",

  "teams": [
    {
      "id": "OTC", "name": "Order to Cash", "lead": "Marta Kowalski",
      "reportedStatus": "green",
      "reportedNote": "Workshops catching up after quarter-end close. No impact expected on Design sign-off.",
      "design": { "total": 34, "done": 19, "overdue": 6, "blocked": 1 },
      "fte": { "planned": 7, "actual": 6 },
      "signal": "6 design activities overdue. Credit management design is blocked by decision D-02, which has no owner.",
      "buildNeed": "Build needs 4 pricing and credit specialists full-time from 23 Nov. Today 2 are assigned, each at 0.5 FTE. Both go full-time on 23 Nov, when their close duties pass to a backfill already in the budget. The other 2 must come from outside (R-07, D-05).",
      "onCriticalPath": true
    },
    {
      "id": "S2P", "name": "Source to Pay", "lead": "Daniel Reyes",
      "reportedStatus": "green",
      "reportedNote": "Design complete except one approval. Ready to start Build on 2 Nov.",
      "design": { "total": 28, "done": 27, "overdue": 0, "blocked": 0 },
      "fte": { "planned": 5, "actual": 5 },
      "signal": "No overdue or blocked design work.",
      "onCriticalPath": false
    },
    {
      "id": "PTP", "name": "Plan to Produce", "lead": "Hiro Saito",
      "reportedStatus": "amber",
      "reportedNote": "One workshop moved (device history record). Recoverable within the phase.",
      "design": { "total": 31, "done": 26, "overdue": 1, "blocked": 0 },
      "fte": { "planned": 6, "actual": 6 },
      "signal": "1 design workshop overdue (device history record).",
      "onCriticalPath": false
    },
    {
      "id": "R2R", "name": "Record to Report", "lead": "Claire Dubois",
      "reportedStatus": "green",
      "reportedNote": "On plan.",
      "design": { "total": 26, "done": 24, "overdue": 0, "blocked": 0 },
      "fte": { "planned": 5, "actual": 5 },
      "signal": "No overdue or blocked design work.",
      "onCriticalPath": false
    },
    {
      "id": "QM", "name": "Quality and Compliance", "lead": "Tomas Lindqvist",
      "reportedStatus": "amber",
      "reportedNote": "Waiting on the validation approach decision (D-08).",
      "design": { "total": 18, "done": 11, "overdue": 3, "blocked": 0 },
      "fte": { "planned": 4, "actual": 4 },
      "signal": "3 design activities overdue. 0 of 3 QA reviewers named. Validation approach (D-08) still open.",
      "onCriticalPath": true
    },
    {
      "id": "DATA", "name": "Data Migration", "lead": "Ayesha Rahman",
      "reportedStatus": "amber",
      "reportedNote": "Mock 1 lessons learned under review. Cleansing plan in draft.",
      "design": { "total": 22, "done": 14, "overdue": 3, "blocked": 1 },
      "fte": { "planned": 6, "actual": 5.5 },
      "signal": "Mock load 1 loaded 71% of records clean against a 95% target. 1,240 suspected duplicate customers.",
      "kpis": [
        { "name": "Mock load 1: records loaded clean", "value": 71, "target": 95, "unit": "%", "date": "2026-10-05" },
        { "name": "Suspected duplicate customer records", "value": 1240, "of": 18600, "unit": "records" }
      ],
      "onCriticalPath": false
    },
    {
      "id": "INT", "name": "Integration", "lead": "Ben Okafor",
      "reportedStatus": "green",
      "reportedNote": "31 of 42 interfaces specified. On plan.",
      "design": { "total": 42, "done": 31, "overdue": 1, "blocked": 0 },
      "fte": { "planned": 5, "actual": 5 },
      "signal": "The 3PL warehouse partner's test environment is ready 14 Dec; Build needs it from 23 Nov (R-09).",
      "onCriticalPath": false
    },
    {
      "id": "TEST", "name": "Testing", "lead": "Julia Novak",
      "reportedStatus": "green",
      "reportedNote": "Test strategy approved. Test case drafting started.",
      "design": { "total": 16, "done": 12, "overdue": 0, "blocked": 1 },
      "fte": { "planned": 3, "actual": 3 },
      "signal": "Test environment (QAS) ready date moved from 9 Nov to 23 Nov (I-03).",
      "onCriticalPath": false
    },
    {
      "id": "OCM", "name": "Change Management", "lead": "Sam Whitaker",
      "reportedStatus": "green",
      "reportedNote": "Change impact assessment 80% complete.",
      "design": { "total": 14, "done": 12, "overdue": 0, "blocked": 0 },
      "fte": { "planned": 3, "actual": 3 },
      "signal": "No overdue or blocked design work.",
      "onCriticalPath": false
    },
    {
      "id": "TECH", "name": "Basis and Infrastructure", "lead": "Felix Brandt",
      "reportedStatus": "amber",
      "reportedNote": "QAS rebuild in progress.",
      "design": { "total": 20, "done": 15, "overdue": 2, "blocked": 0 },
      "fte": { "planned": 4, "actual": 4 },
      "signal": "2 activities overdue on the QAS test environment rebuild.",
      "onCriticalPath": false
    }
  ],

  "risks": [
    { "id": "R-04", "team": "DATA", "title": "Customer and material master data quality", "description": "Mock load 1 loaded 71% of records clean (target 95%). 1,240 suspected duplicate customer records out of 18,600 active. Mock load 2 on 7 Dec is at risk.", "likelihood": "High", "impact": "High", "owner": "Ayesha Rahman", "raised": "2026-10-07", "trend": "Worse", "nextStep": "Agree who owns the cleanup (D-06) and draft the cleansing plan (A-15) before mock load 2 on 7 Dec.", "nextStepDue": "2026-10-23", "links": ["D-06", "A-15"] },
    { "id": "R-07", "team": "OTC", "title": "Pricing and credit specialists split with quarter-end close", "description": "The two pricing and credit specialists also run quarter-end close, each at 0.5 FTE on the program. Order to cash workshops slip whenever close is busy. Build needs four full-time from 23 Nov: these two, once a backfill takes over their close duties, plus two more from outside.", "likelihood": "High", "impact": "High", "owner": "Marta Kowalski", "raised": "2026-08-21", "trend": "Worse", "nextStep": "Fund two contract specialists (D-05) and start the close backfill on 23 Nov.", "nextStepDue": "2026-10-30", "links": ["D-05", "O-1"] },
    { "id": "R-09", "team": "INT", "title": "3PL partner test environment late", "description": "The 3PL warehouse partner's test environment is not available until 14 Dec. Shipping interfaces need it from 23 Nov for Build.", "likelihood": "Medium", "impact": "High", "owner": "Ben Okafor", "raised": "2026-09-25", "trend": "Same", "nextStep": "Ask the partner to bring its test environment forward (A-16); use simulated shipping messages in Build until then.", "nextStepDue": "2026-10-21", "links": ["A-16"] },
    { "id": "R-11", "team": "QM", "title": "Validation approach not agreed", "description": "The validation approach for quality processes is not agreed (D-08) and no QA reviewers are named. Full scripted validation would add about 3 weeks to Test.", "likelihood": "High", "impact": "Medium", "owner": "Tomas Lindqvist", "raised": "2026-09-11", "trend": "Same", "nextStep": "Decide the validation approach (D-08) and name three QA reviewers.", "nextStepDue": "2026-11-06", "links": ["D-08"] },
    { "id": "R-12", "team": "PMO", "title": "Go-live date and fiscal quarter-end close", "description": "If the Design slip is not recovered, the go-live date moves toward the fiscal quarter-end close.", "likelihood": "Medium", "impact": "High", "owner": "Lena Hoffmann", "raised": "2026-10-15", "trend": "New", "nextStep": "Take a recovery plan to the steering committee (rule G-1).", "nextStepDue": "2026-10-28", "links": ["M2", "M5", "G-1"] },
    { "id": "R-05", "team": "TECH", "title": "Production system sizing", "description": "Production sizing is based on 2025 order volumes; growth is not modeled.", "likelihood": "Medium", "impact": "Medium", "owner": "Felix Brandt", "raised": "2026-08-14", "trend": "Same", "nextStep": "Add three years of order growth to the sizing model.", "nextStepDue": "2026-12-04", "links": [] },
    { "id": "R-03", "team": "OCM", "title": "Super-user nominations", "description": "Two of the three plants have not named their super-users.", "likelihood": "Low", "impact": "Medium", "owner": "Sam Whitaker", "raised": "2026-09-18", "trend": "Better", "nextStep": "Plant managers name their super-users.", "nextStepDue": "2026-11-13", "links": [] }
  ],

  "issues": [
    { "id": "I-03", "team": "TECH", "title": "Test environment (QAS) rebuild", "description": "A failed system copy forced a rebuild. Ready date moved from 9 Nov to 23 Nov.", "severity": "Medium", "owner": "Felix Brandt", "raised": "2026-10-12" },
    { "id": "I-05", "team": "OTC", "title": "Order to cash workshops overdue", "description": "6 order to cash design activities are overdue; workshops have been rescheduled twice.", "severity": "High", "owner": "Marta Kowalski", "raised": "2026-09-30" }
  ],

  "decisions": [
    {
      "id": "D-02", "team": "OTC", "status": "Open",
      "title": "Credit check for rush orders (design decision KDD-07)",
      "question": "Should rush orders get a credit check with a fast release, or keep today's practice of no check?",
      "options": [
        "A: Credit check on every order, with a 2-hour release target for rush orders (the order to cash lead recommends A).",
        "B: No credit check for rush orders, as today."
      ],
      "context": "Today rush orders skip the credit check. Two rush orders shipped to past-due accounts last quarter.",
      "raised": "2026-09-04", "neededBy": "2026-10-09",
      "owner": null, "ownerNote": "Unassigned: the Credit Manager role is vacant.",
      "blocks": "Order to cash credit management design, and so the Design gate (M2). Also the value estimate V-03."
    },
    {
      "id": "D-06", "team": "DATA", "status": "Open",
      "title": "Owner of customer master cleanup",
      "question": "Does Sales Operations or the Data Migration team own removing duplicate customers before conversion?",
      "options": ["A: Sales Operations owns it, the Data team supports.", "B: The Data team owns it, Sales Operations confirms."],
      "context": "1,240 suspected duplicates (R-04). Nobody has started the cleanup.",
      "raised": "2026-10-07", "neededBy": "2026-10-23",
      "owner": "Lena Hoffmann",
      "blocks": "Data cleansing before mock load 2 on 7 Dec."
    },
    {
      "id": "D-05", "team": "OTC", "status": "Open",
      "title": "Fund two contract pricing and credit specialists for Build",
      "question": "Approve $0.62M from contingency for two contract specialists, 23 Nov 2026 to 12 Feb 2027?",
      "options": ["A: Approve, so order to cash Build starts on 23 Nov with 4 of 4 specialists full-time.", "B: Do not approve; order to cash Build starts with 2 of 4."],
      "context": "Contractors need 3 weeks to onboard, so approval is needed by 30 Oct for a 23 Nov start.",
      "raised": "2026-10-02", "neededBy": "2026-10-30",
      "owner": "Dana Whitfield",
      "cost": 0.62,
      "blocks": "Order to cash Build staffing (R-07). Needed for recovery option O-1."
    },
    {
      "id": "D-08", "team": "QM", "status": "Open",
      "title": "Validation approach for quality processes",
      "question": "Risk-based assurance (test what matters most) or full scripted validation of every quality process?",
      "options": ["A: Risk-based assurance.", "B: Full scripted validation (adds about 3 weeks to Test)."],
      "context": "Regulators accept a risk-based approach if it is documented. Quality has not chosen.",
      "raised": "2026-09-11", "neededBy": "2026-11-06",
      "owner": "Tomas Lindqvist",
      "blocks": "Quality design sign-off and the Test plan (R-11)."
    },
    {
      "id": "D-01", "team": "PMO", "status": "Decided",
      "title": "Implementation approach",
      "question": "New implementation or system conversion?",
      "options": ["New implementation (greenfield)."],
      "context": "Decided by the steering committee.",
      "raised": "2026-02-10", "neededBy": "2026-03-20", "decided": "2026-03-20",
      "owner": "Dana Whitfield",
      "blocks": ""
    }
  ],

  "actions": [
    { "id": "A-14", "title": "Name an owner for D-02 (credit check for rush orders)", "owner": "Lena Hoffmann", "due": "2026-10-14", "status": "Open" },
    { "id": "A-15", "title": "Draft the duplicate-customer cleansing plan", "owner": "Ayesha Rahman", "due": "2026-10-23", "status": "Open" },
    { "id": "A-16", "title": "Ask the 3PL partner to bring its test environment forward", "owner": "Ben Okafor", "due": "2026-10-21", "status": "Open" },
    { "id": "A-11", "title": "Approve the test strategy", "owner": "Julia Novak", "due": "2026-10-02", "status": "Done" }
  ],

  "recoveryOptions": [
    {
      "id": "O-1", "name": "Recover in Build and hold go-live on 7 Jun 2027",
      "how": "Name an owner and decide D-02 at the 28 Oct steering committee. Approve D-05 by 30 Oct. Teams that sign off their own design by 2 Nov start Build under rule G-2 (Source to Pay is closest, at 27 of 28). Order to cash starts Build on 23 Nov, three weeks late, and catches up by 12 Feb with four full-time specialists. Quality chooses risk-based assurance (D-08 option A) by 6 Nov.",
      "cost": 0.62,
      "confidence": "Medium (program office estimate; there is no detailed recovery schedule yet)",
      "needs": ["D-02", "D-05", "D-08", "G-2"]
    },
    {
      "id": "O-2", "name": "Accept the slip and set a new go-live date",
      "how": "Re-plan Build, Test and Deploy from the 20 Nov Design gate.",
      "cost": null,
      "costNote": "Not estimated yet.",
      "confidence": "Not assessed",
      "needs": []
    }
  ],

  "budget": {
    "currency": "USD", "unit": "millions",
    "approved": 48.0,
    "spentToDate": 21.6,
    "plannedToDate": 21.4,
    "forecastAtCompletion": 48.0,
    "forecastLastUpdated": "2026-09-04",
    "weeklyRunRate": 0.68,
    "runRateSplit": { "SI partner": 0.42, "Internal team and backfill": 0.20, "Other": 0.06 },
    "runRateNote": "Average actual spend per week over the last 6 weeks: ($21.6M - $17.5M) / 6 weeks.",
    "categories": [
      { "name": "SI partner fees", "approved": 26.5, "spentToDate": 12.6 },
      { "name": "Internal team and backfill", "approved": 9.8, "spentToDate": 4.7 },
      { "name": "Software subscriptions", "approved": 6.2, "spentToDate": 3.6 },
      { "name": "Data and test tooling", "approved": 1.5, "spentToDate": 0.7 }
    ],
    "contingency": {
      "approved": 4.0, "drawn": 1.6, "remaining": 2.4,
      "draws": [
        { "date": "2026-05-20", "amount": 1.1, "reason": "Prepare overran by 3 weeks" },
        { "date": "2026-09-28", "amount": 0.5, "reason": "Extra sandbox and test system capacity" }
      ],
      "note": "The $1.6M drawn from contingency was spent inside the categories above, so spent to date ($21.6M) already includes it."
    }
  },

  "valueCase": {
    "currency": "USD", "unit": "millions per year at full run rate",
    "startRule": "Every benefit line starts a fixed number of months after go-live. If go-live moves, every line moves with it.",
    "lines": [
      { "id": "V-01", "team": "S2P", "name": "Procurement savings", "annual": 7.2, "financeValidated": true, "startsAfterGoLiveMonths": 3, "owner": "Daniel Reyes" },
      { "id": "V-02", "team": "PTP", "name": "Lower inventory carrying cost", "annual": 5.4, "financeValidated": true, "startsAfterGoLiveMonths": 6, "owner": "Hiro Saito" },
      { "id": "V-03", "team": "OTC", "name": "Fewer credit write-offs and faster collection", "annual": 3.1, "financeValidated": false, "startsAfterGoLiveMonths": 3, "owner": "Marta Kowalski", "note": "Estimate. Depends on the rush-order credit check design (D-02)." },
      { "id": "V-04", "team": "R2R", "name": "Faster financial close", "annual": 1.8, "financeValidated": true, "startsAfterGoLiveMonths": 2, "owner": "Claire Dubois" },
      { "id": "V-05", "team": "TECH", "name": "Retire Oracle E-Business Suite licenses and hosting", "annual": 4.5, "financeValidated": true, "startsAfterGoLiveMonths": 4, "owner": "Owen Castellano" }
    ]
  },

  "changesThisWeek": [
    { "type": "concern", "text": "Design gate forecast moved from 6 Nov to 20 Nov: now 15 working days late (was 5).", "refs": ["M2"] },
    { "type": "concern", "text": "Decision D-02 passed its needed-by date (9 Oct) and still has no owner. Action A-14 to name one is overdue.", "refs": ["D-02", "A-14"] },
    { "type": "concern", "text": "Mock load 1: 71% of records loaded clean against a 95% target.", "refs": ["R-04"] },
    { "type": "concern", "text": "Test environment (QAS) now ready 23 Nov (was 9 Nov).", "refs": ["I-03"] },
    { "type": "new", "text": "New risk R-12: go-live date and fiscal quarter-end close.", "refs": ["R-12"] },
    { "type": "opportunity", "text": "Source to Pay has finished 27 of 28 design activities and could start Build on 2 Nov under rule G-2.", "refs": ["S2P", "G-2"] }
  ],

  "history": {
    "cutoffs": ["2026-09-04", "2026-09-11", "2026-09-18", "2026-09-25", "2026-10-02", "2026-10-09", "2026-10-16"],
    "designGateForecast": ["2026-10-30", "2026-10-30", "2026-11-03", "2026-11-04", "2026-11-06", "2026-11-06", "2026-11-20"],
    "designDonePct": [64, 67, 69, 71, 73, 75, 76],
    "overdueActivities": [5, 6, 8, 9, 11, 12, 16],
    "spentToDate": [17.5, 18.2, 18.9, 19.5, 20.2, 20.9, 21.6],
    "plannedToDate": [17.4, 18.1, 18.8, 19.4, 20.1, 20.7, 21.4],
    "teamsRedOnEvidence": [0, 0, 1, 1, 1, 1, 3]
  },

  "glossary": {
    "Design gate": "The formal approval that ends the Design phase. Build should not start before it, except under rule G-2.",
    "Working days": "Monday to Friday. The plan does not adjust for holidays (C-02).",
    "FTE": "Full-time equivalent: 0.5 FTE is a person working half their time on the program.",
    "RAID": "Risks, actions, issues and decisions: the program's log of what could go wrong and what needs deciding.",
    "Reported status": "The status a team lead writes in the weekly report.",
    "Evidence status": "The status the dashboard computes from the data: red if 3 or more design activities are overdue or the team is 1 FTE or more short; amber if any activity is overdue or blocked or the team is short at all; green otherwise.",
    "Mock load": "A rehearsal of moving data from the old system to SAP. The share loaded clean shows data readiness.",
    "QAS": "The test system where integrated testing runs.",
    "3PL": "Third-party logistics: the outside warehouse partner that ships orders.",
    "KDD": "Key design decision.",
    "SI partner": "The systems integrator delivering the program with Corvalis."
  }
}
```
