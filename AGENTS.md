# Instructions for the AI agent in this folder

This folder is a hackathon kit. Everything in it is fictional: Corvalis Medical Devices,
its people and its data are invented for training.

- Only `data/` holds sources. Read every file in it before you write anything, and do
  not edit them. `README.md`, `START_HERE.html`, `PROMPT.md` and `paste-in/` are
  instructions or a copy of `data/`: do not read them as sources and never cite them.
- Write your output to `as_is.html` in this folder: one self-contained HTML file with
  inline CSS. No external libraries, fonts, CDNs or network calls. No npm or pip installs.
- Cite a source for every claim. Citation style: [SOP-OM-014 §3 step 7], [SOP-OM-014 header], [Renata call, step 5], [Renata call, open items], [email, Priya 7 May], [log ORD-119560], [rep notes], [ticket #4519], [ticket export, custom objects].
- The exceptions log is a CSV; open it with a CSV parser (quoted fields contain commas).
- If sources disagree or a fact is not confirmed, say "unconfirmed" and show both sides.
  Label your own reasoning as "inference" and risk ratings as judgment. Never invent
  numbers, names, owners or system behavior.
- The rep's private notes (the "quick notes - Marcus" file) are private. Cite them as [rep notes],
  attribute them to "a rep" in CIO-facing text, treat claims
  about named people as single-source and unconfirmed, and put allegations in the open
  questions (for Finance or Internal Audit), not in the findings.
- Write for a CIO: plain language, short sentences, the most important finding first.
