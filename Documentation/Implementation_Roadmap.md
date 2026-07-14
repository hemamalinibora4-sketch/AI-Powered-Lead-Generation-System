# Implementation Roadmap – 4 Hour Development Plan

## Overview

This roadmap defines the step-by-step implementation process for developing the **AI-Powered Lead Generation System** in Salesforce. The project is divided into multiple phases covering organization setup, Lead customization, automation, AI integration, testing, documentation, and final submission.

Each phase should be marked as completed after successful implementation in the Salesforce org, with supporting screenshots stored in the corresponding `Screenshots/` folder.

---

# Development Phases

| **Phase**                          | **Time** | **Activities**                                                           | **Status** |
| ---------------------------------- | -------- | ------------------------------------------------------------------------ | ---------- |
| Phase 1: Org Setup                 | 15 min   | Create Salesforce Developer Org, enable Agentforce and Flow              | ⬜          |
| Phase 2: Lead Customization        | 30 min   | Create custom fields, validation rules, and update Lead page layouts     | ⬜          |
| Phase 3: Lightning App & Tabs      | 20 min   | Build Lead Generation App, add Leads tab, and configure navigation       | ⬜          |
| Phase 4: Security Model            | 30 min   | Create profiles, roles, and test users                                   | ⬜          |
| Phase 5: Automation (Flow)         | 45 min   | Design and activate Record-Triggered Flow with scoring logic             | ⬜          |
| Phase 6: AI Integration            | 45 min   | Configure Prompt Builder, connect Agentforce, and map AI Summary field   | ⬜          |
| Phase 7: Testing                   | 30 min   | Create sample leads, verify scoring, and validate AI output              | ⬜          |
| Phase 8: GitHub & Documentation    | 45 min   | Initialize repository, commit changes, prepare README and project report | ⬜          |
| Phase 9: Final Review & Submission | 20 min   | Verify checklist, organize artifacts, and submit project                 | ⬜          |

---

# Phase Completion Guidelines

After completing each phase:

* Update the status from ⬜ to ✅.
* Add implementation screenshots to the relevant folder.
* Commit changes with a meaningful Git message.
* Maintain a clean incremental development history.

---

# Prerequisites

Before starting the implementation, ensure the following requirements are available:

## Salesforce Requirements

* Valid Salesforce Developer Edition account (Free)
* Basic knowledge of Salesforce Setup and Object Manager
* Permission to configure Salesforce features

---

## Development Tools

Required tools:

* GitHub account
* Git installed locally (recommended)
* Modern web browser

Recommended browsers:

* Google Chrome
* Mozilla Firefox

---

# Salesforce Features to Enable

## Agentforce (Einstein GPT)

Required for:

* AI-powered lead summaries
* Natural-language generation
* Prompt Builder integration

---

## Salesforce Flow

Used for:

* Record-triggered automation
* Lead score calculation
* AI prompt invocation

No additional license is required for standard Flow functionality.

---

## Prompt Builder

Required for:

* Creating AI prompt templates
* Mapping Lead fields
* Generating AI summaries

Ensure the required permissions are enabled.

---

# Suggested Git Commit Workflow

## Phase 2: Lead Customization

Changes:

* Custom Lead fields
* Validation rules
* Page layout updates
* Screenshots

Commands:

```bash id="r4h9p2"
git add Data-Model/ Screenshots/02_Lead_Customization/

git commit -m "Phase 2: add custom Lead fields and validation rules"
```

---

## Phase 4: Security Model

Changes:

* Role hierarchy
* Profiles
* Test users
* Security documentation

Commands:

```bash id="w6k3n8"
git add Security/ Screenshots/04_Security_Model/

git commit -m "Phase 4: add role hierarchy, profiles, and test users"
```

---

## Phase 5: Automation Flow

Changes:

* Record-Triggered Flow
* Lead scoring logic
* Flow screenshots

Commands:

```bash id="m2x7q5"
git add Automation/ Screenshots/05_Automation_Flow/

git commit -m "Phase 5: build and activate lead scoring flow"
```

---

## Phase 6: AI Integration

Changes:

* Prompt Builder configuration
* Agentforce integration
* AI Summary setup

Commands:

```bash id="p8v4s1"
git add AI-Integration/ Screenshots/06_AI_Integration/

git commit -m "Phase 6: configure Prompt Builder and AI Summary field"
```

---

## Phase 7: Testing

Changes:

* Test cases
* Test results
* Validation screenshots

Commands:

```bash id="z5c9k7"
git add Testing/ Screenshots/07_Testing/

git commit -m "Phase 7: complete end-to-end testing results"
```

---

# Related Documentation

* Architecture: `Architecture.md`
* Lead Customization: `../Data-Model/Lead_Custom_Fields.md`
* Automation Flow: `../Automation/Lead_Scoring_Flow.md`
* AI Integration: `../AI-Integration/Prompt_Template.md`
