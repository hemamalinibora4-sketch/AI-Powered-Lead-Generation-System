# 7. Test Plan & Results

### Objective

Verify that the Lead Management System functions correctly by testing validation rules, lead scoring, AI summary generation, and role-based security.

### QA Strategy

| Test Type          | What it Verifies                                                                                                                                |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Unit Testing       | Manually create Lead records with different inputs to verify Lead Scoring logic.                                                                |
| Validation Testing | Attempt to save invalid records (such as empty or personal email addresses) and confirm that validation error messages are displayed.           |
| AI Testing         | Create Lead records with different industries and engagement levels to verify that **AI_Summary__c** generates relevant and readable summaries. |
| Security Testing   | Log in as **Sales Representative** and **Sales Manager** users to verify role-based record visibility and profile permissions.                  |

### Test Cases

| # | Test Case                       | Steps                                                                         | Expected Result                                                                     | Actual Result | Status |
| - | ------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | ------------- | ------ |
| 1 | Create Lead with Valid Email    | Create a Lead using a valid company email address.                            | Lead record is saved successfully.                                                  |               | ⬜      |
| 2 | Create Lead with Personal Email | Enter a Gmail, Yahoo, Hotmail, or Outlook email address and save.             | Validation rule prevents the record from being saved and displays an error message. |               | ⬜      |
| 3 | Lead Scoring – High Engagement  | Create a Lead with **Engagement Level = High** and **Industry = Technology**. | **Lead_Score__c** is calculated using the highest weighting.                        |               | ⬜      |
| 4 | Lead Scoring – Low Engagement   | Create a Lead with **Engagement Level = Low** and **Industry = Other**.       | **Lead_Score__c** is calculated using the lowest weighting.                         |               | ⬜      |
| 5 | AI Summary Generation           | Create and save a Lead with all required fields completed.                    | **AI_Summary__c** is automatically populated with a relevant and readable summary.  |               | ⬜      |
| 6 | Sales Representative Access     | Log in as **John Rep** and access Lead records.                               | User can create, view, and edit only their own Leads.                               |               | ⬜      |
| 7 | Sales Manager Access            | Log in as **Jane Manager** and access Lead records.                           | User can view subordinate Leads and access dashboards and reports.                  |               | ⬜      |

### Test Execution

Execute each test case in the Salesforce org and record the outcome.

* Update the **Actual Result** column with the observed behavior.
* Change the **Status** column to **✅ Pass** or **❌ Fail** after each test.
* Capture a screenshot for every completed test case.

### Minimum Submission Requirements

Ensure the following scenarios are successfully completed before submission:

* Create and verify **at least three Lead records**.
* Successfully save one Lead with a valid company email.
* Verify one validation failure using an invalid or personal email address.
* Confirm one successful AI-generated Lead summary.
* Validate Lead Scoring calculations.
* Verify role-based access for both **Sales Representative** and **Sales Manager** users.

### Screenshots

Store all screenshots for this phase in:

`../Screenshots/07_Testing/`

Suggested screenshot sequence:

1. Valid Lead Creation
2. Validation Rule Error
3. High Engagement Lead Score
4. Low Engagement Lead Score
5. AI Summary Generation
6. Sales Representative Access Verification
7. Sales Manager Access Verification
