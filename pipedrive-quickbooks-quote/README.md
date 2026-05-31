# Pipedrive → QuickBooks Multi-Company Quote Automation

**Stack:** Make.com · Pipedrive · QuickBooks Online

---

## Overview

When a new deal is added in Pipedrive, this automation instantly creates a matching quote in the correct QuickBooks company account — handling multi-company routing logic, CRM-to-accounting product mapping, and error fallbacks automatically. No manual data re-entry required between sales and finance.

---

## Problem

The client operated multiple business entities, each with its own QuickBooks account. When a new deal was created in Pipedrive, someone had to manually log into the correct QuickBooks company, recreate the deal as a quote, and map the products. This caused delays in quote delivery, occasional routing errors, and duplicated data entry work.

---

## Solution

A Make.com automation that:

1. Watches Pipedrive for new deal creation events
2. Reads deal metadata (products, value, company field) to determine which QuickBooks account to target
3. Routes to the correct QuickBooks company using conditional logic
4. Maps Pipedrive deal line items to the corresponding QuickBooks products/services
5. Creates the quote in QuickBooks with all deal details pre-filled
6. Updates the Pipedrive deal with the QuickBooks quote ID for traceability
7. Handles errors gracefully — logs failures and notifies the team without blocking the pipeline

---

## Key Features

- **Multi-company routing** — deal metadata determines which QuickBooks instance receives the quote
- **Automatic product mapping** — Pipedrive line items mapped to QuickBooks products/services
- **Idempotent design** — re-running the automation does not create duplicate quotes
- **Traceability** — QuickBooks quote ID written back to the Pipedrive deal record
- **Error handling** — failed routes are logged and flagged without stopping other deals

---

## Impact

| Before | After |
|---|---|
| Manual login to correct QuickBooks company | Automatic routing via deal metadata |
| Manual quote creation (10–20 min per deal) | Quote created in under 30 seconds |
| Risk of wrong-company routing | Logic-enforced correct routing |
| No CRM link to QuickBooks record | Quote ID synced back to Pipedrive |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration + routing logic |
| Pipedrive API | Deal trigger + line item source + quote ID sync |
| QuickBooks Online API | Quote creation (multi-company) |

---

## Screenshot

![Pipedrive → QuickBooks automation flow](./New%20Deal%20Added%20Pipedrive%20-%20Create%20QuickBooks%20Quote.png)
