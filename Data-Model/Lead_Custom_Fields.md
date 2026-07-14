Lead Object — Custom Fields
Extends the standard Lead object with the following fields.

API Name	Label	Type	Details
Lead_Score__c	Lead Score	Number (0–100)	Computed by the Record-Triggered Flow; higher = better quality lead
AI_Summary__c	AI Summary	Long Text Area	AI-generated natural-language summary of the lead, written by Agentforce
Industry_Type__c	Industry Type	Picklist	e.g., Technology, Healthcare, Finance, Retail, Education, Other
Engagement_Level__c	Engagement Level	Picklist	High / Medium / Low
Validation Rules
Rule Name	Enforces	Error Behavior
Reject_Personal_Email	Blocks free/personal email domains (Gmail, Yahoo, Hotmail, Outlook) from being used as the Lead's email	Save is blocked with an inline error on the Email field
Required Company	Company must be populated	Save is blocked until filled
Page Layout Changes
Added Lead_Score__c, AI_Summary__c, Industry_Type__c, Engagement_Level__c to the Lead page layout, grouped in a new "AI Insights" section near the top of the record for visibility.
Setup Steps
Setup → Object Manager → Lead → Fields & Relationships → New
Create each field above with the specified type and picklist values
Set field-level security so both Sales Rep and Sales Manager profiles can read/edit as appropriate
Add fields to the Lead page layout under a new "AI Insights" section
Setup → Object Manager → Lead → Validation Rules → New → build Reject_Personal_Email
Screenshots for this phase: ../Screenshots/02_Lead_Customization/
