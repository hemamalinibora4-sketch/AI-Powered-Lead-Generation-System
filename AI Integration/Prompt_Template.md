# AI Integration – Prompt Builder & AI Summary

## Overview

This project uses **Agentforce (Einstein GPT)** with **Prompt Builder** to automatically generate AI-powered summaries for Lead records. The generated summary is stored in the custom field **`AI_Summary__c`** and provides sales representatives with a concise overview of each lead, including lead quality and the recommended next action.

---

## Prompt Template Configuration

| **Setting**       | **Value**                                 |
| ----------------- | ----------------------------------------- |
| **Template Type** | Field Generation                          |
| **Object**        | Lead                                      |
| **Target Field**  | `AI_Summary__c`                           |
| **AI Model**      | Agentforce (Einstein GPT) – Default Model |
| **Status**        | Active                                    |

---

## Prompt Inputs

The following Lead fields are used as inputs to generate the AI summary:

* Company
* `Industry_Type__c`
* `Engagement_Level__c`
* `Lead_Score__c`
* Lead Source

---

## Example Prompt Instruction

> Summarize this lead in 2–3 sentences, highlighting the company's industry, engagement level, and lead score. Recommend the most appropriate next action for the sales representative.

---

## Setup Steps

1. Enable **Agentforce (Einstein GPT)** in Salesforce.
2. Navigate to **Setup → Einstein Setup** and complete the required configuration.
3. Open **Setup → Prompt Builder**.
4. Click **New Prompt Template**.
5. Select **Field Generation** as the template type.
6. Choose **Lead** as the object.
7. Select **`AI_Summary__c`** as the target field.
8. Add the required Lead fields as merge fields:

   * Company
   * `Industry_Type__c`
   * `Engagement_Level__c`
   * `Lead_Score__c`
   * Lead Source
9. Write the prompt instructions.
10. Test the prompt using the **Preview** panel.
11. Activate the Prompt Template.
12. Reference the Prompt Template from the **Record-Triggered Flow** (`../Automation/Lead_Scoring_Flow.md`).

---

## Expected Output

After a Lead record is created or updated, the Prompt Template generates an AI summary similar to the following:

> **ABC Technologies** operates in the IT Services industry and currently has a high engagement level with a lead score of 92. This prospect shows strong purchase intent and should be contacted promptly by the assigned sales representative.

---

## Benefits

* Automatically generates meaningful lead summaries.
* Saves time for sales representatives.
* Improves lead prioritization.
* Provides consistent AI-generated recommendations.
* Enhances sales productivity using Agentforce (Einstein GPT).

---

## Related Components

* **Automation:** `../Automation/Lead_Scoring_Flow.md`
* **Lead Fields:** `../Data-Model/Lead_Custom_Fields.md`

---

## Screenshots

Store all screenshots related to this implementation in:

```text
../Screenshots/06_AI_Integration/
```

