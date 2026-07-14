# System Architecture – AI-Powered Lead Generation System

## Overview

The **AI-Powered Lead Generation System** is built on the Salesforce platform and combines Salesforce native automation with Agentforce (Einstein GPT) to automate lead scoring, qualification, and AI-generated lead summaries.

The architecture consists of Salesforce configuration components, automation workflows, AI integration, and security controls that work together to help sales representatives identify and prioritize high-value leads.

---

# Platform Components

| **Component**                 | **Purpose**                                                                                                        |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Salesforce Developer Org**  | Development environment where all configurations, customizations, automation, and AI integrations are implemented. |
| **Object Manager**            | Used to customize the standard Lead object by creating custom fields, validation rules, and page layout changes.   |
| **Lightning App Builder**     | Used to create and customize the **Lead Generation App** user interface.                                           |
| **Flow Builder**              | Used to create the Record-Triggered Flow for automated lead scoring and AI summary generation.                     |
| **Prompt Builder**            | Used to design and configure AI prompts that are sent to Agentforce.                                               |
| **Agentforce (Einstein GPT)** | Generates natural-language lead summaries and provides AI-powered insights for sales representatives.              |

---

# Data Flow

## Step 1: Lead Creation or Update

A Lead record is created or updated through:

* Manual entry
* Web forms
* Data import

---

## Step 2: Record-Triggered Flow Execution

The Salesforce **Record-Triggered Flow** automatically starts when the Lead record is created or updated.

The Flow evaluates the following fields:

* `Industry_Type__c`
* Company
* Lead Source
* `Engagement_Level__c`

---

## Step 3: Lead Score Calculation

The Flow applies predefined scoring rules and calculates the lead score.

The calculated value is stored in:

```text id="q1s7e4"
Lead_Score__c
```

The score range is:

```text id="p3k8m2"
0 – 100
```

Detailed scoring logic:

```text id="z8x2c6"
../Automation/Lead_Scoring_Flow.md
```

---

## Step 4: AI Summary Generation

After calculating the score:

1. The Flow invokes the configured Prompt Template.
2. Lead information is passed to Agentforce.
3. Agentforce (Einstein GPT) generates a natural-language summary.
4. The generated summary is stored in:

```text id="r5n9v3"
AI_Summary__c
```

AI configuration details:

```text id="m2q7w8"
../AI-Integration/Prompt_Template.md
```

---

## Step 5: Sales Representative Action

The sales representative views:

* Lead Score
* AI Summary
* Lead Information

directly on the Lead record and uses these insights to prioritize customer outreach.

---

# System Diagram

```text id="f7k3a1"
Lead Created / Updated
          │
          ▼
Record-Triggered Flow
          │
          ▼
Calculate Lead Score
(Lead_Score__c)
          │
          ▼
Prompt Template
          │
          ▼
Agentforce (Einstein GPT)
          │
          ▼
Generate AI Summary
(AI_Summary__c)
          │
          ▼
Sales Representative
Views Score + Summary
and Prioritizes Outreach
```

---

# Architecture Workflow Summary

| **Stage** | **Process**                                      |
| --------- | ------------------------------------------------ |
| 1         | Lead record is created or updated                |
| 2         | Record-Triggered Flow starts automatically       |
| 3         | Lead details are evaluated                       |
| 4         | Lead score is calculated                         |
| 5         | Prompt Template sends data to Agentforce         |
| 6         | AI-generated summary is created                  |
| 7         | Summary is stored in Lead record                 |
| 8         | Sales representatives use insights for follow-up |

---

# Related Documentation

## Data Model

Field definitions and Lead object customization:

```text id="v4j9p2"
../Data-Model/Lead_Custom_Fields.md
```

---

## Automation

Lead scoring Flow logic:

```text id="n8c4r6"
../Automation/Lead_Scoring_Flow.md
```

---

## AI Integration

Prompt Builder and Agentforce configuration:

```text id="b6m1x5"
../AI-Integration/Prompt_Template.md
```

---

## Security Model

User roles and permissions:

```text id="h3k7s9"
../Security/Profiles_and_Roles.md
```
