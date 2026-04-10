
# ZIVUX CRM — Product Documentation & Investor Overview

> **Version:** 1.0 | **Date:** April 2026 | **Classification:** Confidential — Investor Ready

---

## Table of Contents

1. [Product Overview](#1-product-overview)
2. [Module Architecture](#2-module-architecture)
3. [User Flow / Customer Journey](#3-user-flow--customer-journey)
4. [Features Explanation](#4-features-explanation)
5. [Pricing & SaaS Model](#5-pricing--saas-model)
6. [Enterprise vs SaaS Difference](#6-enterprise-vs-saas-difference)
7. [Investor Perspective](#7-investor-perspective)
8. [Visual Diagrams](#8-visual-diagrams)
9. [Technical Overview](#9-technical-overview-high-level)

---

## 1. PRODUCT OVERVIEW

### What is Zivux CRM?

Zivux CRM is a **cloud-native, multi-tenant Customer Relationship Management platform** purpose-built for B2B sales organizations, distributors, and service enterprises. It unifies the entire customer lifecycle — from lead capture and nurturing through conversion, quotation, and post-sale support — into a single, integrated system.

Unlike horizontal CRMs that require extensive third-party plugins, Zivux ships with **native WhatsApp integration, visual workflow automation (n8n + Camunda BPMN), quotation generation, and AI-assisted engagement** out of the box. This makes it uniquely positioned for markets where WhatsApp is the primary business communication channel (India, Southeast Asia, Middle East, Latin America, Africa).

### Mission

> To democratize enterprise-grade CRM capabilities for growing businesses — enabling them to manage relationships, automate operations, and scale revenue without enterprise-grade budgets.

### Target Users

| Segment               | Use Case                                                  |
|------------------------|----------------------------------------------------------|
| **SMBs (5–50 users)**  | Sales pipeline management, lead tracking, quotations     |
| **Mid-Market (50–500)**| Multi-team collaboration, workflow automation, campaigns  |
| **Enterprise (500+)**  | Custom workflows, BPMN processes, API integrations       |
| **Sales Teams**        | Lead management, follow-ups, WhatsApp engagement         |
| **Distributors**       | Dealer/partner network management, product catalogs      |
| **Service Companies**  | Ticket management, SLA tracking, customer support        |
| **Marketing Teams**    | Campaign management, template-driven outreach            |

### Core Value Proposition

- **All-in-one platform** — No plugin fatigue. Leads, accounts, campaigns, tickets, tasks, quotations, and WhatsApp in one system
- **WhatsApp-native** — First-class WATI integration for business messaging where email fails
- **Visual automation** — Drag-and-drop workflow builder powered by n8n and Camunda BPMN
- **AI-powered assistant** — ZivuxBot for intelligent lead scoring and engagement recommendations
- **Configurable without code** — Dynamic form builder, custom fields, and flexible role permissions

---

## 2. MODULE ARCHITECTURE

### 2.1 Module Hierarchy

```
ZIVUX CRM
│
├── 1. DASHBOARD
│   ├── Lead Metrics & Analytics
│   ├── Pipeline Overview
│   ├── Team Performance
│   └── Activity Feed
│
├── 2. SYSTEM SETTINGS / CONFIGURATION
│   ├── 2.1 Role & Permission Management
│   │   ├── Role Creation & Editing
│   │   ├── Granular Permission Matrix (30+ permissions)
│   │   └── Route-Level Access Control
│   ├── 2.2 Team / Employee Management
│   │   ├── Employee Directory
│   │   ├── Department Management
│   │   └── Employee Dashboard
│   ├── 2.3 Category Management
│   │   ├── Product Categories
│   │   ├── Sub-Categories
│   │   └── WhatsApp Hierarchy Categories
│   ├── 2.4 Product Catalog
│   │   ├── Product Master (SKU, Pricing, GST, HSN)
│   │   ├── Manufacturer Management
│   │   └── Inventory Opening Balance
│   ├── 2.5 Industry Master
│   ├── 2.6 Lead Status Configuration
│   │   ├── Status Pipeline (with color & sequence)
│   │   └── Sub-Status Definitions
│   ├── 2.7 Lead Source Management
│   ├── 2.8 Scheme Management
│   ├── 2.9 Attendance System
│   └── 2.10 Dynamic Form Builder
│       ├── Custom Field Definitions
│       ├── Dependent Field Logic
│       └── Source-Specific Configurations
│
├── 3. ACCOUNTS
│   ├── 3.1 Customers
│   │   ├── Customer Directory
│   │   ├── Customer Detail View
│   │   └── Extra Details & Custom Fields
│   ├── 3.2 Dealers
│   ├── 3.3 Partners
│   └── 3.4 Distributors
│
├── 4. LEAD MANAGEMENT
│   ├── Lead Dashboard
│   ├── Lead Creation & Import (Excel bulk)
│   ├── Lead Detail & History Timeline
│   ├── Lead Assignment & Reassignment
│   ├── Lead Verification
│   ├── Follow-up Scheduling
│   ├── Lead Reports & Analytics
│   └── Quotation Generation (from Lead)
│
├── 5. CAMPAIGN MANAGEMENT
│   ├── Campaign Creation (with Rich Text)
│   ├── Campaign Calendar View
│   ├── Template Management & Preview
│   ├── Multi-Channel Outreach (WhatsApp, Email)
│   └── Campaign Analytics
│
├── 6. WHATSAPP WEB INTEGRATION
│   ├── Chat Interface (Real-time)
│   ├── Template Message Sending
│   ├── Media Upload & Sharing
│   ├── Contact Management
│   ├── Session Management
│   └── Emoji & Rich Media Support
│
├── 7. TICKET MANAGEMENT
│   ├── Manual Ticket Creation
│   ├── Email Ticket Ingestion
│   ├── Ticket Detail View (with File Carousel)
│   ├── Ticket Reports & Analytics
│   ├── Operation Team Management
│   └── SLA Tracking
│
├── 8. TASK MANAGEMENT
│   ├── Task Creation & Assignment
│   ├── Task Detail View
│   ├── Bulk Actions
│   ├── Task Status Tracking
│   └── Task Dashboard
│
├── 9. QUOTATION MANAGEMENT
│   ├── Quotation Builder (Line Items, Tax, Discount)
│   ├── PDF Generation & Preview
│   ├── GST/Tax Computation
│   ├── Draft/Sent Status Tracking
│   └── Payment Terms & Banking Details
│
├── 10. WORKFLOW AUTOMATION
│   ├── n8n Visual Workflow Builder
│   ├── Camunda BPMN Process Designer
│   ├── Trigger-Based Automation
│   │   ├── lead_created, lead_status_changed
│   │   ├── task_created, ticket_created
│   │   ├── whatsapp_message, email_received
│   │   ├── webhook, schedule, manual
│   │   └── campaign_started, account_created
│   └── Action Library
│       ├── Update/Assign Leads
│       ├── Create Tasks/Tickets
│       ├── Send Email/WhatsApp/SMS
│       ├── HTTP Requests & Webhooks
│       └── Conditional Logic & Wait Steps
│
├── 11. REPORTS & ANALYTICS
│   ├── Lead Reports
│   │   ├── Agent Performance
│   │   ├── Geographic Distribution
│   │   ├── Lead Quality Scoring
│   │   ├── Status Distribution
│   │   └── Temperature Distribution
│   └── Ticket Reports
│
├── 12. ZIVUX AI BOT
│   └── AI-Assisted Engagement & Recommendations
│
└── 13. UTILITIES
    ├── QR Code Generation & Registration
    ├── Calendar (Shared)
    ├── Location Master
    ├── Unit Management
    └── File Upload & Management
```

### 2.2 System Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────┐
│                        ZIVUX CRM — PLATFORM                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐              │
│  │   FRONTEND   │  │   API LAYER  │  │  INTEGRATIONS│              │
│  │  (Next.js)   │──│  (REST APIs) │──│              │              │
│  │  React 19    │  │  Laravel BE  │  │  ┌─────────┐ │              │
│  │  TypeScript  │  │              │  │  │WhatsApp │ │              │
│  │  Tailwind    │  │  Auth API    │  │  │ (WATI)  │ │              │
│  │  Redux +     │  │  Lead API    │  │  └─────────┘ │              │
│  │  React Query │  │  Account API │  │  ┌─────────┐ │              │
│  └──────┬───────┘  │  Campaign API│  │  │Camunda  │ │              │
│         │          │  Ticket API  │  │  │ (BPMN)  │ │              │
│         │          │  Task API    │  │  └─────────┘ │              │
│  ┌──────┴───────┐  │  Config API  │  │  ┌─────────┐ │              │
│  │  MIDDLEWARE   │  │  Workflow API│  │  │  n8n    │ │              │
│  │  Auth + RBAC │  └──────┬───────┘  │  │Workflow │ │              │
│  │  30+ Perms   │         │          │  └─────────┘ │              │
│  └──────────────┘         │          │  ┌─────────┐ │              │
│                    ┌──────┴───────┐  │  │Firebase │ │              │
│                    │   DATABASE   │  │  │  Push   │ │              │
│                    │  Multi-Tenant│  │  └─────────┘ │              │
│                    │  Per-Org     │  └──────────────┘              │
│                    └──────────────┘                                 │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### 2.3 Module Interconnection Map

```
                    ┌──────────┐
                    │DASHBOARD │ ◄── Aggregates all module data
                    └────┬─────┘
                         │
          ┌──────────────┼──────────────┐
          │              │              │
    ┌─────┴─────┐  ┌────┴────┐  ┌─────┴──────┐
    │   LEADS   │  │ACCOUNTS │  │ CAMPAIGNS  │
    │           │◄─┤         │  │            │
    └─────┬─────┘  └────┬────┘  └─────┬──────┘
          │              │              │
          │    ┌─────────┴─────────┐   │
          ├────►   QUOTATIONS      │   │
          │    └───────────────────┘   │
          │                            │
    ┌─────┴──────────┐          ┌─────┴──────────┐
    │  WHATSAPP      │◄─────────┤   TEMPLATES    │
    │  INTEGRATION   │          └────────────────┘
    └─────┬──────────┘
          │
    ┌─────┴─────┐     ┌──────────┐
    │  TICKETS  │◄────┤  TASKS   │
    └─────┬─────┘     └────┬─────┘
          │                │
    ┌─────┴────────────────┴─────┐
    │    WORKFLOW AUTOMATION      │
    │  (n8n + Camunda BPMN)      │
    │                            │
    │  Triggers any module       │
    │  based on events           │
    └────────────────────────────┘
          │
    ┌─────┴─────┐     ┌──────────────┐
    │  REPORTS  │     │ ZIVUX AI BOT │
    └───────────┘     └──────────────┘
```

---

## 3. USER FLOW / CUSTOMER JOURNEY

### 3.1 Onboarding Flow

```
┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│  1. SIGN UP  │───►│ 2. ORG SETUP │───►│ 3. PLAN      │
│              │    │              │    │   SELECTION   │
│ • Email/Pass │    │ • Org Name   │    │              │
│ • Company    │    │ • Branch(es) │    │ • Basic      │
│ • Industry   │    │ • Department │    │ • Pro        │
│              │    │ • Logo       │    │ • Enterprise │
└──────────────┘    └──────────────┘    └──────┬───────┘
                                               │
┌──────────────┐    ┌──────────────┐    ┌──────┴───────┐
│  6. GO LIVE  │◄───│ 5. INVITE    │◄───│ 4. MODULE    │
│              │    │    TEAM      │    │   ACTIVATION │
│ • Dashboard  │    │              │    │              │
│ • First Lead │    │ • Add Emps   │    │ • Leads  ✓  │
│ • First Deal │    │ • Set Roles  │    │ • Accounts✓  │
│              │    │ • Assign     │    │ • WhatsApp✓  │
│              │    │   Perms      │    │ • Tickets ✓  │
└──────────────┘    └──────────────┘    └──────────────┘
```

### 3.2 Daily CRM Workflow (Lead → Conversion → Support)

```
LEAD CAPTURE                    NURTURING                      CONVERSION
─────────────────────────────────────────────────────────────────────────────

  ┌────────────┐   ┌────────────┐   ┌────────────┐   ┌────────────┐
  │  Lead      │──►│  Qualify   │──►│  Follow-Up │──►│  Convert   │
  │  Created   │   │  & Assign  │   │  & Engage  │   │  to Account│
  │            │   │            │   │            │   │            │
  │ • Manual   │   │ • Status   │   │ • WhatsApp │   │ • Create   │
  │ • Import   │   │   Pipeline │   │   Chat     │   │   Customer │
  │ • Campaign │   │ • Sub-     │   │ • Calls    │   │ • Generate │
  │ • WhatsApp │   │   Status   │   │ • Email    │   │   Quotation│
  │ • Webhook  │   │ • Assign   │   │ • Campaign │   │ • Close    │
  │            │   │   to Agent │   │ • Schedule │   │   Deal     │
  └────────────┘   └────────────┘   └────────────┘   └─────┬──────┘
                                                            │
POST-SALE SUPPORT                                           │
─────────────────────────────────────────────────────────────┘
                                                            │
  ┌────────────┐   ┌────────────┐   ┌────────────┐  ┌──────┴─────┐
  │  Resolved  │◄──│  Work on   │◄──│  Ticket    │◄─│  Account   │
  │  & Close   │   │  Task/     │   │  Created   │  │  Active    │
  │            │   │  Ticket    │   │            │  │            │
  │ • Close    │   │ • Assign   │   │ • Manual   │  │ • Ongoing  │
  │   Ticket   │   │   Ops Team │   │ • Email    │  │   Support  │
  │ • Customer │   │ • Track    │   │ • Auto via │  │ • Upsell   │
  │   Feedback │   │   Progress │   │   Workflow │  │   Opps     │
  └────────────┘   └────────────┘   └────────────┘  └────────────┘
```

### 3.3 Step-by-Step Customer Journey

| Step | Action | Module Used | Outcome |
|------|--------|-------------|---------|
| 1 | Admin signs up & configures org | Auth + Configuration | Org created, roles defined |
| 2 | Admin selects plan & activates modules | Billing + Settings | Modules unlocked per plan |
| 3 | Admin invites team & assigns roles | Employee Management + RBAC | Team onboarded with permissions |
| 4 | Admin configures lead statuses, sources, products | System Settings | CRM customized to business process |
| 5 | Sales agent creates/imports leads | Lead Management | Pipeline populated |
| 6 | Agent qualifies leads, moves through status pipeline | Lead Management | Leads progressed |
| 7 | Agent engages via WhatsApp, email, campaigns | WhatsApp + Campaigns | Prospects nurtured |
| 8 | Agent generates quotation for qualified lead | Quotation Module | Formal quote sent to prospect |
| 9 | Lead converts to customer account | Accounts Module | Revenue recognized |
| 10 | Customer raises support ticket | Ticket Management | Issue tracked |
| 11 | Internal task created for resolution | Task Management | Work assigned |
| 12 | Workflow automation triggers follow-ups | Workflow Engine | Process automated |
| 13 | Management reviews reports & analytics | Reports + Dashboard | Data-driven decisions |

---

## 4. FEATURES EXPLANATION

### 4.1 Dashboard

| Aspect | Detail |
|--------|--------|
| **What it does** | Centralized command center showing real-time KPIs, pipeline health, team activity, and alerts |
| **Who uses it** | Sales managers, team leads, C-suite executives |
| **Business value** | Instant visibility into business health without digging through modules; enables data-driven decisions |
| **Key metrics** | Lead conversion rate, pipeline value, agent performance, follow-up due, ticket SLA compliance |

### 4.2 System Settings / Configuration

| Aspect | Detail |
|--------|--------|
| **What it does** | Complete admin control panel for customizing every aspect of the CRM |
| **Who uses it** | System administrators, org owners |
| **Business value** | Zero-code customization — businesses configure the CRM to match their exact process without developer intervention |

**Sub-modules:**

- **Role & Permission Management** — 30+ granular permissions controlling access to every module, action, and view. Middleware-enforced at the route level
- **Team/Employee Management** — Employee directory, department hierarchy, attendance tracking, and per-employee dashboards
- **Category Management** — Hierarchical product categories and WhatsApp message categories
- **Product Catalog** — Full product master with SKU, MRP, sale price, cost price, GST percentage, HSN codes, manufacturer details, and inventory opening balances
- **Industry / Lead Status / Lead Source Masters** — Configurable picklists that adapt the CRM vocabulary to each business
- **Dynamic Form Builder** — Drag-and-drop form configuration with dependent field logic, per-source customization, and API-driven field rendering

### 4.3 Accounts (Customers, Dealers, Partners, Distributors)

| Aspect | Detail |
|--------|--------|
| **What it does** | Manages the entire relationship network — customers, dealers, channel partners, and distributors — in a unified account structure |
| **Who uses it** | Account managers, sales teams, channel managers |
| **Business value** | 360-degree view of every business relationship; prevents information silos between sales, support, and management |
| **Key features** | Custom fields, extra details, account detail view, linked leads/tickets/quotations |

### 4.4 Lead Management

| Aspect | Detail |
|--------|--------|
| **What it does** | Full lead lifecycle — capture, qualify, assign, nurture, convert. Includes bulk Excel import, verification, status pipeline with sub-statuses, follow-up scheduling, and inline WhatsApp chat |
| **Who uses it** | Sales agents, SDRs, sales managers |
| **Business value** | No lead falls through the cracks. Visual pipeline management ensures systematic progression. WhatsApp integration means engagement happens where customers actually respond |
| **Key features** | Lead dashboard, status pipeline (with colors & sequencing), sub-status tracking, agent assignment, follow-up dates, lead history timeline, quotation generation from lead, bulk import, lead reports (agent performance, geographic distribution, quality scoring, temperature distribution) |

### 4.5 Campaign Management

| Aspect | Detail |
|--------|--------|
| **What it does** | Create, schedule, and track marketing campaigns with multi-channel outreach (WhatsApp templates, email) and calendar-based planning |
| **Who uses it** | Marketing teams, growth managers |
| **Business value** | Coordinated outreach at scale; template-driven messaging ensures brand consistency; campaign analytics measure ROI |
| **Key features** | Rich text campaign builder, template management with preview, campaign calendar, multi-select targeting, campaign-to-lead attribution |

### 4.6 WhatsApp Web Integration

| Aspect | Detail |
|--------|--------|
| **What it does** | Native WhatsApp Business API integration via WATI — real-time chat, template messaging, media sharing, and contact management directly within the CRM |
| **Who uses it** | Sales agents, support teams, campaign managers |
| **Business value** | Game-changer for markets where WhatsApp is the primary business channel. No context-switching — agents chat with leads/customers without leaving the CRM. Template messages enable compliant, scalable outreach |
| **Key features** | Real-time chat interface, template message sending (with approval flow), media upload & sharing, emoji support, session management, contact sync, WhatsApp-triggered workflows |

### 4.7 Ticket Management

| Aspect | Detail |
|--------|--------|
| **What it does** | Multi-channel support ticket system — manual creation, email ticket ingestion, file attachments (with carousel viewer), operation team routing, and ticket analytics |
| **Who uses it** | Support agents, operations teams, service managers |
| **Business value** | Structured support process with accountability. Email-to-ticket conversion ensures nothing is missed. Analytics reveal support bottlenecks and SLA compliance |
| **Key features** | Manual + email ticket creation, file carousel viewer, operation team assignment, ticket detail view, ticket reports (agent performance, resolution metrics) |

### 4.8 Task Management

| Aspect | Detail |
|--------|--------|
| **What it does** | Internal task assignment, tracking, and bulk management. Tasks can be standalone or linked to leads/tickets/accounts |
| **Who uses it** | All CRM users — agents, managers, ops teams |
| **Business value** | Ensures accountability for every action item. Bulk operations enable efficient management at scale |
| **Key features** | Task creation & assignment, dynamic task views, bulk actions dialog, status tracking, task-to-lead/ticket linking |

### 4.9 Quotation Management

| Aspect | Detail |
|--------|--------|
| **What it does** | Professional quotation generation with line items, tax computation (GST), discounts, payment terms, and PDF export |
| **Who uses it** | Sales agents, account managers |
| **Business value** | Professional, consistent quotes generated in seconds — no spreadsheets. GST-compliant tax computation reduces errors. PDF export enables instant sharing |
| **Key features** | Customer/lead/account selection, item table with pricing, GST/tax auto-calculation, currency support (INR+), discount handling, payment terms, banking details, company branding (logo, GST number), draft/sent status, PDF generation & preview |

### 4.10 Workflow Automation

| Aspect | Detail |
|--------|--------|
| **What it does** | Dual-engine workflow automation — n8n visual builder for business logic and Camunda BPMN for enterprise process management |
| **Who uses it** | Admins, power users, process designers |
| **Business value** | Eliminates manual, repetitive tasks. Ensures process compliance. Scales operations without proportional headcount increase |

**Trigger Events (12):**
`lead_created` · `lead_status_changed` · `lead_assigned` · `task_created` · `ticket_created` · `account_created` · `campaign_started` · `whatsapp_message` · `email_received` · `schedule` · `manual` · `webhook`

**Action Library (18):**
`update_lead` · `assign_lead` · `lead_sub_status` · `create_task` · `update_task` · `create_ticket` · `update_ticket` · `update_account` · `add_to_campaign` · `send_email` · `send_whatsapp` · `send_sms` · `add_note` · `wait` · `condition` · `http_request` · `webhook_send` · `set_variable`

### 4.11 Reports & Analytics

| Aspect | Detail |
|--------|--------|
| **What it does** | Visual analytics across leads and tickets — agent performance, geographic distribution, quality scoring, status distribution, and trend analysis |
| **Who uses it** | Sales managers, C-suite, ops managers |
| **Business value** | Data-driven decision making. Identify top performers, bottleneck stages, and geographic opportunities |
| **Visualization** | ApexCharts + Chart.js for interactive dashboards; jsVectorMap for geographic data |

### 4.12 ZivuxBot (AI Assistant)

| Aspect | Detail |
|--------|--------|
| **What it does** | AI-powered assistant for intelligent engagement recommendations, lead insights, and operational guidance |
| **Who uses it** | Sales agents, managers |
| **Business value** | Augments human judgment with data-driven recommendations; reduces ramp time for new agents |

---

## 5. PRICING & SaaS MODEL

### 5.1 Plan Comparison

```
┌─────────────────┬──────────────────┬──────────────────┬──────────────────┐
│                 │     BASIC        │   PROFESSIONAL   │   ENTERPRISE     │
│                 │   "Get Started"  │  "Scale Faster"  │  "Full Control"  │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ POSITIONING     │ Entry-level for  │ Growth-stage     │ Large orgs with  │
│                 │ small teams      │ companies        │ complex needs    │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ USER LIMIT      │ Up to 10 users   │ Up to 50 users   │ Unlimited        │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ IDEAL CUSTOMER  │ Startups, solo   │ SMBs with sales  │ Enterprises,     │
│                 │ founders, micro  │ + support teams  │ multi-branch     │
│                 │ businesses       │                  │ distributors     │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│                 │                  │                  │                  │
│ MODULES         │                  │                  │                  │
│                 │                  │                  │                  │
│ Dashboard       │       ✓          │       ✓          │       ✓          │
│ Leads           │       ✓          │       ✓          │       ✓          │
│ Accounts        │  Customers only  │  Full (4 types)  │  Full (4 types)  │
│ Tasks           │       ✓          │       ✓          │       ✓          │
│ Tickets         │  Manual only     │  Manual + Email  │  Full + SLA      │
│ Campaigns       │       —          │       ✓          │       ✓          │
│ WhatsApp        │       —          │       ✓          │       ✓          │
│ Quotations      │  Basic           │       ✓          │  ✓ + Custom PDF  │
│ Reports         │  Basic           │  Full Analytics  │  Full + Custom   │
│ Workflow (n8n)  │       —          │       ✓          │       ✓          │
│ BPMN (Camunda)  │       —          │       —          │       ✓          │
│ ZivuxBot AI     │       —          │  Limited         │       ✓          │
│ Dynamic Forms   │       —          │       ✓          │       ✓          │
│ API Access      │       —          │  Read-only       │  Full CRUD       │
│ Multi-Branch    │       —          │       —          │       ✓          │
│ Custom Roles    │  3 preset roles  │  10 custom roles │  Unlimited       │
│ Permissions     │  Basic (view/add)│  Full granular   │  Full + custom   │
│ Products        │  Up to 100       │  Up to 1,000     │  Unlimited       │
│ Bulk Import     │       —          │       ✓          │  ✓ + Automation  │
│ QR Generation   │       —          │       ✓          │       ✓          │
│ Calendar        │       ✓          │       ✓          │       ✓          │
│                 │                  │                  │                  │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ STORAGE         │ 5 GB             │ 25 GB            │ 100 GB+          │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ SUPPORT         │ Email            │ Email + Chat     │ Dedicated AM     │
│                 │ (48hr SLA)       │ (24hr SLA)       │ (4hr SLA)        │
├─────────────────┼──────────────────┼──────────────────┼──────────────────┤
│ PRICE TIER      │       $          │       $$         │      $$$         │
│ (per user/mo)   │                  │  ~2.5x Basic     │   Custom quote   │
└─────────────────┴──────────────────┴──────────────────┴──────────────────┘
```

### 5.2 Subscription Model

| Aspect | Detail |
|--------|--------|
| **Billing Cycle** | Monthly and Annual (annual = ~20% discount) |
| **Trial** | 14-day free trial on Professional plan |
| **Pricing Model** | Per-user, per-month (seat-based) |
| **Add-ons** | WhatsApp message packs, additional storage, API call quotas |
| **Upgrade Path** | Seamless mid-cycle upgrade with prorated billing |
| **Downgrade** | Effective at next billing cycle; data retained |

### 5.3 Multi-Tenant SaaS Architecture

```
┌─────────────────────────────────────────────┐
│              ZIVUX CLOUD PLATFORM           │
│                                             │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐   │
│   │  Org A  │  │  Org B  │  │  Org C  │   │   Each org = isolated tenant
│   │ store_1 │  │ store_5 │  │ store_9 │   │   Each store = branch
│   │ store_2 │  │ store_6 │  │ store_10│   │
│   └────┬────┘  └────┬────┘  └────┬────┘   │
│        │            │            │         │
│   ┌────┴────────────┴────────────┴────┐    │
│   │        SHARED APPLICATION LAYER    │    │
│   │   (Next.js Frontend + API Gateway) │    │
│   └────────────────┬──────────────────┘    │
│                    │                       │
│   ┌────────────────┴──────────────────┐    │
│   │       DATA ISOLATION LAYER         │    │
│   │   org_id + store_id partitioning   │    │
│   │   Per-tenant encryption keys       │    │
│   └───────────────────────────────────┘    │
│                                             │
└─────────────────────────────────────────────┘
```

**Key Architectural Properties:**
- **Tenant isolation** via `org_id` — every query is scoped to the organization
- **Branch support** via `store_id` / `branch_id` — enterprises with multiple locations get isolated views
- **Shared compute** — single application deployment serves all tenants (cost-efficient)
- **Per-tenant customization** — dynamic forms, custom fields, and role permissions are org-specific
- **Scalability** — horizontal scaling at the application layer; database sharding at the data layer

---

## 6. ENTERPRISE VS SaaS DIFFERENCE

### 6.1 Feature Comparison

| Capability | Standard SaaS | Enterprise |
|------------|:------------:|:----------:|
| Lead Management | ✓ | ✓ |
| Account Types (All 4) | ✓ (Pro+) | ✓ |
| WhatsApp Integration | ✓ (Pro+) | ✓ + Custom WATI instance |
| Ticket Management | ✓ | ✓ + Custom SLA rules |
| Campaign Management | ✓ (Pro+) | ✓ + Advanced targeting |
| n8n Workflows | ✓ (Pro+) | ✓ + Unlimited workflows |
| **Camunda BPMN** | — | ✓ |
| **Multi-Branch** | — | ✓ |
| **Custom API Integrations** | Read-only (Pro) | Full CRUD + Webhooks |
| **ZivuxBot AI (Full)** | Limited | ✓ |
| **Dynamic Form Builder** | ✓ (Pro+) | ✓ + Advanced logic |
| **Dedicated Infrastructure** | Shared | Optional dedicated tenant |
| **SSO / SAML** | — | ✓ |
| **Audit Logs** | — | ✓ |
| **Custom PDF Templates** | — | ✓ |
| **Priority Support (4hr SLA)** | — | ✓ |
| **Onboarding Assistance** | Self-serve | Dedicated team |
| **Data Export** | CSV | CSV + API + Custom |
| **Uptime SLA** | 99.5% | 99.9% |

### 6.2 Customization Capabilities

| Layer | Standard SaaS | Enterprise |
|-------|:------------:|:----------:|
| **Fields** | Dynamic form builder — add custom fields to any entity | Same + dependent field logic, conditional visibility |
| **Workflows** | n8n visual builder with 12 triggers, 18 actions | Same + Camunda BPMN for complex multi-department processes |
| **Roles** | Up to 10 custom roles with 30+ permissions | Unlimited roles + custom permission groups |
| **Branding** | Logo + company details on quotations | Full white-label option |
| **Integrations** | WhatsApp (WATI), Email | Custom API connectors, ERP integration, payment gateways |
| **Reporting** | Pre-built dashboards and reports | Custom report builder + data warehouse export |

---

## 7. INVESTOR PERSPECTIVE

### 7.1 Revenue Model

```
┌─────────────────────────────────────────────────────────┐
│                    REVENUE STREAMS                       │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  1. SUBSCRIPTION REVENUE (Primary — ~70%)               │
│     • Per-user, per-month SaaS subscriptions            │
│     • Annual contracts with 20% discount                │
│     • High gross margin (80%+ at scale)                 │
│     • Net Revenue Retention target: 120%+               │
│                                                         │
│  2. USAGE-BASED REVENUE (~15%)                          │
│     • WhatsApp message packs (per-message pricing)      │
│     • Storage add-ons                                   │
│     • API call quotas                                   │
│     • AI bot interaction credits                        │
│                                                         │
│  3. PROFESSIONAL SERVICES (~10%)                        │
│     • Enterprise onboarding & implementation            │
│     • Custom workflow design                            │
│     • Data migration services                           │
│     • Training programs                                 │
│                                                         │
│  4. MARKETPLACE / INTEGRATIONS (~5% future)             │
│     • Third-party app marketplace                       │
│     • Integration connector fees                        │
│     • Partner referral revenue                          │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### 7.2 Market Opportunity

| Dimension | Detail |
|-----------|--------|
| **TAM (Total Addressable Market)** | Global CRM market: $89B+ (2024), growing at ~14% CAGR |
| **SAM (Serviceable)** | SMB/Mid-market CRM in WhatsApp-first markets (India, SEA, MENA, LatAm): ~$12B |
| **SOM (Obtainable)** | Initial beachhead — Indian B2B SMBs with WhatsApp-centric sales: ~$800M |
| **Growth Driver** | WhatsApp Business API adoption accelerating; 100M+ businesses on WhatsApp globally |

### 7.3 Competitive Advantage

```
┌────────────────────────────────────────────────────────────┐
│                   COMPETITIVE MOAT                         │
├────────────────────────────────────────────────────────────┤
│                                                            │
│  1. WHATSAPP-NATIVE CRM                                    │
│     Most CRMs treat WhatsApp as a plugin. Zivux makes it  │
│     a first-class citizen — chat in-context with leads,    │
│     trigger workflows from messages, run campaigns.        │
│     This is a wedge into WhatsApp-first markets.           │
│                                                            │
│  2. DUAL WORKFLOW ENGINE                                   │
│     n8n for business users + Camunda BPMN for enterprises. │
│     No other mid-market CRM offers both. This bridges      │
│     the gap between "easy" and "powerful."                  │
│                                                            │
│  3. GST/TAX-NATIVE QUOTATION                              │
│     Built-in GST computation, HSN codes, and Indian tax    │
│     compliance. Eliminates the need for separate billing   │
│     software for Indian businesses.                        │
│                                                            │
│  4. DYNAMIC FORM BUILDER                                   │
│     Zero-code customization means faster time-to-value     │
│     and lower churn. Businesses don't outgrow the CRM.     │
│                                                            │
│  5. MULTI-TENANT, MULTI-BRANCH                             │
│     Distributed businesses (franchises, dealer networks,   │
│     multi-city operations) get branch-level isolation       │
│     within a single org. Few mid-market CRMs offer this.   │
│                                                            │
│  6. AI-FIRST TRAJECTORY                                    │
│     ZivuxBot lays the foundation for AI-driven lead        │
│     scoring, auto-responses, and predictive analytics.     │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### 7.4 Expansion Strategy

| Phase | Timeline | Focus |
|-------|----------|-------|
| **Phase 1 — Beachhead** | Year 1–2 | Indian B2B SMBs. Land with WhatsApp integration as the wedge. Free-to-paid conversion via Basic → Pro |
| **Phase 2 — Vertical Depth** | Year 2–3 | Industry-specific templates (Real Estate, Education, Manufacturing, Healthcare). Pre-built workflows per vertical |
| **Phase 3 — Geographic Expansion** | Year 3–4 | SEA (Indonesia, Philippines), MENA (UAE, Saudi), LatAm (Brazil, Mexico). WhatsApp-first economies |
| **Phase 4 — Platform Play** | Year 4–5 | App marketplace, partner ecosystem, API economy. Become the operating system for mid-market sales |

### 7.5 Key Metrics (Targets)

| Metric | Year 1 | Year 2 | Year 3 |
|--------|--------|--------|--------|
| Customers (Orgs) | 200 | 800 | 2,500 |
| Users | 2,000 | 12,000 | 50,000 |
| ARR | — | — | — |
| Net Revenue Retention | 110% | 120% | 130% |
| Gross Margin | 75% | 80% | 85% |
| CAC Payback (months) | 18 | 12 | 9 |
| Monthly Churn | <5% | <3% | <2% |

### 7.6 Why Now?

1. **WhatsApp Business API** has matured — conversation-based pricing makes it viable for SMBs
2. **India's digital transformation** — UPI, GST digitization, and remote work have made SMBs CRM-ready
3. **AI inflection point** — GPT/LLM integration enables a new class of CRM intelligence
4. **Incumbents are expensive** — Salesforce, HubSpot pricing excludes most SMBs in emerging markets
5. **No dominant WhatsApp-first CRM** exists — the category is still up for grabs

---

## 8. VISUAL DIAGRAMS

### 8.1 CRM Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         ZIVUX CRM ARCHITECTURE                         │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  ┌─────────────────────────────────────────────────────────────┐       │
│  │                      PRESENTATION LAYER                     │       │
│  │                                                             │       │
│  │  Next.js 15 (App Router) + React 19 + TypeScript            │       │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐      │       │
│  │  │Tailwind  │ │ Radix UI │ │ MUI v7   │ │ Shadcn   │      │       │
│  │  │  CSS     │ │Components│ │Date/Icons│ │   UI     │      │       │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘      │       │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐                   │       │
│  │  │ApexCharts│ │ Chart.js │ │VectorMap │  Data Viz          │       │
│  │  └──────────┘ └──────────┘ └──────────┘                   │       │
│  └──────────────────────────┬──────────────────────────────────┘       │
│                             │                                          │
│  ┌──────────────────────────┴──────────────────────────────────┐       │
│  │                     STATE MANAGEMENT                        │       │
│  │                                                             │       │
│  │  ┌──────────────┐  ┌────────────────┐  ┌───────────────┐  │       │
│  │  │ Redux Toolkit │  │ React Query    │  │ Context API   │  │       │
│  │  │ (Auth State)  │  │ (Server State) │  │ (UI State)    │  │       │
│  │  └──────────────┘  └────────────────┘  └───────────────┘  │       │
│  └──────────────────────────┬──────────────────────────────────┘       │
│                             │                                          │
│  ┌──────────────────────────┴──────────────────────────────────┐       │
│  │                     MIDDLEWARE LAYER                         │       │
│  │                                                             │       │
│  │  ┌──────────────────────────────────────────────────────┐  │       │
│  │  │  Next.js Middleware (Auth + RBAC — 30+ Permissions)  │  │       │
│  │  │  AES Encryption (crypto-js) + Token Management       │  │       │
│  │  └──────────────────────────────────────────────────────┘  │       │
│  └──────────────────────────┬──────────────────────────────────┘       │
│                             │                                          │
│  ┌──────────────────────────┴──────────────────────────────────┐       │
│  │                      API GATEWAY                            │       │
│  │                                                             │       │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  │       │
│  │  │ Core API │  │ Emp API  │  │ OTP/File │  │ Workflow │  │       │
│  │  │(Laravel) │  │(Employees│  │(Upload)  │  │(n8n/BPMN)│  │       │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘  │       │
│  └──────────────────────────┬──────────────────────────────────┘       │
│                             │                                          │
│  ┌──────────────────────────┴──────────────────────────────────┐       │
│  │                    EXTERNAL SERVICES                        │       │
│  │                                                             │       │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  │       │
│  │  │ WhatsApp │  │ Camunda  │  │ Firebase │  │  SMTP    │  │       │
│  │  │  (WATI)  │  │  Engine  │  │  (Push)  │  │ (Email)  │  │       │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘  │       │
│  └─────────────────────────────────────────────────────────────┘       │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

### 8.2 Data Flow Diagram

```
                    INBOUND                         PROCESSING                      OUTBOUND
                    ─────────                       ──────────                      ────────

  ┌─────────┐                             ┌──────────────────┐
  │ Web Form │─────┐                      │                  │             ┌──────────────┐
  └─────────┘     │                      │   LEAD ENGINE    │────────────►│ WhatsApp Msg │
  ┌─────────┐     │    ┌──────────┐      │                  │             └──────────────┘
  │WhatsApp │─────┼───►│  LEAD    │─────►│  • Assign        │             ┌──────────────┐
  └─────────┘     │    │ CAPTURE  │      │  • Qualify       │────────────►│ Email        │
  ┌─────────┐     │    └──────────┘      │  • Score         │             └──────────────┘
  │  Excel  │─────┤                      │  • Route         │             ┌──────────────┐
  └─────────┘     │                      └────────┬─────────┘────────────►│ SMS          │
  ┌─────────┐     │                               │                       └──────────────┘
  │Campaign │─────┘                               │
  └─────────┘                                     ▼
                                          ┌──────────────────┐
                                          │   CONVERSION     │             ┌──────────────┐
                                          │                  │────────────►│ Quotation PDF│
                                          │  • Quote         │             └──────────────┘
                                          │  • Negotiate     │             ┌──────────────┐
                                          │  • Close         │────────────►│ Account      │
                                          └────────┬─────────┘             │ Created      │
                                                   │                       └──────────────┘
                                                   ▼
                                          ┌──────────────────┐
                                          │   POST-SALE      │             ┌──────────────┐
                                          │                  │────────────►│ Reports &    │
                                          │  • Support       │             │ Analytics    │
                                          │  • Upsell        │             └──────────────┘
                                          │  • Retain        │             ┌──────────────┐
                                          └──────────────────┘────────────►│ Dashboard    │
                                                                           └──────────────┘
```

### 8.3 SaaS Plan Comparison (Visual)

```
     BASIC                    PROFESSIONAL               ENTERPRISE
  ┌──────────┐             ┌──────────────┐           ┌──────────────┐
  │          │             │              │           │              │
  │  ██████  │             │  ██████████  │           │ ████████████ │
  │  ██████  │  Features   │  ██████████  │           │ ████████████ │
  │          │  Coverage   │  ██████████  │           │ ████████████ │
  │          │             │  ██████████  │           │ ████████████ │
  │          │             │              │           │ ████████████ │
  └──────────┘             └──────────────┘           └──────────────┘

   10 users                  50 users                   Unlimited
   5 modules                 11 modules                 All modules
   3 roles                   10 roles                   Unlimited
   No automation             n8n workflows              n8n + Camunda
   No WhatsApp               WhatsApp ✓                 WhatsApp ✓
   Email support             Chat support               Dedicated AM
```

### 8.4 Permission Matrix (Simplified)

```
PERMISSION              │ Admin │ Manager │ Agent │ Viewer
────────────────────────┼───────┼─────────┼───────┼───────
view_lead_management    │   ✓   │    ✓    │   ✓   │   ✓
add_lead_management     │   ✓   │    ✓    │   ✓   │   —
edit_lead_management    │   ✓   │    ✓    │   ✓   │   —
view_customer           │   ✓   │    ✓    │   ✓   │   ✓
add_customer            │   ✓   │    ✓    │   —   │   —
view_marketing_campaign │   ✓   │    ✓    │   ✓   │   ✓
add_marketing_campaign  │   ✓   │    ✓    │   —   │   —
view_whatsapp           │   ✓   │    ✓    │   ✓   │   —
view_task_management    │   ✓   │    ✓    │   ✓   │   ✓
add_task_management     │   ✓   │    ✓    │   ✓   │   —
view_manual_ticket      │   ✓   │    ✓    │   ✓   │   ✓
add_manual_ticket       │   ✓   │    ✓    │   ✓   │   —
view_role_management    │   ✓   │    —    │   —   │   —
view_team               │   ✓   │    ✓    │   —   │   —
add_team                │   ✓   │    —    │   —   │   —
view_product            │   ✓   │    ✓    │   ✓   │   ✓
add_product             │   ✓   │    ✓    │   —   │   —
view_lead_workflow      │   ✓   │    ✓    │   —   │   —
lead_reports            │   ✓   │    ✓    │   —   │   —
view_tickets_reports    │   ✓   │    ✓    │   —   │   —
zivux_bot               │   ✓   │    ✓    │   ✓   │   —
```

---

## 9. TECHNICAL OVERVIEW (HIGH LEVEL)

### 9.1 Technology Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Frontend Framework** | Next.js 15 (App Router) | SSR, routing, middleware |
| **UI Library** | React 19 + TypeScript | Component-based UI |
| **Styling** | Tailwind CSS 3.4 + Radix UI + MUI v7 | Design system |
| **State (Client)** | Redux Toolkit | Authentication state |
| **State (Server)** | TanStack React Query | API data caching & sync |
| **Backend** | Laravel (REST API) | Business logic, data persistence |
| **Auth** | AES Encryption (crypto-js) + bcrypt | Credential security |
| **Workflow** | n8n + Camunda BPMN (bpmn-js) | Visual automation |
| **Flow Builder** | React Flow (@xyflow/react) | Workflow canvas |
| **WhatsApp** | WATI API | Business messaging |
| **Push Notifications** | Firebase | Real-time alerts |
| **Charts** | ApexCharts + Chart.js | Data visualization |
| **Maps** | jsVectorMap | Geographic analytics |
| **PDF** | jsPDF + jspdf-autotable | Quotation generation |
| **Excel** | SheetJS (XLSX) | Import/export |
| **Rich Text** | React Quill | Campaign content editing |
| **Validation** | Yup | Schema validation |

### 9.2 Cloud-Based SaaS Architecture

```
┌──────────────────────────────────────────────────┐
│                 CLOUD INFRASTRUCTURE              │
│                                                  │
│  ┌────────────┐    ┌─────────────┐               │
│  │   CDN      │    │ Load        │               │
│  │ (Static)   │    │ Balancer    │               │
│  └─────┬──────┘    └──────┬──────┘               │
│        │                  │                      │
│  ┌─────┴──────────────────┴──────┐               │
│  │      APPLICATION SERVERS       │               │
│  │   (Next.js + Node.js Runtime)  │               │
│  │   Auto-scaling (2–N instances) │               │
│  └───────────────┬────────────────┘               │
│                  │                                │
│  ┌───────────────┴────────────────┐               │
│  │       API / BACKEND SERVERS    │               │
│  │      (Laravel + PHP Runtime)   │               │
│  │   Auto-scaling (2–N instances) │               │
│  └───────────────┬────────────────┘               │
│                  │                                │
│  ┌───────┬───────┴───────┬────────┐               │
│  │ MySQL │   Redis       │ Object │               │
│  │  DB   │   Cache       │Storage │               │
│  │(Multi-│   (Session)   │(Files) │               │
│  │tenant)│               │        │               │
│  └───────┘   └───────────┘ └──────┘               │
│                                                  │
└──────────────────────────────────────────────────┘
```

### 9.3 Role-Based Access Control (RBAC)

The system implements **middleware-enforced RBAC** with 30+ granular permissions:

- **Authentication**: AES-encrypted credentials, dual-token system (`_token` for API, `v2_token` for WhatsApp)
- **Authorization**: Next.js middleware intercepts every route, checks `user_crm_permissions` cookie against required permissions
- **Granularity**: View/Add/Edit permissions per module (e.g., `view_lead_management`, `add_lead_management`, `edit_lead_management`)
- **Storage**: Permissions stored as comma-separated strings in HTTP-only cookies
- **Enforcement**: 403 response for unauthorized access; automatic redirect for unauthenticated users

### 9.4 API Integration Architecture

```
ZIVUX FRONTEND
      │
      ├── Core CRM API (Laravel)
      │   ├── /login — Authentication
      │   ├── /api/getDynamicFormBySource — Dynamic fields
      │   ├── /api/getCountry — Reference data
      │   └── /api/* — CRUD for all entities
      │
      ├── Employee API
      │   ├── /emp-api/employees — Employee CRUD
      │   ├── /emp-api/get-departments — Departments
      │   └── /emp-api/getAttendance — Attendance
      │
      ├── WhatsApp API (WATI)
      │   ├── /api/watiConversation — Messages
      │   ├── /api/GetTemplates — Templates
      │   ├── /api/whatsappTextMessageCloudAPI — Send
      │   └── /api/checkSessionStatus — Session
      │
      ├── Workflow API
      │   ├── /GetN8nWorkflow — n8n definitions
      │   └── /camunda-api/* — Camunda BPMN engine
      │
      └── Media/OTP API
          ├── /api/v2.0/image_upload — Media
          ├── /api/v2.0/sendMessage — Messaging
          └── /api/v2.0/upload-media — File upload
```

### 9.5 Data Structure Overview

```
┌──────────────────────────────────────────────────────────────────┐
│                      CORE DATA ENTITIES                          │
├──────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ORGANIZATION (org_id)                                           │
│  └── BRANCH (store_id / branch_id)                               │
│      ├── USERS (id, name, email, role, permissions)              │
│      ├── LEADS                                                   │
│      │   ├── id, customer_name, email, contact_no               │
│      │   ├── company_name, industry, priority                    │
│      │   ├── status → STATUS (id, name, color, sequence)         │
│      │   │            └── SUB_STATUS (id, name)                  │
│      │   ├── lead_source, campaign_name                          │
│      │   ├── assignee, followup_date                             │
│      │   ├── quotation_exists, quotation_status                  │
│      │   └── [dynamic_fields...] — via Dynamic Form Builder      │
│      │                                                           │
│      ├── ACCOUNTS (customers, dealers, partners, distributors)   │
│      │   ├── id, name, type, contact_info                        │
│      │   └── [extra_details...] — custom fields                  │
│      │                                                           │
│      ├── CAMPAIGNS                                               │
│      │   ├── id, name, type, status                              │
│      │   ├── content (rich text), templates                      │
│      │   └── schedule, target_audience                           │
│      │                                                           │
│      ├── TICKETS                                                 │
│      │   ├── id, subject, description, status                    │
│      │   ├── source (manual/email), priority                     │
│      │   ├── assigned_to, operation_team                         │
│      │   └── attachments[]                                       │
│      │                                                           │
│      ├── TASKS                                                   │
│      │   ├── id, title, description, status                      │
│      │   ├── assigned_to, due_date                               │
│      │   └── linked_entity (lead/ticket/account)                 │
│      │                                                           │
│      ├── QUOTATIONS                                              │
│      │   ├── id, quotation_number, date, validity                │
│      │   ├── customer/lead reference                             │
│      │   ├── line_items[] (product, qty, price, tax, discount)   │
│      │   ├── totals (subtotal, tax, grand_total)                 │
│      │   └── status (draft/sent), payment_terms                  │
│      │                                                           │
│      ├── PRODUCTS                                                │
│      │   ├── id, name, item_cd, category, sub_category           │
│      │   ├── mrp, sale_price, cost_price, net_rate               │
│      │   ├── gst_perc, hsn_code                                  │
│      │   └── manufacturer, inventory                             │
│      │                                                           │
│      ├── WORKFLOWS                                               │
│      │   ├── id, name, trigger_type                              │
│      │   ├── nodes[] (type, config, position)                    │
│      │   └── connections[] (source → target)                     │
│      │                                                           │
│      └── CONFIGURATION                                           │
│          ├── ROLES (id, name, permissions[])                     │
│          ├── STATUSES (id, name, color, sequence, sub_statuses[])│
│          ├── CATEGORIES (id, name, sub_categories[])             │
│          ├── INDUSTRIES (id, name)                               │
│          ├── LEAD_SOURCES (id, name)                             │
│          └── DYNAMIC_FIELDS (source, field_config[])             │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

### 9.6 Security Overview

| Layer | Mechanism |
|-------|-----------|
| **Transport** | HTTPS/TLS for all communications |
| **Authentication** | AES-256 encrypted login payloads; bcrypt password hashing |
| **Session** | Dual-token system; encrypted sessionStorage; HTTP-only permission cookies |
| **Authorization** | Middleware-enforced RBAC at every route; 30+ granular permissions |
| **Data Isolation** | Multi-tenant via `org_id` scoping; branch isolation via `store_id` |
| **Input Validation** | Yup schema validation on forms; server-side validation on API |
| **Encryption** | crypto-js AES for sensitive data at rest in browser storage |

---

## APPENDIX: GLOSSARY

| Term | Definition |
|------|-----------|
| **Org** | Organization — the top-level tenant in the multi-tenant architecture |
| **Branch / Store** | A physical or logical location within an organization |
| **Lead** | A potential customer at any stage of the sales pipeline |
| **Account** | A converted business relationship (customer, dealer, partner, or distributor) |
| **Status Pipeline** | The sequence of stages a lead moves through (e.g., New → Contacted → Qualified → Won) |
| **Sub-Status** | A secondary status providing granularity within a pipeline stage |
| **WATI** | WhatsApp Team Inbox — the third-party API used for WhatsApp Business integration |
| **n8n** | Open-source workflow automation platform, integrated as the visual workflow builder |
| **Camunda BPMN** | Enterprise-grade Business Process Model and Notation engine for complex process automation |
| **Dynamic Fields** | Custom form fields configured per entity type via the Dynamic Form Builder |
| **RBAC** | Role-Based Access Control — permissions model governing module and action access |
| **HSN** | Harmonized System of Nomenclature — product classification code used in GST compliance |

---

> **Document prepared for investor review.**
> **Zivux CRM — Where relationships become revenue.**
