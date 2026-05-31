# Deal Won — Create New Basecamp Project

**Client:** Direct Scaffold Supplies — Brisbane, Australia
**Stack:** Make.com · Pipedrive · Basecamp · Make Data Store

---

## Overview

When a deal is marked as Won in Pipedrive, this automation instantly spins up a new Basecamp project for that client — pulling deal and organisation details from Pipedrive, checking for duplicates, creating the project via the Basecamp API, and writing the result back to Pipedrive. No manual project setup required.

---

## Problem

Every time a deal was won, the operations team had to manually create a Basecamp project, name it correctly, and link it back to the Pipedrive deal. This was a repeated, error-prone task that added friction at the most critical moment in the sales-to-delivery handoff.

---

## Solution

A Make.com automation triggered by Pipedrive's webhook on deal-won events:

1. **Trigger** — Pipedrive webhook fires when a deal stage changes to Won
2. **Fetch deal details** — retrieves full deal data including title, value, and owner
3. **Fetch organisation details** — pulls the linked company name and contact info
4. **Duplicate check** — queries the Make Data Store to confirm this deal hasn't already created a project (idempotency)
5. **Create Basecamp project** — fires an HTTP request to the Basecamp API to create a named project
6. **Sleep buffer** — short delay to allow Basecamp to provision the project before the next step
7. **Fetch project ID** — retrieves the newly created project's ID from Basecamp
8. **Log to Data Store** — records the deal ID + Basecamp project ID to prevent future duplicates
9. **Update Pipedrive deal** — writes the Basecamp project link back into the Pipedrive deal for full traceability

---

## Key Features

- **Idempotent** — Data Store check prevents duplicate Basecamp projects if the automation reruns
- **Fully bidirectional** — Basecamp project ID synced back to Pipedrive deal record
- **Sleep + retry logic** — handles Basecamp API provisioning delay gracefully
- **Zero manual steps** — entire handoff from sales win to project creation is automated

---

## Flow Diagram

```
Pipedrive Deal Won (webhook)
  → Get Deal Details
  → Get Organisation Details
  → Check Data Store (duplicate?)
      → [New] Create Basecamp Project (HTTP)
          → Sleep (provisioning delay)
          → Fetch Project ID
          → Log to Data Store
          → Update Pipedrive Deal with BC Project Link
      → [Exists] Skip
```

---

## Impact

| Before | After |
|---|---|
| Manual Basecamp project creation per won deal | Instant automated project creation |
| Risk of missed or duplicate projects | Idempotent — guaranteed once-only creation |
| No link between CRM and project tool | Basecamp project ID synced back to Pipedrive |
| Operations delay after deal close | Zero delay — project ready before team is notified |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration |
| Pipedrive API (webhook) | Deal-won trigger + deal/org data source + update target |
| Basecamp API (HTTP) | Project creation |
| Make Data Store | Idempotency tracking (duplicate prevention) |
