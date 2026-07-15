# 4. Security Model – Profiles & Roles

### Objective

Implement a role hierarchy and custom profiles to control access to Lead records based on user responsibilities.

### Role Hierarchy

Navigate to **Setup → Roles** and create the following hierarchy:

```
Sales Director
    └── Sales Manager
            └── Sales Representative
```

**Steps:**

1. Go to **Setup → Roles**.
2. Click **Set Up Roles**.
3. Create the **Sales Director** role as the top-level role.
4. Under **Sales Director**, create the **Sales Manager** role.
5. Under **Sales Manager**, create the **Sales Representative** role.
6. Save the role hierarchy.

### Create Custom Profiles

Navigate to **Setup → Profiles** and clone the **Standard User** profile twice.

* Clone **Standard User** and rename it **Sales Rep Profile**.
* Clone **Standard User** again and rename it **Sales Manager Profile**.

### Configure Profile Permissions

**Sales Rep Profile**

* Lead Object Permissions:

  * Read ✓
  * Create ✓
  * Edit ✓
  * Delete ✗
  * View All ✗
  * Modify All ✗
* Provide access only to the required Lead fields.
* Allow limited access to reports.

**Sales Manager Profile**

* Lead Object Permissions:

  * Read ✓
  * Create ✓
  * Edit ✓
  * Delete ✓
  * View All ✓
  * Modify All (if required)
* Grant access to dashboards and reports.
* Enable record approval and deletion capabilities.

### Create Users and Assign Roles

Navigate to **Setup → Users** and create users with the appropriate profile and role assignments.

| User                 | Profile                           | Role                 |
| -------------------- | --------------------------------- | -------------------- |
| Sales Director       | Standard User (or Custom Profile) | Sales Director       |
| Sales Manager        | Sales Manager Profile             | Sales Manager        |
| Sales Representative | Sales Rep Profile                 | Sales Representative |

### Access Verification

Verify the security model by logging in as different users:

* **Sales Representative:** Can create, view, and edit only their own Lead records with limited reporting access.
* **Sales Manager:** Can view Lead records owned by users below them in the role hierarchy, access dashboards and reports, and approve or delete records as permitted.
* **Sales Director:** Has visibility into records owned by all users beneath them in the role hierarchy.

### Screenshots

Store the screenshots for this phase in:

`../Screenshots/04_Security_Model/`

Suggested screenshot sequence:

1. Role Hierarchy
2. Sales Rep Profile
3. Sales Manager Profile
4. Sales Rep Permissions
5. Sales Manager Permissions
6. User Creation
7. Record Access Verification
