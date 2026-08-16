# Campaign Operations & QA Platform

> **A configurable platform for campaign management, batch processing, intelligent lead distribution, customer follow-ups, dynamic evaluations, automated scoring, and agent performance tracking.**

Campaign Operations & QA Platform is an enterprise-oriented workflow management system designed to centralize and automate operational processes that are traditionally handled through Excel files and manual coordination.

The platform manages the complete lifecycle from **campaign and batch creation to intelligent customer assignment, follow-up handling, dynamic QA evaluation, automated scoring, and agent KPI tracking**.

---

## Overview

Traditional operational environments often rely heavily on Excel files to manage:

- Customer lists
- Campaigns
- Agent assignments
- Follow-ups
- Call results
- QA evaluations
- Agent performance
- KPIs and reports

This manual approach can lead to:

- Duplicate assignments
- Manual customer distribution
- Inconsistent evaluation processes
- Manual score calculations
- Difficult campaign management
- Limited agent performance visibility
- Data integrity issues
- Fragmented operational history

The **Campaign Operations & QA Platform** centralizes these processes into a configurable workflow management system.

Instead of building a separate workflow for every campaign, administrators can configure campaigns, batches, evaluation forms, validation rules, scoring logic, and operational workflows dynamically.

---

---

# Screenshots

The following screenshots demonstrate the main workflows and interfaces of the platform.

## Authentication

### Login

![Login](./Screen%20Shoot/01-Login.png)

---

## Agent Workspace

### Agent Dashboard

![Agent Dashboard](./Screen%20Shoot/02-Agent%20Dashboard.png)

### Agent Work Queue

![Agent Work Queue](./Screen%20Shoot/03-Agent%20Work%20Queue.png)

---

## Administration

### Admin Dashboard

![Admin Dashboard](./Screen%20Shoot/04-Admin%20Dashboard.png)

### Batches Management

![Batches](./Screen%20Shoot/05-Batches.png)

### Evaluation Forms

![Forms](./Screen%20Shoot/06-Forms.png)

### Call Results

![Call Results](./Screen%20Shoot/07-Call%20Results.png)

### Daily Targets

![Daily Targets](./Screen%20Shoot/08-Daily%20Targets.png)

### Calls Management

![Calls](./Screen%20Shoot/09-Calls.png)

---

# Core Architecture

The platform is built around a **Campaign-Based Operational Architecture**.

Each campaign can have its own:

- Customer batches
- Assigned agents
- Workflow configuration
- Evaluation form
- Validation rules
- Scoring rules
- Operational requirements
- Performance metrics

This allows multiple campaigns to operate simultaneously while maintaining independent configurations.

---

# Campaign Management

Administrators can create and manage dedicated campaigns.

Each campaign represents an independent operational workflow with its own configuration and customer population.

### Capabilities

- Create campaigns
- Activate / deactivate campaigns
- Configure campaign settings
- Assign agents
- Configure campaign workflows
- Configure evaluation requirements
- Monitor campaign progress
- Track campaign performance

The campaign architecture makes the platform configurable without requiring application code changes for every new campaign.

---

# Batch Management

Customer data is imported into campaigns through **batches**.

Instead of maintaining one large global customer list, the platform organizes imported customers into manageable batches associated with specific campaigns.

### Capabilities

- Import customer lists
- Associate batches with campaigns
- Validate imported data
- Detect duplicate records
- Track batch status
- Monitor processing progress
- Control batch availability
- Track customer origin

This provides better control over large customer datasets and campaign operations.

---

# Intelligent Lead Queue

One of the core components of the platform is the centralized **Smart Lead Queue**.

Agents do not manually select customers.

Instead, an agent requests:

> **Next Lead**

The system determines which customer should be assigned according to the configured workflow.

### Queue Decision Flow

```text
Agent requests Next Lead
          │
          ▼
Check Follow-Up Queue
          │
     ┌────┴────┐
     │         │
   Found     Not Found
     │         │
     ▼         ▼
Assign      Check Agent
Follow-Up   Campaigns
                │
                ▼
        Find Available Lead
                │
                ▼
          Lock & Assign
```

The system can evaluate:

- Existing follow-up tasks
- Agent eligibility
- Agent campaign assignments
- Available campaign customers
- Customer availability
- Queue priority
- Campaign workflow rules

The selected customer is then locked and assigned to prevent duplicate processing.

### Benefits

- Prevents duplicate assignments
- Eliminates manual distribution
- Centralizes queue management
- Supports multiple campaigns
- Supports follow-up prioritization
- Improves agent utilization
- Provides consistent lead allocation

---

# Follow-Up Management

Customers who require another interaction can be returned to a dedicated follow-up workflow.

The system stores the required callback information and makes the customer eligible for future assignment according to the configured rules.

### Follow-Up Capabilities

- Schedule callbacks
- Track callback dates
- Track previous attempts
- Store call history
- Track call status
- Store agent notes
- Prioritize follow-up customers
- Automatically return eligible customers to the queue

This creates a complete customer interaction lifecycle instead of treating every call as an isolated operation.

---

# Dynamic Evaluation Engine

The platform includes a configurable evaluation engine that allows evaluation forms to be created dynamically.

Evaluation forms are not tightly coupled to application code.

Different campaigns can use completely different evaluation structures while using the same underlying system.

### Form Capabilities

- Campaign-specific forms
- Custom questions
- Multiple question types
- Required questions
- Conditional questions
- Validation rules
- Configurable scoring
- Dynamic evaluation workflows

This architecture makes it possible to introduce new evaluation workflows without rebuilding the application.

---

# Validation Engine

The platform validates submitted evaluation answers according to rules configured for each campaign and form.

Validation can determine whether an evaluation:

- Is complete
- Contains valid answers
- Meets required conditions
- Passes specific criteria
- Qualifies for scoring

