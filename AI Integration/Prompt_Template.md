AI Integration — Prompt Builder & AI Summary
Overview
Agentforce (Einstein GPT) is used via a Prompt Template to turn raw Lead data into a natural-language summary that helps sales reps prioritize outreach.

Prompt Template Config
Template Type: Field Generation
Object: Lead
Target Field: AI_Summary__c
Model: Agentforce default (Einstein GPT)
Status: Active
Prompt Inputs (mapped from the Lead record)
Company
Industry_Type__c
Engagement_Level__c
Lead_Score__c
Lead Source
Example Prompt Instruction (paraphrased, not the literal template text)
"Summarize this lead in 2–3 sentences, noting its industry, engagement level, and score, and recommend a next action for the sales rep."

Setup Steps
Enable Agentforce/Einstein GPT for the org (Setup → Einstein Setup)
Setup → Prompt Builder → New Prompt Template → Field Generation
Select Lead as the object, AI_Summary__c as the target field
Add the input fields listed above as merge fields in the prompt
Write and test the prompt instructions in the Prompt Builder preview panel
Activate the template
Reference the template from the Record-Triggered Flow (see ../Automation/Lead_Scoring_Flow.md)
Screenshots for this phase: ../Screenshots/06_AI_Integration/
