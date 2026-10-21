# Corvalis Medical Devices: all discovery sources in one file
Fictional training data. Use this file in paste-in mode, together with PROMPT.md.

---

## FILE: SOP-OM-014 Standard Sales Order Entry v3.0 (2021).md

_The official procedure for this process._

**CONTROLLED DOCUMENT — Corvalis Medical Devices, Inc.**
**SOP-OM-014: Standard Sales Order Entry**
Version 3.0 | Effective Date: 2021-03-15 | Owner: Process Excellence Group
Next scheduled review: 2023-03-15 *(note stamped on file copy: "REVIEW
OVERDUE")*

## 1. Purpose
This procedure describes how an Order Entry Clerk enters a standard sales
order for an existing customer in the Oracle E-Business Suite Order
Organizer.

## 2. Scope
Applies to all domestic standard orders for finished-goods items shipped
from the Fargo, ND distribution center. Rush orders, configure-to-order
items, and international orders are covered under separate procedures
(SOP-OM-015, SOP-OM-020, SOP-OM-031 respectively — not attached).

## 3. Procedure

1. Log in to the Order Organizer under the Order Management Super User
   responsibility.
2. Enter the customer number. The system will validate the customer exists
   and is not on Customer Hold.
3. Confirm the ship-to and bill-to sites default correctly from the
   customer record. If incorrect, select the correct site from the
   list of values.
4. Enter the line: item number, quantity ordered, and requested ship date.
5. The system will apply pricing automatically from the price list
   assigned to the customer. Order Entry Clerks are **not authorized** to
   override pricing under any circumstances. Any pricing exception must be
   submitted in writing to the Pricing Committee for approval prior to
   order entry.
6. The system performs an Available-to-Promise (ATP) check on the line
   automatically. If the item is unavailable, the Clerk should advise the
   customer of the expected ship date and proceed with entry; the order
   will backorder automatically.
7. Upon booking, the system runs an automated credit check against the
   customer's aggregate open accounts receivable balance. Orders that
   would bring the customer's aggregate open balance above **$10,000**
   are placed on CREDIT HOLD automatically and routed to the Credit
   Department for review and release. No order on CREDIT HOLD may be
   released by anyone outside the Credit Department.
8. Once the order passes credit check (or is released from hold), the
   Clerk clicks Book Order. This completes the Standard Sales Order Entry
   procedure. Subsequent steps (pick release, ship confirm, invoicing) are
   covered under SOP-OM-018, SOP-OM-019, and SOP-FIN-004 respectively.

## 4. Roles
- **Order Entry Clerk** — enters the order per steps 1–8 above.
- **Credit Department** — reviews and releases orders on CREDIT HOLD.
- **Pricing Committee** — approves any pricing exception prior to entry.

## 5. Revision History
| Version | Date | Summary |
|---|---|---|
| 1.0 | 2018-06-01 | Initial release |
| 2.0 | 2019-11-20 | Updated for Order Organizer terminology change |
| 3.0 | 2021-03-15 | Added credit hold threshold detail |

*(Handwritten margin note on the file copy, initials "H.P.", undated:
"is this still $10K? check with Priya" — no further annotation.)*

---

## FILE: notes - call w Renata Diaz (order entry walkthrough) 04-27.md

_Discovery call with the Inside Sales supervisor._

# Discovery call notes — Order Entry walkthrough

**Date:** 2026-04-27
**Attendee:** Renata Diaz, Inside Sales Supervisor (manages the 5-person Inside
Sales / Order Entry team out of the Minneapolis office)
**Taken by:** (discovery analyst — notes only, not verbatim transcript)

## Context
Renata's team takes phone and email orders from hospitals, surgery centers and
a couple of regional distributors for Corvalis's wound-care and single-use
surgical instrument lines. She walked through a "normal" order start to
finish on a screen-share, using a test/training account so nothing real was
booked.

## Walkthrough, in her words (tightened)

1. Rep opens the **Sales Order Workbench** (she also calls it "the order
   screen" a couple times) under the Order Management responsibility.
2. Types in the customer number if the rep already knows it (most of her
   reps have their regular accounts memorized), or looks it up by customer
   name. She said "the system will show you if they're an existing customer
   or not" but when I asked exactly how that works — is it an exact name
   match, a fuzzy search, does it flag possible duplicates — she said "I'd
   have to actually go check, I've just never had to think about it because
   my reps mostly know their own accounts already." Did not have a firm
   answer.
3. Ship-to defaults in from the customer record. She said for most of her
   accounts there's only one ship-to site so this isn't really a decision
   point. When I asked what happens for a hospital system with multiple
   receiving docks/campuses, she paused and said "that's more of an edge
   case, I don't do a lot of those myself" — didn't have a confirmed answer
   for how the rep picks the right one.
4. Rep adds the line: item number (catalog codes like WD-2200 for the
   standard wound dressing kit, SI-8800 for the basic surgical instrument
   kit), quantity, and requested date.
5. Pricing comes in automatically off the price list attached to the
   customer — she was very confident about this part: **"We've been
   100% list price for well over a year now. Sales stopped doing manual
   overrides after the pricing cleanup project. It's just not a thing
   anymore."** I asked if there was ever an exception process for a manual
   discount and she said "not that I'm aware of, not on my team anyway."
6. Availability shows on the line automatically — she called it "the ATP
   check," said it's basically instant, red or green, and that reps just
   read it off the screen.
7. Credit check she described as automatic and invisible on a normal order
   — "you don't even notice it happening unless the account's a problem."
   She was **not** aware, at the time of this call, that rush orders behave
   differently on credit check (see the separate email thread with Dale and
   Priya, which came up the following week).
8. Once the line looks right, rep clicks **Book Order**. That's the step she
   considers "the order is placed" — after that it's picking and shipping,
   which is a different team (warehouse in Fargo) that she doesn't cover.

## Things she flagged without being asked
- "New reps get maybe two days of shadowing and then they're on the phones.
  There isn't really a written manual anymore, the old SOP is from 2021 and
  a lot of it doesn't match what we actually do." (She did not specify
  which parts don't match.)
- She was fairly sure there's a customer-level hold that can get set for
  brand-new accounts but couldn't describe when or how it gets released, or
  who owns that decision. "Might be a Finance thing."

## Open items from this call
- How duplicate/near-duplicate customer records are prevented or flagged at
  order entry — unconfirmed.
- How the correct ship-to site is chosen for a multi-site customer —
  unconfirmed.
- Who actually owns/maintains the price list and how often it's updated —
  not asked, not offered.

---

## FILE: FW_ credit check on RUSH orders (thread).txt

_An email thread between Sales Ops, Credit and Inside Sales._

```
From: Dale Kowalski <dale.kowalski@corvalismed.com>
To: Priya Chandrasekaran <priya.chandrasekaran@corvalismed.com>
Cc: Renata Diaz <renata.diaz@corvalismed.com>
Sent: Thursday, May 07, 2026 4:41 PM
Subject: RE: RE: RE: credit check on RUSH orders

Priya,

I need to push back on this one more time. You're telling me ZZ-RUSH orders skip
the credit check completely. That is backwards. A rush order is when a hospital
calls in a panic and needs product tomorrow -- that is EXACTLY the situation
where I'd want AR to be looking harder at the account, not skipping the review
entirely. If we ship $40K of wound-care product on a rush basis to an account
that's already 90 days past due, that's on Finance, not on my reps.

Can you please confirm in writing (a) whether this is actually how it's
configured today in Production, and (b) who approved that design. I don't
remember this coming through Sales Ops for sign-off.

Dale Kowalski
Sales Ops Manager, Corvalis Medical Devices


-----Original Message-----
From: Priya Chandrasekaran
Sent: Thursday, May 07, 2026 2:15 PM
To: Dale Kowalski
Cc: Renata Diaz
Subject: RE: RE: credit check on RUSH orders

Dale,

I checked with Yuki in IT and this is confirmed -- the Credit Check Rule is
tied to Order Type, not to the customer. ZZ-STD (Domestic Standard) runs the
credit check on Book. ZZ-RUSH does not have a credit check rule assigned at
all, so nothing stops it. Yuki says this has been the case since at least the
12.1.3 upgrade project, so it's not something that "changed last year" like
I said on the phone -- I was wrong about that part, sorry. How long it's
actually been this way, nobody over here seems to know for sure.

To be clear, our team's understanding is that the aggregate open-balance
threshold that actually blocks an order is $10,000, and above that it goes to
CREDIT HOLD and needs a release. That's what's in the old SOP anyway. Whether
that's still the live number in the credit check rule setup, I'd have to have
Yuki pull it, I don't check that config myself day to day -- I just work the
hold queue.

Priya


-----Original Message-----
From: Dale Kowalski
Sent: Wednesday, May 06, 2026 11:02 AM
To: Priya Chandrasekaran
Cc: Renata Diaz
Subject: RE: credit check on RUSH orders

Renata's team flagged this to me after a rush order went out Friday to
Briarwood Regional -- an account that (per Renata) has had payment issues
before. Nobody on my side even knew rush orders didn't get checked. Priya can
you look into this and get back to me?

-----Original Message-----
From: Renata Diaz
Sent: Tuesday, May 05, 2026 9:20 AM
To: Dale Kowalski
Subject: rush order credit thing

Hey Dale -- one of my reps, Marcus, booked a rush order for Briarwood Regional
Friday afternoon and it just sailed right through, no hold, nothing. I thought
we were "100% list price, credit checked, no holds on the happy path" per your
own training deck, so this caught me off guard. Can you find out from Priya's
team whether that's expected for rush orders specifically? Marcus swears he
didn't do anything different than usual.

-Renata
```

---

## FILE: order_entry_exceptions_log_Q2.csv

_Every order-entry exception logged in Q2 (to 10 June)._

```
OrderDate,OrderNum,Channel,IssueType,Description,LoggedBy,Resolution,RootCause
2026-04-02,ORD-118842,Phone,ATP false negative,"WD-2200 line showed no availability, rep re-ran autoschedule twice and it cleared",Marcus W.,Order booked after retry,
2026-04-06,ORD-118901,Phone,Price override,"Rep keyed manual unit price below list on SI-8800 line ""per verbal approval""",Angela T.,Order booked,
2026-04-09,ORD-119005,Email,Wrong ship-to,Order shipped to Briarwood Regional dock B instead of dock C,Warehouse (Fargo),Reshipped next day,
2026-04-14,ORD-119182,Phone,Credit hold not released same day,Order sat in CREDIT HOLD 2 business days before AR released it,Renata D.,Released by Priya C.,
2026-04-15,ORD-119190,Portal,Duplicate customer record,Two customer numbers exist for St. Adelaide Clinic; order booked against the older inactive one,Helen P.,Reassigned to active customer #,
2026-04-21,ORD-119344,Phone,ATP false negative,"SI-8800 line showed red, item was confirmed in stock by Fargo warehouse lead same day",Marcus W.,Manually confirmed by supervisor override,
2026-04-24,ORD-119401,Phone,Price override,"Rep says ""told to match a competitor price"" on WD-2200 line, no approval on file",Angela T.,Order booked,
2026-05-01,ORD-119560,Phone,Rush order no credit check,Rush order booked for Briarwood Regional with open past-due balance; no hold triggered,Marcus W.,Escalated to Sales Ops (Dale K.) - see email thread,
2026-05-01,ORD-119602,Email,Wrong ship-to,Same Briarwood dock mix-up as 04-09,Helen P.,Reshipped,
2026-05-05,ORD-119680,Phone,DFF misuse,attribute10 blank on what should have been a sample order; order billed in error,Helen P.,Credit memo issued (separate process),
2026-05-08,ORD-119755,Portal,ATP false negative,"WD-2200 red on screen, cleared itself by next morning with no rep action",Angela T.,Booked next day,
2026-05-08,ORD-119820,Phone,Credit hold not released same day,"Order held over a weekend, no one available to release until Monday",Renata D.,Released by Priya C. Monday AM,
2026-05-14,ORD-119901,Phone,Price override,"Manual discount on SI-8800 ""per Sales Director""",Marcus W.,Order booked,
2026-05-19,ORD-120004,Email,Duplicate customer record,Briarwood Regional has 3 near-duplicate customer names in the system,Helen P.,Not resolved - flagged to IT,
2026-05-27,ORD-120188,Phone,Rush order no credit check,Second instance this quarter - different account this time,Renata D.,Escalated to Sales Ops,
2026-06-02,ORD-120340,Phone,ATP false negative,SI-8800 line,Marcus W.,Cleared after retry,
2026-06-10,ORD-120501,Portal,New customer hold - unclear release path,First order for a brand new customer sat in hold with nobody sure who releases NEW CUSTOMER HOLD,Angela T.,Eventually released by Priya C. after being asked twice,
```

---

## FILE: quick notes - Marcus (order desk) - stuff nobody writes down.md

_A rep's private notes._

stuff i keep meaning to tell renata but never do

- when ATP shows red on WD-2200 i almost never believe it. like 80% of the
  time i know fargo has the stock bc i literally shipped it last week to
  someone else. i just hit autoschedule again or back out the line and
  re-add it and it usually flips green the 2nd time. no idea why. told yuki
  once, she said something about a "nightly batch job" reconciling ATP and
  that maybe the screen is stale during the day sometimes?? never got a real
  answer

- attribute10 on the line -- some of us use it to flag "sample, no charge"
  orders, some of us just leave it blank and write SAMPLE in the notes
  field instead. nobody ever trained me on this it's just what the guy who
  sat next to me before (Trevor, he's gone now) told me to do. renata does
  NOT know this field is being used for that btw

- ship-to for briarwood regional -- they have like 3 loading docks and the
  default ship-to on the account is wrong for 2 of them. i just manually
  change it every time i get a briarwood order, i know which one is which
  from memory. if i'm out sick and someone else takes a briarwood call it
  WILL go to the wrong dock, has happened at least twice this year

- ok this one i probably shouldn't put in writing but -- st. adelaide
  clinic is basically a friend of the sales director's, and maybe 3-4 times
  a year i get a call (not an email, always a call) telling me to knock a
  price down on their order before i book it. i just override the unit
  price on the line manually. i don't love doing it without anything in
  writing but it's always come from someone above renata so i just do it.
  renata thinks we're 100% list price, i've never corrected her on that

- credit hold -- when it does pop up (rare on my orders, mine are mostly
  regulars) i genuinely don't know what actually releases it. one time i
  just called priya's extension and she looked at something and said it
  was fine, few minutes later i could book. no idea what she actually
  checked

- rush orders -- these never seem to hold up on credit even when i'm
  pretty sure the account is behind on payment (briarwood again, actually).
  always figured that was normal since they're urgent. dale's apparently
  mad about this now per that whole email thing

- half the time when i search for a customer by name two or three come up
  that all sound almost the same (like "briarwood regional med ctr" vs
  "briarwood regional medical center" vs "briarwood reg med center - old").
  i just pick whichever one has an order history that looks familiar. no
  clue if that's the "right" way to do it

---

## FILE: ticket_dump_EBS_OM_config.txt

_IT service desk tickets for Order Management, with the analyst's notes._

```
EXPORT: Corvalis Medical Devices - IT Service Desk ticket queue
FILTER: Module = Order Management, last 120 days
EXPORTED BY: Yuki Tanaka, ERP Support Analyst
NOTES ON EACH TICKET: written by Yuki Tanaka
EXPORT DATE: 2026-06-15
NOTE FROM YUKI: pulled this together for the discovery folks, not a formal
report, just filtered our ticket tool and cleaned up the noise a bit. we
don't keep a separate customization register for OM as far as I know - if
one exists I've never seen it and I've been doing this role 3 years. this
plus what's in people's heads is basically the whole picture.

--------------------------------------------------------------------------
TICKET #4471 (closed) - "ATP showing wrong on WD-2200 orders"
Reported by: order entry team (multiple reps over time, this ticket is the
one I use to bucket all the ATP complaints since they're basically the same
issue)
Notes: Item WD-2200 (and a few others in that same item category) runs
through a nightly custom concurrent program, XXCVL_ATP_REVAL, that
re-validates ATP overnight against the Fargo warehouse cycle-count
adjustments. During the business day, the standard ATP engine is what the
order screen calls live, but if a cycle count adjustment posted that
morning hasn't made it through XXCVL_ATP_REVAL yet, the live check can show
a false negative until the next overnight run. This has been reported on
and off for over a year. No permanent fix scheduled - "known behavior,"
per the ticket closure note from a prior analyst (not me).

--------------------------------------------------------------------------
TICKET #4502 (closed) - "attribute10 on order line - what is it for"
Reported by: Helen Park, Order Mgmt Supervisor
Notes: attribute10 (Descriptive Flexfield, Sales Order Line) has no
system-enforced value set - it's a free-text field. Per whoever set this
up originally (before my time, I don't have a name on this), it appears to
have been intended to flag "no-charge sample" lines so they route to a
different revenue account. There's no validation, no required-field rule,
and as far as I can tell most reps either don't use it at all or use the
line Notes field instead. I flagged to Helen that this should probably be
a value set with an approval step if it affects revenue recognition, but
that's a process/policy call, not mine to make.

--------------------------------------------------------------------------
TICKET #4519 (closed) - "credit check rule - does RUSH order type check
credit"
Reported by: Priya Chandrasekaran, Credit Analyst
Notes: Confirmed in Oracle Order Management Order Type setup
(OEXOTCTY form): order type ZZ-STD (Domestic Standard) has Credit Check
Rule = CREDIT-DOM-2024 attached, which runs at Book. Order type ZZ-RUSH
(Rush) has no Credit Check Rule assigned - field is blank. This is
standard EBS config, not a customization, so there's no code to point to,
just a setup value. I don't have change-history/audit trail turned on for
this form so I can't tell you exactly when or by whom the ZZ-RUSH row was
set up this way, or whether it was ever meant to be temporary. It's been
this way at least since I started 3 years ago.

--------------------------------------------------------------------------
TICKET #4530 (closed) - "duplicate customer records - Briarwood"
Reported by: Helen Park
Notes: Confirmed 3 customer number records in the system with very similar
names, all mapped to what looks like the same physical hospital
(Briarwood Regional Medical Center). No dedupe/fuzzy-match rule is
configured on customer search in the Sales Order Workbench - it's a
straight text search against customer name/number, so all 3 will surface
and a rep has to pick. This is a data quality issue in the customer
master, not something OM itself can fix. Suggested a data cleanup project
to Helen; not actioned as of this export.

--------------------------------------------------------------------------
TICKET #4544 (open) - "NEW CUSTOMER HOLD - who releases this"
Reported by: order entry team (routed through Helen Park)
Notes: NEW CUSTOMER HOLD is a standard Order Management hold, applied
automatically to the first order for any customer number less than 90
days old in the system. Release responsibility in the hold-source setup
(OEXHOLDS) points to "Credit Manager" role, which nobody currently holds
as an assigned responsibility in our instance - Priya's team has been
releasing these informally because they're the closest thing we have to
a credit function, but they are not actually assigned the Credit Manager
role that the hold definition references. Left open pending a decision on
whether to reassign the hold-source responsibility or formally give
someone the Credit Manager role.

--------------------------------------------------------------------------
Other custom objects touching Order Management I'm aware of (not
exhaustive, just what I could think of when asked):
- XXCVL_ATP_REVAL - nightly concurrent program, see ticket 4471 above
- XXCVL_ORDACK_EXTRACT - nightly extract table feeding a report Finance
  uses for something, I've never fully understood what report consumes it
- No custom forms, no custom OA Framework pages that I know of touching
  this L4. Order entry itself runs on the standard Sales Order Workbench /
  Order Organizer forms, unmodified as far as I can tell.

Customization level overall for this area I'd call "light" - a couple of
concurrent programs bolted on, everything else is standard config
(order types, price lists, holds, credit check rules). The mess, if there
is one, is more in the setup values and the customer master data than in
custom code.
```
