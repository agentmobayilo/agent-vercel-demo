# Google Workspace SaaS Instructions

Paste your full prompt/instructions here.

## Context
- Product idea:
- Target users:
- Must-have features:
- Business model:
- Constraints:

## Full Prompt / Instruction

<!-- Paste everything below this line -->
You work form now

You are going to build a SaaS to take advantage of the Google Workspace CLI ()


Before you start I need you to create docs folder and have (PRD.md, PROJECT_SUMMARY.md, PROJECT_STATUS.md)

Use the same format as mobayilo
(https://github.com/adusingi/mobayilo/blob/main/docs/src/content/docs/project-history/PROJECT_SUMMARY.md)
https://github.com/adusingi/mobayilo/blob/main/docs/src/content/docs/project-history/PROJECT_STATUS.md (Status has alway task, test and exit criteria)
https://github.com/adusingi/mobayilo/blob/main/docs/src/content/docs/project-history/PRD.md


Backend: Ruby 3.4 + Rails 8 (latest stable)
Frontend: Hotwire (Turbo + Stimulus) — no heavy JS framework needed for MVP
Database: PostgreSQL (Heroku/Render/Railway friendly)
Jobs: Sidekiq + Redis
Google: Omniauth + gws CLI via system calls
Billing: Stripe
Deployment: Render, Railway, or Heroku (all have great Rails support)

----
Ideal UI structure

Dashboard

Today
. Inbox Actions
. Leads Detected
. Pending Follow-ups
. Meetings

Inbox AI
. Urgent emails
. Reply drafts
. Lead detection


CRM Sheet Sync
. Deals detected
. Follow-up reminders

Daily Brief
. Important emails
. Meetings today
. Documents to review

----

1️⃣ Fast SaaS development

Rails gives you out of the box:

authentication

database ORM

background jobs

admin panels

API endpoints

migrations

validations


2️⃣ Background jobs (critical for your product)

Your system will need:

Gmail scanning

lead detection

follow-up scheduling

daily briefing generation

LLM processing

Rails has excellent job systems:

Sidekiq
Resque
DelayedJob

Example workflow:

New Gmail message webhook
      ↓
Rails controller
      ↓
Sidekiq job
      ↓
LLM classification
      ↓
create tasks / update sheets

Rails handles this beautifully.

3️⃣ OAuth integrations are easy

You will integrate:

Google Workspace OAuth

Gmail API

Drive API

Calendar API

Rails gems exist for this:

omniauth-google-oauth2
google-api-client
4️⃣ Billing (Stripe)

Rails + Stripe is extremely mature.

Use:

Pay gem

or

Stripe Ruby SDK

You can implement subscriptions in hours.

5️⃣ Admin dashboards

You will need internal tools:

user management

AI usage monitoring

token costs

logs

support tools

Rails gives this instantly with:

ActiveAdmin

or

Administrate


Suggested Rails architecture
Rails 7/8
PostgreSQL
Sidekiq
Redis
Hotwire or React
Example system architecture
User
 ↓
Rails Web App
 ↓
OAuth Google Workspace
 ↓
Background Jobs (Sidekiq)
 ↓
AI Processing (OpenAI)
 ↓
Workspace Actions
  - Gmail
  - Drive
  - Calendar
  - Sheets
Database example

Tables:

users
workspaces
gmail_accounts
emails
tasks
leads
followups
ai_actions
subscriptionsHere is a **clean one-page product specification** version. This format is what founders typically use for **investors, engineers, and early product planning**.

---

# Product Spec — OpsPilot

### AI Executive Copilot for Google Workspace

## Overview

**OpsPilot** is an AI operations assistant for Google Workspace that turns emails and workspace activity into actionable work. Instead of acting as a passive email assistant, OpsPilot functions as a decision-and-execution layer across Gmail, Calendar, Docs, Drive, and Sheets.

The system monitors inbox activity, identifies high-priority messages, extracts tasks and opportunities, drafts responses, schedules meetings, and updates tracking systems automatically.

The goal is simple: **transform Google Workspace from a place where work accumulates into a system that executes work.**

---

## Core Value Proposition

**Turn Gmail into action.**

OpsPilot helps teams:

* Identify urgent emails and opportunities
* Draft responses automatically
* Convert messages into tasks and follow-ups
* Coordinate meetings
* Maintain CRM records
* Generate daily executive briefings

Instead of manually processing dozens of emails per day, users receive prioritized insights and ready-to-send actions.

---

## Target Customers

Primary market:

**Small and mid-sized service businesses using Google Workspace**

Examples include:

* Agencies
* Consulting firms
* Recruitment agencies
* Clinics and professional services
* Small B2B sales teams
* Founders and executive assistants

These teams rely heavily on Gmail but typically lack structured systems for lead management, follow-ups, and task tracking.

---

## Initial Beachhead Use Case

### Sales Inbox + Follow-up Copilot

The first version focuses on identifying inbound business opportunities and ensuring they are never missed.

Key capabilities:

* Detect quote, demo, or inquiry emails
* Summarize the request
* Draft a response
* Create follow-up reminders
* Log the opportunity into a Google Sheet or CRM

This focused use case provides immediate and measurable ROI.

---

## Key Features

### 1. Inbox Command Center

Automated inbox analysis and prioritization.

Capabilities include:

* Email classification (urgent, reply needed, FYI, lead, admin)
* Lead detection
* Priority scoring
* Suggested replies
* Thread summarization

---

### 2. Action Extraction

OpsPilot extracts operational tasks from incoming emails and documents.

Examples:

* Tasks
* Deadlines
* Owners
* Follow-up reminders
* Proposal requests
* Meeting intent

These actions are automatically organized into tasks or calendar items.

---

### 3. Smart Drafting

The assistant generates contextual messages based on email content.

Examples:

* Reply drafts
* Follow-up emails
* Proposal responses
* Meeting scheduling messages
* Internal summaries

Users can approve, edit, or send drafts instantly.

---

### 4. Workspace Automation

OpsPilot can execute actions across Google Workspace.

Supported actions include:

* Creating calendar events
* Updating Google Sheets pipelines
* Searching Drive documents
* Writing Docs summaries
* Assembling meeting preparation briefs

---

### 5. Daily Executive Briefing

Each morning OpsPilot generates a concise operational briefing containing:

* Urgent emails
* Pending follow-ups
* Sales opportunities
* Upcoming meetings
* Blocked tasks

This briefing can be delivered through email, chat, or a Docs summary.

---

## Example Workflows

### Sales Inquiry

Email received:
“Can you send pricing for a 3-month engagement?”

OpsPilot automatically:

* Classifies the message as a sales opportunity
* Extracts the client request
* Drafts a response
* Creates a follow-up reminder
* Adds the lead to a Google Sheets CRM

---

### Meeting Coordination

Email received:
“Can we talk next week?”

OpsPilot:

* Checks calendar availability
* Suggests time slots
* Drafts the scheduling reply
* Creates the calendar event once confirmed

---

### Executive Briefing

User request:
“Summarize everything important today.”

OpsPilot gathers information from:

* Unread priority emails
* Scheduled meetings
* Relevant Drive documents

The system generates a one-page operational summary.

---

## MVP Scope

The first version will focus on core inbox automation.

Features included in MVP:

* Gmail integration
* Email classification
* Task and action extraction
* Reply draft generation
* Follow-up reminders
* Google Sheets CRM updates
* Daily summary report

This provides enough value to begin monetization quickly.

---

## Product Modules

1. **Inbox Command Center** — AI email triage and prioritization
2. **Follow-up Engine** — automated reminders and task generation
3. **Workspace Briefing Engine** — daily summaries and meeting preparation
4. **CRM Sync** — Google Sheets opportunity tracking
5. **Calendar Coordinator** — meeting detection and scheduling assistance

---

## Pricing Model

**Starter — $29 / user / month**

* Gmail triage
* Reply suggestions
* Daily summary

**Pro — $79 / user / month**

* Lead detection
* Follow-ups
* Calendar automation
* Sheets CRM updates

**Team — $149 / user / month**

* Shared inbox workflows
* CRM integrations
* Admin controls
* Team analytics
* Executive assistant mode

---

## Competitive Advantage

The product’s differentiation lies in execution rather than summarization.

Most AI email tools only analyze messages. OpsPilot converts workspace activity into real operational outcomes by coordinating across Gmail, Calendar, Docs, Drive, and Sheets.

This creates a unified automation layer for small teams running their businesses in Google Workspace.

---

## Go-To-Market Positioning

Instead of marketing the product as a generic AI assistant, the messaging focuses on operational reliability.

Primary message:

**“Never miss a lead or follow-up in Gmail again.”**

Secondary positioning:

**“AI assistant for Google Workspace that turns emails into replies, tasks, meetings, and CRM updates.”**

---

## Long-Term Expansion

After the initial sales inbox focus, OpsPilot can expand into:

1. Meeting coordination automation
2. Project document summarization
3. Workspace knowledge search
4. Cross-document briefing generation
5. Full executive assistant workflows

The long-term vision is to create an **AI operator layer for Google Workspace teams**.

---

## Product Vision

OpsPilot transforms Google Workspace from a passive set of productivity tools into an intelligent operations platform.

The assistant monitors incoming information, understands user intent, and executes the next logical step automatically.

In practical terms, **OpsPilot turns email into finished work.**

