# AI Certificate Maker

**Stack:** Make.com · Google Sheets · Gmail · Google Drive · HeyGen

---

## Overview

Built for an AI education institute, this system automates the complete certificate lifecycle — from course completion detection through personalized certificate generation, cloud storage, email delivery, and a custom AI video message per recipient.

---

## Problem

The institute was manually generating certificates, saving them to Drive, emailing them individually, and recording completions in a spreadsheet. As enrollment grew, this became a bottleneck that delayed delivery and created inconsistency.

---

## Solution

A Make.com automation that:

1. Watches a Google Sheet for new course completion entries
2. Generates a personalized certificate using a Drive template
3. Saves the certificate to a designated Google Drive folder
4. Sends a personalized email to the recipient with the certificate attached
5. Triggers a HeyGen AI video message personalized to the recipient's name and course
6. Updates the Google Sheet to mark delivery as complete

---

## Key Features

- **Fully automated** from completion entry to delivery — no manual steps
- **Personalized at scale** — each certificate and video is unique to the recipient
- **HeyGen AI video integration** — recipients receive a personalized video alongside their certificate
- **Google Drive organization** — certificates stored in structured, named folders
- **Delivery tracking** — Google Sheet updated with sent status and timestamp

---

## Impact

| Before | After |
|---|---|
| Manual certificate creation per student | Instant automated generation |
| 10–15 min per recipient | Under 60 seconds end-to-end |
| Generic email delivery | Personalized email + AI video |
| No delivery tracking | Auto-logged in Google Sheet |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration |
| Google Sheets | Completion trigger + delivery tracking |
| Google Drive | Certificate template + storage |
| Gmail | Personalized certificate delivery |
| HeyGen API | AI-generated personalized video messages |<img width="1693" height="1382" alt="Screenshot 2026-06-01 033416" src="https://github.com/user-attachments/assets/cd0958af-6418-4957-aa87-84dcb8b3694b" />
