# 4.1 Test Users & Access Verification

### Objective

Create test users to simulate a real-world sales team and verify that the configured role hierarchy and custom profiles enforce the intended record access and permissions.

### Create Test Users

Navigate to **Setup → Users** and create the following users:

| Full Name    | Username                                                    | Profile               | Role                 |
| ------------ | ----------------------------------------------------------- | --------------------- | -------------------- |
| Jane Manager | [jane.manager@example.com](mailto:jane.manager@example.com) | Sales Manager Profile | Sales Manager        |
| John Rep     | [john.rep@example.com](mailto:john.rep@example.com)         | Sales Rep Profile     | Sales Representative |

Assign each user the corresponding **Profile** and **Role**, then save the user records.

### Access Verification

Verify the security model by logging in as each test user and performing the following checks:

**John Rep (Sales Representative)**

* Log in as **John Rep**.
* Confirm that he can create, view, and edit only the Lead records he owns.
* Attempt to delete a Lead record and verify that the action is blocked due to profile permissions.
* Confirm that access to reports is limited.

**Jane Manager (Sales Manager)**

* Log in as **Jane Manager**.
* Confirm that she can view all Lead records owned by users below her in the role hierarchy.
* Verify that she can access dashboards and reports.
* Confirm that she can approve or delete records according to her assigned permissions.

### Expected Results

* Sales Representatives can access only their own Lead records and cannot perform restricted actions such as deleting records.
* Sales Managers can access Lead records owned by subordinate users, view dashboards and reports, and perform management-level actions permitted by their profile.

### Screenshots

Store the screenshots for this phase in:

`../Screenshots/04_Security_Model/`

Suggested screenshot sequence:

1. Test User Creation
2. John Rep Login and Lead Access
3. John Rep Permission Restriction (Delete Blocked)
4. Jane Manager Login
5. Jane Manager Viewing Team Leads
6. Jane Manager Dashboard and Reports Access
