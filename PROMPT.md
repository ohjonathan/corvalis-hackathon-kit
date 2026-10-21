You are my analyst on an SAP S/4HANA discovery team. I am the design lead for Corvalis Medical Devices, which runs order-to-cash on Oracle E-Business Suite 12.1.3 and is moving to SAP S/4HANA. On Monday I walk the Corvalis CIO through how Standard Sales Order Entry really works today.

The folder data/ holds everything discovery collected for this one process: the official SOP, a walkthrough call, an email thread, an exceptions log, a rep's private notes and an IT ticket export. Only data/ holds sources.

1. Read every file in data/ in full before writing anything.
2. Build as_is.html in this folder: one self-contained HTML page (inline CSS, no external libraries, fonts or network calls) with:
   - at the top, the three findings that matter most for the S/4HANA design, each with the one decision you would ask the CIO to make on Monday;
   - the process as it actually runs today, step by step: who does what, on which screen;
   - a table of gaps between what the SOP says and what really happens. Include anything the SOP is silent on or puts out of scope if it happens during order entry. For each gap: what the SOP says, what actually happens, the evidence, the risk (type: financial, control, customer or data; and High, Medium or Low), who owns it in practice today (a named person or role with a citation, "nobody" if a source shows no one does, or "unconfirmed" if no source says), and the design question it raises, in S/4HANA terms where you can (for example credit management, Business Partner, availability check, pricing conditions, item categories);
   - a short list of open questions for the CIO.
3. Cite the source for every claim, in this style: [SOP-OM-014 §3 step 7], [Renata call, step 5], [email, Priya 7 May], [log ORD-119560], [rep notes], [ticket #4519]. If sources disagree or something is not confirmed, write "unconfirmed" and show both sides. Label your own reasoning as "inference". Do not invent facts.

Here is one gap row, using a minor finding so you can see the format:
SOP says: next scheduled review 2023-03-15 [SOP-OM-014 header]. Reality: the file copy is stamped "REVIEW OVERDUE" [SOP-OM-014 header], and new reps learn by two days of shadowing because "a lot of it doesn't match what we actually do" [Renata call, flagged items]. Risk: control; Low. Owner today: Process Excellence Group owns the SOP on paper [SOP-OM-014 header]; nobody is keeping it current (inference). S/4HANA question: who keeps process documentation current after go-live?

When the page is done, tell me in the chat what you would check next.
