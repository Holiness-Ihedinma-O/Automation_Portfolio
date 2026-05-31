# M365 Inbox Scanner & AI Parser

**Stack:** Make.com · Microsoft 365 · OpenAI · Airtable

---

## Overview

Built for a multilingual real estate agency managing bookings from English, Spanish, and German-speaking clients. This automation scans the M365 inbox continuously, uses OpenAI to extract structured data from unstructured emails, deduplicates records, and generates language-matched reply drafts — all without human intervention.

---

## Problem

The agency's team was manually reading every incoming booking email, extracting client and property details, logging them in their CRM, and composing replies — all in three different languages. Errors were frequent, responses were slow, and manual data entry consumed hours of staff time daily.

---

## Solution

A modular Make.com automation suite that:

1. Continuously scans the M365 inbox for new booking-related emails
2. Sends email content to OpenAI for structured data extraction (name, property, dates, language, intent)
3. Detects the email language (EN/ES/DE) automatically
4. Checks the CRM (Airtable) for existing records and applies deduplication logic
5. Creates or updates Lead, Company, and People records as appropriate
6. Generates a language-matched reply draft using OpenAI
7. Produces a daily activity summary report for the operations team

---

## Key Features

- **Multilingual parsing** — handles English, Spanish, and German with language-specific OpenAI prompts
- **Structured data extraction** — converts unstructured email prose into clean JSON records
- **Three-layer deduplication** — checks Leads, Companies, and People separately before writing
- **Language-matched reply generation** — draft replies match the client's original language
- **Daily summary reports** — operations team receives an end-of-day digest automatically
- **Modular scenario design** — each function (scanning, parsing, deduplication, reply) is a separate Make.com scenario for easy maintenance

---

## Impact

| Before | After |
|---|---|
| Manual email triage and logging | Fully automated extraction and CRM entry |
| Replies drafted manually in 3 languages | AI-generated drafts in the correct language |
| Duplicate records common | 3-layer deduplication prevents duplicates |
| No daily overview | Automated end-of-day summary |
| Hours of manual work per day | 90%+ reduction in manual handling |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration (modular scenarios) |
| Microsoft 365 Mail API | Inbox scanning and email retrieval |
| OpenAI API (GPT-4o) | Data extraction, language detection, reply generation |
| Airtable | CRM — Leads, Companies, People records |
