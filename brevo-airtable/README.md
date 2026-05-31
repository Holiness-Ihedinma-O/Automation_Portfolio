# Brevo ↔ Airtable Sync

**Stack:** Make.com · Brevo · Airtable

---

## Overview

A bidirectional sync automation that keeps contact data, list membership, and engagement status consistent between Brevo (email marketing) and Airtable (CRM) in real time — eliminating manual exports, imports, and data drift between the two platforms.

---

## Problem

The client was managing their CRM in Airtable and their email marketing in Brevo, but the two platforms were out of sync. New Airtable contacts weren't making it to Brevo automatically, Brevo engagement data wasn't reflected in the CRM, and manual CSV exports were causing delays and version conflicts.

---

## Solution

A Make.com automation with two directional flows:

**Airtable → Brevo (CRM to Marketing)**
1. Watches Airtable for new or updated contact records
2. Checks if the contact already exists in Brevo
3. Creates or updates the Brevo contact with current data
4. Assigns the correct list(s) and tag(s) based on Airtable fields

**Brevo → Airtable (Marketing to CRM)**
1. Watches for Brevo webhook events (unsubscribes, bounces, clicks, opens)
2. Locates the matching record in Airtable
3. Updates the CRM record with engagement status, unsubscribe flags, or bounce data

---

## Key Features

- **Bidirectional** — changes in either platform propagate to the other
- **Deduplication logic** — checks for existing records before writing to prevent duplicates
- **List and tag sync** — Airtable categories map to Brevo lists automatically
- **Engagement feedback loop** — Brevo events update CRM records in real time
- **Error handling** — failed records are logged for review without stopping the automation

---

## Impact

| Before | After |
|---|---|
| Manual CSV exports between platforms | Real-time automated sync |
| CRM and email lists always out of sync | Both platforms always up to date |
| No visibility on email engagement in CRM | Brevo events reflected in Airtable |
| Risk of emailing unsubscribed contacts | Unsubscribes auto-flagged in CRM |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration (two scenarios) |
| Airtable API | CRM data source and target |
| Brevo API + Webhooks | Email marketing platform and event source |
