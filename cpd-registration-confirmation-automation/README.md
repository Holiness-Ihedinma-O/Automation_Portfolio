# CPD Registration Confirmation Automation

**Stack:** Make.com · Google Sheets · Gmail

---

## Overview

Automates the complete registration confirmation flow for a Continuing Professional Development (CPD) event platform. New registrations trigger instant personalized confirmation emails, structured Google Sheet record creation, and organizer notifications — replacing a fully manual process.

---

## Problem

The CPD organizer was manually processing each registration: checking the form submission, sending a confirmation email, adding the attendee to a spreadsheet, and notifying the event team. With multiple events running simultaneously, this was time-consuming and prone to delays and missed entries.

---

## Solution

A Make.com automation that:

1. Watches for new form submissions (via webhook or form tool integration)
2. Validates the submission for required fields and duplicate detection
3. Adds the registrant as a new row in the event's Google Sheet with full details and timestamp
4. Sends a personalized confirmation email to the registrant with event details
5. Sends a notification to the organizer with a summary of the new registration
6. Marks the sheet row as "Confirmed" upon successful email delivery

---

## Key Features

- **Instant confirmation** — registrants receive their email within seconds of submitting
- **Duplicate detection** — checks the Google Sheet before creating a new record
- **Personalized emails** — confirmation includes the registrant's name, event details, and relevant instructions
- **Organizer notifications** — team is alerted to each new registration in real time
- **Delivery status tracking** — Google Sheet updated with confirmation status and timestamp
- **Error handling** — failed deliveries are flagged without losing the registration record

---

## Impact

| Before | After |
|---|---|
| Manual confirmation emails (10–15 min per registration) | Instant automated delivery |
| Spreadsheet updated manually | Auto-populated on registration |
| Organizer notified manually | Real-time team notification |
| Risk of missed or delayed confirmations | Zero missed confirmations |

---

## Tech Stack Details

| Tool | Role |
|---|---|
| Make.com | Workflow orchestration |
| Google Sheets | Attendance record and delivery tracking |
| Gmail | Registrant confirmation + organizer notification |
| Webhook / Form tool | Registration trigger |
