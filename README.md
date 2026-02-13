# -Procurement-and-Leave-Management
A Procurement and Leave Management is a Restful API System built with Java 17 and Spring Boot 3.x, using PostgreSQL as the database. The system provides secure authentication, role-based access control, and modules for managing procurement requests and leave request.

 Technology Stack
• Backend: Java 17, Spring Boot 3.x
• Database: PostgreSQL
• Authentication: JWT (JSON Web Token)
• Build Tool: Maven
 System Modules
1. Authentication & Authorization
• Login/Logout using JWT tokens.
• Role-based access control with three roles:
• Staff – can create and manage their own procurement requests.
• Reviewer – can review /reject procurement requests.
• Approver – can review and approve/reject procurement requests.
• Admin – full access, including managing users and roles.
2. User Management
• User CRUD (Create, Read, Update, Delete (Inactive record with status ‘I’)).
• Admin create user will randomly password and send via email.
• Role assignment handled by Admin.
• Admin responsibilities:
• Manage staff and manager accounts.
• Assign or revoke roles.
• Reset user credentials will send reset password link via email with expiration 24 hours.
3. Procurement Module
• Request Creation: Staff can create procurement requests (e.g., cable, mouse, computer).
• Request Items: Each request can contain multiple items.
• Request Lifecycle:
o Draft – request saved but not submitted.
o Submitted – request sent for manager review.
o Withdrawn staff can withdraw back the application in case they change their mind.
o Reviewed – manager approves the request.
o Approved – manager approves the request.
o Rejected – manager rejects the request.
• Staff Permissions:
• Can save, update, or delete requests while in Draft or Submitted state.
• Cannot modify requests once Approved/Rejected.
• Manager Permissions:
• Review submitted requests.
• Approve or reject requests.
• Audit Trail: Track request history (created, updated, approved, rejected).
4. Leave Management Module
The Leave Module allows staff to request time off, track leave balances, and manage approvals through a
structured workflow. It supports multiple leave types and enforces role-based permissions.
Features
1. Leave Request Creation
• Staff Role can create leave requests by providing:
• Available dates (working days Monday–Friday).
• Working time (full day or half day).
• Reason for leave (e.g., personal, medical, special circumstances).
• Leave type:
o Annual Leave
o Special Leave
o Sick Leave
2. Request Lifecycle
• Draft – request saved but not submitted.
• Submitted – request sent for manager review.
• Withdraw – withdraw back application.
• Reviewed – Reviewer checking the application
• Approved – manager approves the leave.
• Rejected – manager rejects the leave.
3. Staff Permissions
• Can create, save, update, or delete (Inactive record to status ‘I’) leave requests while in Draft or
Submitted status.
• cannot modify requests once Approved/Rejected.
4. Manager Permissions
• Review submitted leave requests.
• Approve or reject requests.
• Provide feedback or comments on decisions.
5. Admin Permissions
• Full visibility of all leave requests.
• Manage leave policies (e.g., maximum annual leave days).
• Override approvals if necessary.
Additional Enhancements
• Leave Balance Tracking: Each staff member has a leave quota (annual leave days, sick leave
allowance, etc.).
• Validation Rules:
o Requests cannot overlap with existing approved leave.
o Requests must fall within working days (Mon–Fri).
o Leave type must be valid and within quota.
• Audit Trail: Track request history (created, updated, approved, rejected).
5. A React UI will be provided later, after the completion of the RESTful API.