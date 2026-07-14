# Lead Scoring Flow – Record-Triggered Automation

## Overview

The **Lead Scoring Flow** is a Salesforce **Record-Triggered Flow** that automatically evaluates Lead records and assigns a score based on predefined business criteria. The flow analyzes lead information such as industry type, engagement level, company details, and lead source to calculate the overall lead score.

After calculating the score, the flow invokes the **Agentforce (Einstein GPT) Prompt Template** to generate an AI-powered lead summary and stores the generated response in the **`AI_Summary__c`** field.

---

## Flow Configuration

| **Setting**          | **Value**                                    |
| -------------------- | -------------------------------------------- |
| **Flow Type**        | Record-Triggered Flow                        |
| **Object**           | Lead                                         |
| **Trigger Event**    | When a record is created or updated          |
| **Automation Tool**  | Salesforce Flow Builder                      |
| **Score Field**      | `Lead_Score__c`                              |
| **AI Summary Field** | `AI_Summary__c`                              |
| **AI Integration**   | Agentforce (Einstein GPT) via Prompt Builder |

---

## Trigger Conditions

The flow executes when:

* A new Lead record is created.
* An existing Lead record is updated.

---

## Lead Scoring Logic

The flow evaluates the following Lead fields:

* `Industry_Type__c`
* Company
* Lead Source
* `Engagement_Level__c`

The scoring rules assign points based on lead quality factors.

---

## Scoring Criteria

| **Factor**       | **Condition**          | **Points** |
| ---------------- | ---------------------- | ---------- |
| Engagement Level | High                   | +40        |
| Engagement Level | Medium                 | +20        |
| Engagement Level | Low                    | +5         |
| Industry Type    | Technology or Finance  | +20        |
| Industry Type    | Other Industries       | +5         |
| Company          | Company name populated | +10        |
| Lead Source      | Web / Referral         | +15        |

---

## Score Calculation

* The flow adds all applicable points.
* The final score is stored in the **`Lead_Score__c`** field.
* The maximum score is restricted to **100**.

Example:

```text
Lead Score = Engagement Points + Industry Points + Company Points + Lead Source Points

Maximum Score = 100
```

---

## AI Summary Generation

After calculating the Lead Score:

1. The flow calls the **Prompt Template** from Agentforce (Einstein GPT).
2. Lead information is passed as input:

   * Company
   * `Industry_Type__c`
   * `Engagement_Level__c`
   * `Lead_Score__c`
   * Lead Source
3. Agentforce generates a natural-language lead summary.
4. The generated response is stored in the **`AI_Summary__c`** field.

Related document:

```text
../AI-Integration/Prompt_Template.md
```

---

## Flow Builder Implementation Steps

### Step 1: Create Record-Triggered Flow

Navigate to:

```text
Setup → Flows → New Flow → Record-Triggered Flow
```

Configure:

* Object: **Lead**
* Trigger: **A record is created or updated**

---

### Step 2: Add Scoring Logic

Create:

* Decision elements
* Formula resources
* Assignment elements

to evaluate:

* Engagement Level
* Industry Type
* Company
* Lead Source

---

### Step 3: Update Lead Score

Add an:

**Update Records** element

Purpose:

* Store the calculated score in:

```text
Lead_Score__c
```

---

### Step 4: Invoke AI Prompt Template

Add an:

**Action** element

Purpose:

* Call the Agentforce Prompt Template.
* Map Lead fields as prompt inputs.
* Generate AI-based lead summary.

---

### Step 5: Update AI Summary

Add another:

**Update Records** element

Purpose:

Store the generated AI response in:

```text
AI_Summary__c
```

---

### Step 6: Activate Flow

After testing:

* Validate the flow.
* Save the flow.
* Activate it.

---

## Expected Result

When a Lead is created or updated:

1. Salesforce automatically evaluates the Lead details.
2. A score is calculated and stored in `Lead_Score__c`.
3. Agentforce generates an AI summary.
4. The summary is saved in `AI_Summary__c`.
5. Sales representatives can quickly prioritize high-value leads.

---

## Benefits

* Automates lead qualification.
* Reduces manual scoring effort.
* Helps sales teams prioritize prospects.
* Provides AI-generated insights.
* Improves sales follow-up efficiency.

---

## Related Components

* **AI Integration:** `../AI-Integration/Prompt_Template.md`
* **Lead Fields:** `../Data-Model/Lead_Custom_Fields.md`

---

## Screenshots

Store all screenshots related to this implementation in:

```text
../Screenshots/05_Automation_Flow/
```

