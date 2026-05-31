# Deal Won — Update QuickBooks Estimate & Sync to Airtable

**Client:** Direct Scaffold Supplies — Brisbane, Australia
**Stack:** Make.com · Pipedrive · QuickBooks Online · Airtable

---

## Overview

When a deal is marked as Won in Pipedrive, this automation finds the matching QuickBooks estimate, updates it with the latest deal line items across multiple QBO company accounts, and syncs the result to Airtable — all automatically. It handles multi-company routing, product-level line item mapping, and both create and update paths in a single workflow.

---

## Problem

Direct Scaffold Supplies operates across multiple QuickBooks company accounts. When a deal was won in Pipedrive, the finance team had to manually locate the corresponding QBO estimate, update it with any last-minute product changes, and record it in Airtable. With multiple companies and complex product lists, this was slow and error-prone.

---

## Solution

A Make.com automation triggered by Pipedrive's deal-won webhook:

1. **Trigger** — Pipedrive webhook fires on deal-won event
2. **Fetch deal** — retrieves full deal data from Pipedrive
3. **Multi-company router** — routes to the correct QuickBooks company account based on deal metadata (3 company branches handled)
4. **For each company branch:**
   - Searches QuickBooks for an existing estimate linked to the deal
   - Fetches the full estimate details
   - Retrieves all products from the Pipedrive deal
   - For each product, fetches product details and searches QuickBooks Items for the matching SKU
   - Aggregates line items into the correct QBO format
   - Updates the QuickBooks estimate with current products, quantities, and pricing
   - Searches Airtable for an existing record (create or update path)
   - Creates or updates the Airtable record with deal + estimate data
5. **Organisation sync** — fetches and updates organisation details for reference

---

## Key Features

- **Multi-company routing** — 3 QuickBooks company accounts handled via router logic
- **Product-level line item mapping** — each Pipedrive product resolved to a QBO item by SKU
- **Aggregator pattern** — line items batched correctly before estimate update
- **Create or update logic** — Airtable records created fresh or updated if they already exist
- **Full audit trail** — Airtable reflects the final won deal state across all companies

---

## Flow Diagram

```
Pipedrive Deal Won (webhook)
  → Get Deal Details
  → Router: Which QBO Company?
      → [Company A / B / C]
          → Search QBO for Estimate
          → Get Estimate Details
          → List Deal Products
              → For each product: Get Product Details → Search QBO Items
          → Aggregate Line Items
          → Update QBO Estimate
          → Get Organisation Details
          → Search Airtable (record exists?)
              → [Exists] Update Airtable Record
              → [New] Create Airtable Record
```

---

## Impact

| Before | After |
|---|---|
| Manual QBO estimate updates post-deal-win | Instant automated estimate update |
| Finance team navigating 3 QBO accounts manually | Automatic routing to correct account |
| Airtable updated manually or not at all | Auto-synced with every won deal |
| Product mismatches between CRM and accounting | SKU-level matching ensures accuracy |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration + multi-company routing |
| Pipedrive API | Deal-won trigger + deal/product/org data source |
| QuickBooks Online API | Estimate search, retrieval, and update (3 companies) |
| Airtable API | Deal record create/update for reporting |
