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
