# Lead Object – Custom Fields & Validation Rules

## Overview

The standard **Salesforce Lead object** is extended with custom fields to support AI-powered lead scoring, qualification, and summary generation. These fields store the lead score calculated by automation, AI-generated insights, industry information, and customer engagement level.

The customizations improve lead visibility and help sales representatives prioritize high-quality prospects.

---

# Custom Field Configuration

| **API Name**          | **Label**        | **Data Type**  | **Details**                                                                                         |
| --------------------- | ---------------- | -------------- | --------------------------------------------------------------------------------------------------- |
| `Lead_Score__c`       | Lead Score       | Number (0–100) | Calculated automatically by the Record-Triggered Flow. Higher scores indicate better-quality leads. |
| `AI_Summary__c`       | AI Summary       | Long Text Area | AI-generated natural-language summary of the lead created using Agentforce (Einstein GPT).          |
| `Industry_Type__c`    | Industry Type    | Picklist       | Represents the lead's industry category.                                                            |
| `Engagement_Level__c` | Engagement Level | Picklist       | Indicates the lead's engagement level: High, Medium, or Low.                                        |

---

# Picklist Values

## Industry Type

Available values:

* Technology
* Healthcare
* Finance
* Retail
* Education
* Other

---

## Engagement Level

Available values:

* High
* Medium
* Low

---

# Validation Rules

Validation rules ensure that Lead records contain valid and complete information before saving.

| **Rule Name**           | **Purpose**                                                                                             | **Error Behavior**                                                         |
| ----------------------- | ------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `Reject_Personal_Email` | Prevents the use of personal email domains such as Gmail, Yahoo, Hotmail, and Outlook for Lead records. | Save is blocked with an inline error message displayed on the Email field. |
| `Required_Company`      | Ensures that the Company field is populated before saving a Lead record.                                | Save is blocked until the Company field contains a value.                  |

---

# Page Layout Changes

The following custom fields are added to the **Lead page layout**:

* `Lead_Score__c`
* `AI_Summary__c`
* `Industry_Type__c`
* `Engagement_Level__c`

A new section named:

```text id="k29x2a"
AI Insights
```

is created near the top of the Lead record page to provide quick visibility of AI-generated information and lead qualification details.

---

# Field-Level Security

Field permissions are configured to ensure proper access control.

| **Profile**          | **Access**                                      |
| -------------------- | ----------------------------------------------- |
| Sales Representative | Read/Edit access based on business requirements |
| Sales Manager        | Read/Edit access based on business requirements |

---

# Setup Steps

## Step 1: Create Custom Fields

Navigate to:

```text id="q8m7u2"
Setup → Object Manager → Lead → Fields & Relationships → New
```

Create each custom field with the specified:

* Field Name
* Data Type
* Picklist Values
* Field Description

---

## Step 2: Configure Field-Level Security

Set permissions for:

* Sales Representative profile
* Sales Manager profile

Ensure users have appropriate read/edit access.

---

## Step 3: Update Lead Page Layout

Navigate to:

```text id="7a2v0n"
Setup → Object Manager → Lead → Page Layouts
```

Perform the following:

* Add custom fields to the Lead page layout.
* Create a new **AI Insights** section.
* Place AI-related fields near the top of the record page.

---

## Step 4: Create Validation Rules

Navigate to:

```text id="x5f3p9"
Setup → Object Manager → Lead → Validation Rules → New
```

Create:

* `Reject_Personal_Email`
* `Required_Company`

Configure the validation formulas and error messages.

---

# Expected Result

After completing the customization:

* Lead records contain AI-related fields.
* Lead scores are automatically stored.
* AI-generated summaries are displayed on Lead records.
* Invalid email domains are blocked.
* Company information is mandatory.
* Sales teams can quickly view lead insights.

---

# Related Components

* **Automation:** `../Automation/Lead_Scoring_Flow.md`
* **AI Integration:** `../AI-Integration/Prompt_Template.md`

---

# Screenshots

Store all screenshots related to this implementation in:

```text id="wq9m51"
../Screenshots/02_Lead_Customization/
```
