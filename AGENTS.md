# Instructions for the AI agent in this folder

This folder is a hackathon kit. Everything in it is fictional: Corvalis Medical Devices,
Project Keystone, its people and its numbers are invented for training.

## What is here

- `single_source_of_now.html`: the program office's dashboard (Executive, Program
  management, Team lead). The program data is at the top of this file, in the
  `window.PROGRAM = {...}` block: the single source of truth. Read it in full before you
  write anything. The dashboard code below it shows the look and helpers such as the
  working-day count and the evidence-status rule.
- `README.md`, `START_HERE.html`, `PROMPT.md` and `paste-in/`: instructions for people,
  not data. Never cite them.

## How to build

- Build each artifact as one self-contained HTML file in this folder, with inline CSS and JS.
- Write in the numbers you use, each taken from the program data, with its record ID.
  Don't copy the whole data block into your file.
- Do not use `fetch()`, ES modules, import maps or a dev server: the page is opened from
  disk (file://), where those fail.
- No external libraries, CDNs, web fonts or network calls. No npm or pip installs.
  Draw charts with inline SVG or HTML and CSS.
- The file must open by double-click in Chrome, Edge or Safari, and print cleanly.
- Keep `single_source_of_now.html` working. Change its data block only when the table
  asks you to change the story. Then update every record the change touches (milestone
  forecasts, team status, RAID items, recovery options), add a line to `changesThisWeek`,
  keep dates as YYYY-MM-DD (put an unknown date in a note and say it is unknown), and
  check the dashboard still opens. Then update the table's artifact to match.

## Evidence rules

- Take every number, date, name and owner from the program data. Never invent one.
- Put the record ID next to every fact. Where a fact has no record ID, cite its section:
  [meta], [governance], [budget], [value], [history]. Styles: [M2], [D-02], [R-07], [I-03], [A-14], [O-1], [G-1], [C-01], [V-03], [team OTC], [budget], [history].
- Anything you calculate, estimate or judge, label "inference" and show the arithmetic,
  for example: "2 specialists x 0.5 FTE = 1 FTE (inference)".
- Dates: the data is the weekly pack as of the reporting cutoff, Fri 16 Oct 2026. Write as
  of that week, for the steering committee on Wed 28 Oct. Working days are Monday to
  Friday, with no holidays (rule C-02). Money is in USD millions unless the data says
  otherwise.
- If the data does not say something, write "not in the data" instead of guessing.

## Writing for executives

- Lead with the so-what and the decision you need, then the evidence.
- Plain words, short sentences, active voice. Explain every acronym or avoid it.
- Put the answer (so-what and ask) on the first screen. Supporting detail and arithmetic
  can follow below it.
- Every ask names who decides, what, and by when.
