# Direct Scaffold Supplies — Airtable Operations Base

**Client:** Direct Scaffold Supplies — Brisbane, Australia
**Stack:** Airtable · Make.com · Pipedrive

---

## Overview

A fully custom Airtable base designed and built as the central operations hub for Direct Scaffold Supplies — an Australian scaffolding company managing multiple concurrent installation jobs across job sites in Brisbane and surrounding regions.

The base manages **1,900+ active scaffold forecast records** with live data flowing in automatically from Pipedrive via Make.com. It replaced a fragmented, manual process and gave the entire team — from field operations to the CEO — a single source of truth for all active jobs.

---

## Problem

Direct Scaffold Supplies was managing scaffold installation forecasts manually — deals were won in Pipedrive but the operations team had no structured, live view of what was installed, what was pending invoicing, what was scheduled for today or tomorrow, and what was still outstanding. The CEO had no real-time visibility without asking the team directly.

---

## Solution

A production Airtable base with:
- Live Pipedrive-to-Airtable sync via Make.com — new and updated deals flow in automatically with full product-level detail
- 10+ custom views tailored to different roles and workflows
- Clean data architecture tracking every scaffold hire product per deal

---

## Base Architecture

**Fields tracked per record:**

| Field | Description |
|---|---|
| New Key | Unique record identifier |
| Product Name | Scaffold product (Low Set Edge, GR On Roof, Ally Scaff, etc.) |
| Product Code | Internal SKU (GRLS, GROR, ALP, ASS1, ASS2, etc.) |
| Deal Product ID | Pipedrive deal product reference |
| Comments on Deal | Hire period, dimensions, special instructions |
| Quantity | Number of units |
| Status | Current job status (Invoiced, Not Invoiced, etc.) |

---

## Custom Views Built

| View | Purpose |
|---|---|
| **Forecast-Pipedrive** | Live view of all deals synced from Pipedrive |
| **Monthly Install View** | Month-by-month installation scheduling |
| **Today** | Day-level view — jobs scheduled for today |
| **Tomorrow** | Day-level view — jobs scheduled for tomorrow |
| **This Week** | Weekly operations planning view |
| **Latest Entry View — Geoff** | CEO-facing summary of most recent activity |
| **Status = Invoiced** | Finance view — invoiced jobs only |
| **Not Invoiced** | Outstanding jobs pending invoicing |
| **Tech-View** | Technical operations view |
| **Instance ID Present** | Data quality view — records with full IDs confirmed |
| **N5997 / N5959 / N5887** | Site-specific filtered views per job site |
| **All Manual Entry** | Records entered manually (outside automation) |

---

## Screenshot

![Direct Scaffold Airtable Operations Base](./airtable-operations-base.png)

---

## Automation Integration

The base is the data destination for several Make.com automations:

- **New Deal Added** → Pipedrive webhook triggers Make.com → product-level records created in Airtable automatically
- **Deal Won** → QBO estimate updated and Airtable record synced with won status
- **Forecast Sync** → Basecamp calendar events created per product, logged back to Airtable with event IDs
- **Deduplication** → Make Data Store prevents duplicate records on reruns and reschedules

---

## Impact

| Before | After |
|---|---|
| Manual data entry into spreadsheets | 1,900+ records auto-populated from Pipedrive |
| No real-time operations visibility | Live views for every role — field, finance, CEO |
| CEO needed to ask team for updates | Dedicated CEO view with latest activity |
| No invoicing status tracking | Invoiced vs Not Invoiced views always up to date |
| Fragmented data across tools | Single source of truth for all active jobs |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Airtable | Operations base — data model, views, interfaces |
| Make.com | Automated data sync from Pipedrive |
| Pipedrive API | Deal and product data source |
