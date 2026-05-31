# Pipedrive Forecast — Basecamp Calendar & Airtable Sync

**Client:** Direct Scaffold Supplies — Brisbane, Australia
**Stack:** Make.com · Pipedrive · Basecamp · Airtable · Make Data Store

---

## Overview

When a new deal event is added or updated in Pipedrive, this automation creates corresponding calendar events in Basecamp and syncs the deal data to Airtable — with full deduplication to ensure events are created once, updated on reschedule, and never duplicated. It handles up to 6 products per deal, creating a dedicated calendar event for each installation line item.

---

## Problem

Direct Scaffold Supplies manages multiple concurrent scaffold installation jobs, each tied to a Pipedrive deal. The operations team needed installation dates from Pipedrive to appear in Basecamp's shared calendar for scheduling and site management — but manually creating calendar events for each product line on each deal was time-consuming and frequently out of sync.

---

## Solution

A Make.com automation triggered by Pipedrive deal events:

1. **Trigger** — Pipedrive webhook fires on new or updated deal events
2. **Sleep buffer** — brief delay to ensure Pipedrive data is fully propagated
3. **Fetch deal details** — retrieves deal title, dates, stage, and owner
4. **Set variables** — constructs event naming and metadata
5. **Fetch organisation** — pulls client company details for event context
6. **List deal products** — retrieves all products (scaffold hire line items) from the deal
7. **For each product (up to 6):**
   - Fetches full product details including hire period and dates
   - Sets product-level variables for event construction
   - **Duplicate check** — queries Make Data Store to see if a Basecamp event already exists for this deal + product combination
   - **Router:**
     - **[New]** Creates a Basecamp calendar event with product name, dates, and deal context → logs the event ID to Data Store → creates Airtable record
     - **[Exists]** Skips creation (idempotent)

---

## Key Features

- **Per-product calendar events** — each scaffold hire line item gets its own Basecamp event
- **Idempotent design** — Data Store prevents duplicate events on reruns or re-triggers
- **Up to 6 product branches** — handles deals with multiple concurrent hire items
- **Airtable sync** — every event creation logged in Airtable for reporting and visibility
- **Sleep/delay logic** — prevents race conditions with Pipedrive's webhook propagation

---

## Flow Diagram

```
Pipedrive Deal Event (webhook)
  → Sleep (propagation buffer)
  → Get Deal Details
  → Set Variables (event naming)
  → Get Organisation Details
  → List Deal Products
      → For each product (×6 branches):
          → Get Product Details
          → Set Product Variables
          → Check Data Store (event exists?)
              → [New]
                  → Create Basecamp Calendar Event
                  → Log to Data Store
                  → Create Airtable Record
              → [Exists] Skip
```

---

## Impact

| Before | After |
|---|---|
| Manual calendar event creation per product per deal | Fully automated on deal update |
| Basecamp calendar always out of sync with Pipedrive | Real-time sync on every deal change |
| Duplicate events on reschedules | Idempotent — once-only creation guaranteed |
| No Airtable visibility on scheduling | Every event creation logged automatically |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration + per-product branching |
| Pipedrive API | Deal/product/org data source (webhook trigger) |
| Basecamp API | Calendar event creation |
| Make Data Store | Idempotency tracking per deal + product |
| Airtable API | Event log and reporting |
