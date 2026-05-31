# Automation Portfolio — Holiness Ihedinma Onyemaechi

**Automation Specialist | Salesforce Certified Platform Administrator | AI Workflow Architect**

📧 holinessonyemaechi@gmail.com · 🔗 [linkedin.com/in/holiness-onyemaechi](https://linkedin.com/in/holiness-onyemaechi) · 🌍 Nigeria (Open to remote & relocation)

---

## About

I design, build, and optimize no-code/low-code automation systems for agencies, SaaS teams, coaches, and global businesses. My work spans CRM development, AI-powered data extraction, cloud integrations, lead enrichment, and workflow orchestration — primarily using Make.com, n8n, Airtable, Zapier, and the OpenAI/Claude APIs.

This portfolio contains real production projects across real client environments. All sensitive data has been removed or anonymized.

---

## Projects

| Project | Client | Stack | Key Outcome |
|---|---|---|---|
| [AI Building Inspection Analyzer](#-ai-building-inspection-analyzer) | Construction agency | Make.com · Podio · OpenAI · Google Docs · OneDrive | Manual documentation time cut from hours to minutes |
| [AI Certificate Maker](#-ai-certificate-maker) | AI education institute | Make.com · Google Sheets · Gmail · Drive · HeyGen | End-to-end certificate scheduling & personalized video delivery |
| [M365 Inbox Scanner & AI Parser](#-m365-inbox-scanner--ai-parser) | Real estate agency | Make.com · Microsoft 365 · OpenAI | Multilingual email parsing with 90%+ reduction in manual handling |
| [Brevo ↔ Airtable Sync](#-brevo--airtable-sync) | SaaS/agency | Make.com · Brevo · Airtable | Real-time bidirectional CRM and email marketing sync |
| [CPD Registration Confirmation Automation](#-cpd-registration-confirmation-automation) | Event/training provider | Make.com · Google Sheets · Gmail | Automated event registration confirmation and record-keeping |
| [Pipedrive → QuickBooks Multi-Company Quote Automation](#-pipedrive--quickbooks-multi-company-quote-automation) | Scaffolding company | Make.com · Pipedrive · QuickBooks | Instant quote generation triggered by new CRM deals |
| [Deal Won → Create Basecamp Project](#-deal-won--create-basecamp-project) | Direct Scaffold Supplies, AU | Make.com · Pipedrive · Basecamp · Data Store | Zero-touch project creation on every deal won |
| [Deal Won → Update QuickBooks Estimate](#-deal-won--update-quickbooks-estimate--sync-to-airtable) | Direct Scaffold Supplies, AU | Make.com · Pipedrive · QuickBooks · Airtable | Multi-company QBO estimate update with Airtable sync |
| [Pipedrive Forecast → Basecamp & Airtable](#-pipedrive-forecast--basecamp-calendar--airtable-sync) | Direct Scaffold Supplies, AU | Make.com · Pipedrive · Basecamp · Airtable | Per-product calendar events with full deduplication |
| [New Deal → QuickBooks Estimate V2](#-pipedrive-new-deal--quickbooks-estimate-v2) | Direct Scaffold Supplies, AU | Make.com · Pipedrive · QuickBooks · Airtable | Instant estimate creation across 3 QBO companies |

---

## Project Details

### 🏗 AI Building Inspection Analyzer
`Make.com` `Podio` `OpenAI` `Google Docs` `OneDrive`

An end-to-end automation that triggers AI-powered property analysis directly from a Podio button click. Generates structured Google Docs reports from templates, injects AI analysis, syncs the result back to Podio, and pulls in relevant OneDrive files with metadata and share links.

**Key highlights:**
- Triggered from Podio with zero manual steps
- AI analysis auto-inserted into pre-formatted Google Docs templates
- Automatic cleanup of temporary files to optimize storage
- OneDrive subfolder files synced into Podio with share links

📁 [View project folder](./ai-building-inspection-analyzer)

---

### 🎓 AI Certificate Maker
`Make.com` `Google Sheets` `Gmail` `Google Drive` `HeyGen`

Designed for an AI education institute, this system automates the full certificate lifecycle — from course completion trigger through personalized certificate generation, storage, and delivery via a custom AI video message using HeyGen.

**Key highlights:**
- Watches a Google Sheet for new completions
- Generates and stores certificates in Google Drive automatically
- Sends personalized emails with certificates attached
- Creates individual HeyGen AI video messages per recipient

📁 [View project folder](./ai-certificate-maker)

---

### 📧 M365 Inbox Scanner & AI Parser
`Make.com` `Microsoft 365` `OpenAI`

Built for a real estate agency handling multilingual bookings across English, Spanish, and German markets. The system scans incoming emails, uses OpenAI to extract structured data, detects language, deduplicates records, and generates language-matched reply drafts — all without human intervention.

**Key highlights:**
- Multilingual parsing (EN/ES/DE) via OpenAI
- Robust deduplication across Leads, Companies, and People
- Language-specific reply draft generation
- Daily activity summary reports
- 90%+ reduction in manual client registration handling

📁 [View project folder](./m365-inbox-scanner-ai-parser)

---

### 🔄 Brevo ↔ Airtable Sync
`Make.com` `Brevo` `Airtable`

A bidirectional sync between Brevo (email marketing) and Airtable (CRM) ensuring contact data, campaign engagement, and list membership stay consistent across both platforms in real time.

**Key highlights:**
- New Airtable records auto-created or updated in Brevo
- Brevo contact updates reflected back into Airtable
- Tag and list membership synced bidirectionally
- Error handling for duplicate and missing records

📁 [View project folder](./brevo-airtable)

---

### ✅ CPD Registration Confirmation Automation
`Make.com` `Google Sheets` `Gmail`

Automates the full registration confirmation flow for a Continuing Professional Development (CPD) event platform. New registrations trigger instant confirmation emails, Google Sheet record creation, and organizer notifications — no manual processing required.

**Key highlights:**
- Instant confirmation emails to registrants
- Auto-populated event attendance Google Sheet
- Organizer summary notifications
- Clean error handling for duplicate submissions

📁 [View project folder](./cpd-registration-confirmation-automation)

---

### 💼 Pipedrive → QuickBooks Multi-Company Quote Automation
`Make.com` `Pipedrive` `QuickBooks`

When a new deal is added in Pipedrive, this automation instantly creates a matching quote in the correct QuickBooks company account — handling multi-company routing logic, product line mapping, and error fallbacks automatically.

**Key highlights:**
- Triggered by new deal creation in Pipedrive
- Routes to the correct QuickBooks company based on deal metadata
- Maps CRM line items to QuickBooks products
- Idempotent design prevents duplicate quotes on reruns

📁 [View project folder](./Pipedrive%20→%20QuickBooks%20Multi-Company%20Quote%20Automation.readme)

---

### 🏗 Deal Won → Create Basecamp Project
`Make.com` `Pipedrive` `Basecamp` `Make Data Store`

**Client: Direct Scaffold Supplies, Brisbane, Australia**

When a deal is marked as Won in Pipedrive, this automation instantly spins up a new Basecamp project — fetching deal and organisation details, checking for duplicates via the Make Data Store, creating the project via the Basecamp API, and writing the project link back to the Pipedrive deal. Zero manual steps at the most critical moment in the sales-to-delivery handoff.

**Key highlights:**
- Idempotent — Data Store prevents duplicate projects if the automation reruns
- Basecamp project ID synced back to Pipedrive deal for full traceability
- Sleep + retry logic handles Basecamp API provisioning delay gracefully

📁 [View project folder](./direct-scaffold-deal-won-bc-project)

---

### 💰 Deal Won → Update QuickBooks Estimate & Sync to Airtable
`Make.com` `Pipedrive` `QuickBooks Online` `Airtable`

**Client: Direct Scaffold Supplies, Brisbane, Australia**

On deal-won, this automation finds the matching QuickBooks estimate across 3 company accounts, updates it with the latest Pipedrive line items at the SKU level, and syncs the result to Airtable. Handles multi-company routing, per-product aggregation, and both create and update paths in a single workflow.

**Key highlights:**
- 3 QuickBooks company accounts routed automatically based on deal metadata
- Product-level line item mapping — each Pipedrive product resolved to a QBO item by SKU
- Airtable create-or-update logic for clean, deduplicated records

📁 [View project folder](./direct-scaffold-deal-won-qbo-estimate)

---

### 📅 Pipedrive Forecast → Basecamp Calendar & Airtable Sync
`Make.com` `Pipedrive` `Basecamp` `Airtable` `Make Data Store`

**Client: Direct Scaffold Supplies, Brisbane, Australia**

Keeps the Basecamp operations calendar in sync with Pipedrive deals. For each product (scaffold hire line item) on a deal, a dedicated Basecamp calendar event is created. Deduplication via Make Data Store ensures events are created once, updated on reschedule, and never duplicated — even across reruns.

**Key highlights:**
- Per-product calendar events — each hire line item gets its own Basecamp event
- Up to 6 product branches per deal handled simultaneously
- Idempotent by deal + product combination, preventing any duplicate calendar entries

📁 [View project folder](./direct-scaffold-forecast-basecamp-airtable)

---

### 📋 Pipedrive New Deal → QuickBooks Estimate V2
`Make.com` `Pipedrive` `QuickBooks Online` `Airtable`

**Client: Direct Scaffold Supplies, Brisbane, Australia**

When a new deal lands in Pipedrive, this automation creates a matching QuickBooks estimate in the correct company account — looking up or creating the customer, building the estimate, syncing IDs back to Pipedrive, and logging everything in Airtable. V2 migrated from raw HTTP calls to Make's native QBO modules for improved reliability and maintainability.

**Key highlights:**
- 3 QBO company accounts — automatic routing, zero manual selection
- Customer search-first logic prevents duplicate QBO customers
- QBO estimate ID and customer ID written back to both the Pipedrive deal and organisation records
- V2 upgrade: native Make QBO modules replace fragile HTTP requests

📁 [View project folder](./direct-scaffold-new-deal-qbo-quote-v2)

---

## Tech Stack

**Automation Platforms:** Make.com · n8n · Zapier · Google Apps Script · Airtable Automations

**CRM & Data:** Salesforce · Airtable · Podio · Pipedrive · Apollo · Brevo · HubSpot

**AI & APIs:** OpenAI (GPT-4o) · Claude API · HeyGen · Webhooks · REST APIs · JSON · Regex

**Cloud & Productivity:** Microsoft 365 · Google Workspace · QuickBooks · OneDrive · Basecamp

---

## Certifications

- Salesforce Certified Agentforce Specialist
- Salesforce Certified Platform Administrator
- Salesforce Certified Platform Foundations
- Certified Airtable Builder
- Make Advanced · Make Intermediate · Make Basics & Foundations
- ISC2 CC (Certified in Cybersecurity)

---

## Let's Connect

I'm open to freelance, contract, and full-time remote opportunities globally.

📧 holinessonyemaechi@gmail.com
🔗 [linkedin.com/in/holiness-onyemaechi](https://linkedin.com/in/holiness-onyemaechi)
