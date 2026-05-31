# AI Building Inspection Analyzer

**Stack:** Make.com · Podio · OpenAI · Google Docs · OneDrive

---

## Overview

An end-to-end automation that replaces manual property inspection documentation with an AI-powered workflow triggered directly from within Podio. A single button click initiates the entire pipeline — from data extraction through AI analysis to final document delivery and CRM sync.

---

## Problem

Construction and inspection teams were spending hours manually writing up inspection reports — copying data out of Podio, formatting Google Docs, attaching files from OneDrive, and syncing everything back. The process was slow, inconsistent, and prone to human error.

---

## Solution

A Make.com automation that:

1. Watches for a Podio button trigger on an inspection record
2. Extracts all relevant property and inspection data from Podio
3. Sends the data to OpenAI for structured AI-powered analysis
4. Creates a new Google Doc from a pre-formatted template
5. Inserts the AI analysis into the correct template placeholders
6. Syncs the completed document back to Podio as a linked file
7. Scans the relevant OneDrive subfolder, attaches files with share links and metadata
8. Cleans up any temporary documents created during processing

---

## Key Features

- **One-click trigger** from Podio — zero manual steps for the end user
- **AI analysis** via OpenAI GPT-4 with structured prompt engineering
- **Template-based document generation** using Google Docs API
- **OneDrive integration** with automatic file discovery and metadata sync
- **Automatic cleanup** of temporary files to prevent storage bloat
- **Idempotent design** — safe to re-run without creating duplicates

---

## Impact

| Before | After |
|---|---|
| 2–3 hours per report | Under 5 minutes |
| Inconsistent formatting | Standardized template output |
| Manual file attachment | Automatic OneDrive sync |
| Separate CRM update required | Auto-synced back to Podio |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration |
| Podio API | Trigger + data source + CRM sync |
| OpenAI API (GPT-4) | AI-powered property analysis |
| Google Docs API | Template-based document generation |
| OneDrive API | File discovery and attachment |