This ensures consistency across evaluations and reduces manual QA processing.

---

# Automated Scoring

After validation, the system automatically calculates the evaluation score according to the configured scoring rules.

### Scoring Features

- Question-based scoring
- Weighted questions
- Validation-based scoring
- Pass / Fail conditions
- Automatic score calculation
- Evaluation status
- Performance indicators

This eliminates manual score calculations and ensures consistent evaluation results.

---

# Agent Performance Tracker

The platform includes an agent-level performance tracking system.

The system does not only store the final result of a call.

It also tracks operational activity to generate meaningful KPIs for every agent.

### Example Metrics

- Completed calls
- Attempted calls
- Total calls
- Call duration
- Total talk time
- Average call duration
- Follow-up activity
- Evaluation scores
- Successful interactions
- Failed attempts
- Daily performance
- Monthly performance
- Campaign performance

This provides supervisors with measurable insight into agent productivity and operational performance.

---

# Call Activity Tracking

Each customer interaction can generate a detailed activity record.

Tracked information can include:

- Call start time
- Call end time
- Call duration
- Call status
- Customer interaction result
- Agent notes
- Callback information
- Evaluation result

This creates a complete operational history for both customers and agents.

---

# KPI & Analytics

The platform transforms operational activity into measurable performance indicators.

## Agent KPIs

Examples include:

- Calls completed
- Calls per day
- Average handling time
- Total talk time
- Follow-up completion rate
- Evaluation score
- Success rate
- Campaign productivity

## Campaign KPIs

Examples include:

- Total customers
- Processed customers
- Pending customers
- Completed calls
- Follow-up customers
- Evaluation results
- Agent productivity
- Campaign progress

---

# Role-Based Access Control

The platform uses role-based authorization to control access to different areas of the system.

### Administrator

Can manage:

- Campaigns
- Batches
- Evaluation forms
- Validation rules
- Scoring rules
- Users
- Agents
- System configuration
- Reports

### Supervisor

Can manage and monitor:

- Campaigns
- Agents
- Queues
- Evaluations
- Performance
- Operational analytics

### Agent

Can:

- Request the next lead
- Process assigned customers
- Record call results
- Add notes
- Schedule callbacks
- Complete evaluations
- View relevant personal performance metrics

---

# Customer Lifecycle

The complete operational workflow can be represented as:

```text
Customer Import
       │
       ▼
Campaign / Batch
       │
       ▼
Smart Queue
       │
       ▼
Agent Assignment
       │
       ▼
Customer Call
       │
       ├── Completed
       ├── No Answer
       ├── Busy
       ├── Callback
       ├── Wrong Number
       └── Rejected
       │
       ▼
Evaluation
       │
       ▼
Validation
       │
       ▼
Score Calculation
       │
       ▼
Agent KPI
       │
       ▼
Analytics & Reporting
```

### Follow-Up Lifecycle

```text
Customer Call
      │
      ▼
Callback Required
      │
      ▼
Follow-Up Queue
      │
      ▼
Next Eligible Agent
      │
      ▼
Customer Reassigned
      │
      ▼
New Interaction
```

---

# System Architecture

```text
                         ┌─────────────────────┐
                         │      Frontend       │
                         │   React / Vite      │
                         │ Tailwind / Shadcn   │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │       REST API      │
                         │    ASP.NET Core     │
                         └──────────┬──────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
              ▼                     ▼                     ▼
       Campaign Engine       Queue Engine        Evaluation Engine
              │                     │                     │
              └─────────────────────┼─────────────────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │      Data Layer     │
                         │   Entity Framework  │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │     SQL Server      │
                         └─────────────────────┘
```

---

# Technology Stack

## Backend

- ASP.NET Core Web API
- Entity Framework Core
- SQL Server
- REST APIs
- Role-Based Authorization

## Frontend

- React
- Vite
- TailwindCSS
- Shadcn/UI

## Infrastructure

- Docker
- Nginx
- Ubuntu / Linux VPS

---

# Key Design Principles

### Configurable Instead of Hard-Coded

Campaigns, forms, validations, and scoring rules are designed to be configurable instead of being tightly coupled to application code.

### Centralized Queue Management

Lead assignment is controlled by a centralized queue engine instead of manual distribution.

### Campaign Isolation

Each campaign can have its own customers, batches, agents, forms, rules, and workflow configuration.

### Automated Evaluation

Evaluation answers are validated and scored automatically based on configurable rules.

### Operational Observability

Agent and campaign activity is continuously tracked to generate measurable KPIs.

### Scalable Workflow

The architecture is designed to support additional campaigns, departments, evaluation workflows, and operational processes.

---

# Problems Solved

The platform addresses common problems found in Excel-driven operational environments:

- Manual customer distribution
- Duplicate assignments
- Uncontrolled customer lists
- Manual callback management
- Manual evaluation scoring
- Inconsistent evaluation processes
- Limited agent performance visibility
- Difficult campaign management
- Fragmented reporting
- Lack of centralized operational history

By centralizing these processes, the platform provides a more controlled, measurable, and scalable operational workflow.

---

# Future Improvements

Potential future extensions include:

- Real-time notifications
- Advanced campaign automation
- SLA monitoring
- Call recording integration
- AI-assisted call evaluation
- AI-powered quality analysis
- Advanced analytics dashboards
- Automated anomaly detection
- Multi-department workflows
- Advanced audit trails
- Real-time agent monitoring

---

# Project Status

🚧 **Currently Under Active Development**

The platform is continuously evolving with additional campaign management, automation, evaluation, analytics, and operational intelligence capabilities.

---

# Author

**Abd El Rahman Elsaeedy**

Backend Developer

[GitHub](https://github.com/abdelra7manelsaeedy)
