# QA Checklist — AI-Powered IT Helpdesk Ticketing System

## 1. User Panel: Tickets

| ID | Summary | Status | Type |
|---|---|---|---|
| UP-TKT-001 | Opening the “Create Ticket” page | ⬜ Not Run | Functional |
| UP-TKT-002 | Displaying the ticket category dropdown | ⬜ Not Run | UI |
| UP-TKT-003 | Selecting a ticket category | ⬜ Not Run | Functional |
| UP-TKT-004 | Entering ticket title | ⬜ Not Run | Functional |
| UP-TKT-005 | Entering ticket description | ⬜ Not Run | Functional |
| UP-TKT-006 | Selecting ticket priority | ⬜ Not Run | Functional |
| UP-TKT-007 | Submitting a ticket with all required fields filled in | ⬜ Not Run | Functional |
| UP-TKT-008 | Showing ticket creation confirmation message | ⬜ Not Run | Functional |
| UP-TKT-009 | Generating a unique ticket ID after ticket submission | ⬜ Not Run | Functional |
| UP-TKT-010 | Showing validation when category is missing | ⬜ Not Run | Validation |
| UP-TKT-011 | Showing validation when title is missing | ⬜ Not Run | Validation |
| UP-TKT-012 | Showing validation when description is missing | ⬜ Not Run | Validation |
| UP-TKT-013 | Showing validation when priority is missing | ⬜ Not Run | Validation |
| UP-TKT-014 | Submitting ticket with long description | ⬜ Not Run | Edge Case |
| UP-TKT-015 | Submitting ticket with special characters in title and description | ⬜ Not Run | Edge Case |
| UP-TKT-016 | Preventing duplicate ticket submission when Submit is clicked multiple times | ⬜ Not Run | Edge Case |
| UP-TKT-017 | Displaying AI/KB solution for safe user issue | ⬜ Not Run | Integration |
| UP-TKT-018 | Hiding AI/KB solution for MFA reset ticket | ⬜ Not Run | Security |
| UP-TKT-019 | Hiding AI/KB solution for password reset ticket | ⬜ Not Run | Security |
| UP-TKT-020 | Showing safe escalation message for admin-only ticket | ⬜ Not Run | Functional |

## 2. User Panel: My Tickets

| ID | Summary | Status | Type |
|---|---|---|---|
| UP-MT-001 | Opening the “My Tickets” page | ⬜ Not Run | Functional |
| UP-MT-002 | Displaying only tickets created by the logged-in user | ⬜ Not Run | Security |
| UP-MT-003 | Displaying ticket ID in My Tickets list | ⬜ Not Run | UI |
| UP-MT-004 | Displaying ticket title or description in My Tickets list | ⬜ Not Run | UI |
| UP-MT-005 | Displaying ticket category in My Tickets list | ⬜ Not Run | UI |
| UP-MT-006 | Displaying ticket priority in My Tickets list | ⬜ Not Run | UI |
| UP-MT-007 | Displaying current ticket status in My Tickets list | ⬜ Not Run | UI |
| UP-MT-008 | Opening ticket details from My Tickets list | ⬜ Not Run | Functional |
| UP-MT-009 | Displaying ticket comment history | ⬜ Not Run | Functional |
| UP-MT-010 | Adding a user comment to own ticket | ⬜ Not Run | Functional |
| UP-MT-011 | Showing comment author and timestamp | ⬜ Not Run | UI |
| UP-MT-012 | Displaying comments in correct order | ⬜ Not Run | Functional |
| UP-MT-013 | Preventing user from accessing another user’s ticket | ⬜ Not Run | Security |
| UP-MT-014 | Clicking Alert button when suggested solution does not work | ⬜ Not Run | Functional |
| UP-MT-015 | Adding alert update to ticket history | ⬜ Not Run | Integration |
| UP-MT-016 | Preventing Alert action on solved ticket | ⬜ Not Run | Validation |
| UP-MT-017 | Showing updated ticket status after technician/admin change | ⬜ Not Run | Integration |
| UP-MT-018 | Refreshing My Tickets list after new ticket creation | ⬜ Not Run | Functional |

## 3. Admin Panel: General Checks

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-GEN-001 | Admin login redirects to Admin Panel | ⬜ Not Run | Functional |
| AP-GEN-002 | Non-admin user cannot access Admin Panel URL | ⬜ Not Run | Security |
| AP-GEN-003 | Helpdesk logo displays in left sidebar | ⬜ Not Run | UI |
| AP-GEN-004 | “Agent Console” label displays under Helpdesk title | ⬜ Not Run | UI |
| AP-GEN-005 | “Version 2.0” text displays in sidebar | ⬜ Not Run | UI |
| AP-GEN-006 | Logged-in admin name displays in sidebar | ⬜ Not Run | UI |
| AP-GEN-007 | Logout button works from Admin Panel | ⬜ Not Run | Functional |
| AP-GEN-008 | Admin session expires and redirects to login | ⬜ Not Run | Security |
| AP-GEN-009 | Admin Panel layout displays correctly in Google Chrome | ⬜ Not Run | Compatibility |
| AP-GEN-010 | Admin Panel layout displays correctly in Firefox | ⬜ Not Run | Compatibility |

## 4. Admin Panel: Sidebar Navigation

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-NAV-001 | Opening “Ongoing Tickets” from sidebar | ⬜ Not Run | Functional |
| AP-NAV-002 | Opening “Escalated” from sidebar | ⬜ Not Run | Functional |
| AP-NAV-003 | Opening “Solved” from sidebar | ⬜ Not Run | Functional |
| AP-NAV-004 | Opening “Admin Playbook” from sidebar | ⬜ Not Run | Functional |
| AP-NAV-005 | Opening “Users” from sidebar | ⬜ Not Run | Functional |
| AP-NAV-006 | Highlighting selected sidebar menu item | ⬜ Not Run | UI |
| AP-NAV-007 | Sidebar icons display correctly | ⬜ Not Run | UI |

## 5. Admin Panel: Ongoing Tickets Page

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-OT-001 | Opening the “Ongoing Tickets” page | ⬜ Not Run | Functional |
| AP-OT-002 | Displaying page title “Ongoing Tickets” | ⬜ Not Run | UI |
| AP-OT-003 | Displaying page subtitle below title | ⬜ Not Run | UI |
| AP-OT-004 | Displaying Ongoing count card | ⬜ Not Run | UI |
| AP-OT-005 | Displaying Escalated count card | ⬜ Not Run | UI |
| AP-OT-006 | Displaying Solved count card | ⬜ Not Run | UI |
| AP-OT-007 | Count cards show correct ticket totals | ⬜ Not Run | Functional |
| AP-OT-008 | Notifications button displays in header | ⬜ Not Run | UI |
| AP-OT-009 | Notification count badge displays correct unread count | ⬜ Not Run | Functional |
| AP-OT-010 | Refresh button reloads ticket data | ⬜ Not Run | Functional |
| AP-OT-011 | “+ New Ticket” button opens ticket form | ⬜ Not Run | Functional |

## 6. Admin Panel: Ticket Search and Filters

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-FLT-001 | Search field displays above ticket table | ⬜ Not Run | UI |
| AP-FLT-002 | Searching ticket by ticket ID | ⬜ Not Run | Functional |
| AP-FLT-003 | Searching ticket by user name | ⬜ Not Run | Functional |
| AP-FLT-004 | Searching ticket by description | ⬜ Not Run | Functional |
| AP-FLT-005 | Clearing search restores full ticket list | ⬜ Not Run | Functional |
| AP-FLT-006 | Priority filter displays all priority options | ⬜ Not Run | UI |
| AP-FLT-007 | Filtering tickets by priority | ⬜ Not Run | Functional |
| AP-FLT-008 | Category filter displays all category options | ⬜ Not Run | UI |
| AP-FLT-009 | Filtering tickets by category | ⬜ Not Run | Functional |
| AP-FLT-010 | Assignment filter displays all assignment options | ⬜ Not Run | UI |
| AP-FLT-011 | Filtering tickets by assignment status | ⬜ Not Run | Functional |
| AP-FLT-012 | Ongoing status chip displays as active | ⬜ Not Run | UI |

## 7. Admin Panel: Ticket Table

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-TBL-001 | Ticket table loads successfully | ⬜ Not Run | Functional |
| AP-TBL-002 | Ticket ID column displays | ⬜ Not Run | UI |
| AP-TBL-003 | Description column displays ticket description | ⬜ Not Run | UI |
| AP-TBL-004 | Category or subtext displays under ticket description | ⬜ Not Run | UI |
| AP-TBL-005 | User column displays ticket owner | ⬜ Not Run | UI |
| AP-TBL-006 | Status column displays status badge | ⬜ Not Run | UI |
| AP-TBL-007 | Priority column displays priority badge | ⬜ Not Run | UI |
| AP-TBL-008 | Assigned To column displays technician or Unassigned | ⬜ Not Run | UI |
| AP-TBL-009 | Action column displays Open Ticket button | ⬜ Not Run | UI |
| AP-TBL-010 | Open Ticket button opens ticket detail view | ⬜ Not Run | Functional |
| AP-TBL-011 | Long ticket description does not break table layout | ⬜ Not Run | UI/UX |
| AP-TBL-012 | Empty ticket list displays proper empty state | ⬜ Not Run | UI/UX |

## 8. Admin Panel: Ticket Management

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-TM-001 | Admin can view full ticket details | ⬜ Not Run | Functional |
| AP-TM-002 | Admin can assign ticket to technician | ⬜ Not Run | Functional |
| AP-TM-003 | Assigned technician name updates in ticket table | ⬜ Not Run | Functional |
| AP-TM-004 | Admin can update ticket status to Ongoing | ⬜ Not Run | Functional |
| AP-TM-005 | Admin can update ticket status to Escalated | ⬜ Not Run | Functional |
| AP-TM-006 | Admin can update ticket status to Solved | ⬜ Not Run | Functional |
| AP-TM-007 | Admin can submit final solution | ⬜ Not Run | Functional |
| AP-TM-008 | Final solution changes ticket status to Admin Solved | ⬜ Not Run | Functional |
| AP-TM-009 | Final solution saves to Knowledge Base | ⬜ Not Run | Integration |
| AP-TM-010 | Final solution saves to AI Playground | ⬜ Not Run | Integration |
| AP-TM-011 | Invalid ticket status transition is blocked | ⬜ Not Run | Validation |
| AP-TM-012 | Admin can add comment to any ticket | ⬜ Not Run | Functional |

## 9. Admin Panel: Escalated Tickets

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-ESC-001 | Opening Escalated page | ⬜ Not Run | Functional |
| AP-ESC-002 | Escalated tickets display in list | ⬜ Not Run | Functional |
| AP-ESC-003 | MFA reset tickets appear as escalated | ⬜ Not Run | Functional |
| AP-ESC-004 | Password reset tickets appear as escalated | ⬜ Not Run | Functional |
| AP-ESC-005 | Account lockout tickets appear as escalated | ⬜ Not Run | Functional |
| AP-ESC-006 | Access request tickets appear as escalated | ⬜ Not Run | Functional |
| AP-ESC-007 | User-facing sensitive AI solution is hidden for escalated tickets | ⬜ Not Run | Security |

## 10. Admin Panel: Solved Tickets

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-SOL-001 | Opening Solved page | ⬜ Not Run | Functional |
| AP-SOL-002 | Solved tickets display in list | ⬜ Not Run | Functional |
| AP-SOL-003 | Admin Solved tickets display correctly | ⬜ Not Run | Functional |
| AP-SOL-004 | Solved ticket detail opens successfully | ⬜ Not Run | Functional |
| AP-SOL-005 | Solved ticket cannot generate new AI solution | ⬜ Not Run | Validation |
| AP-SOL-006 | Solved ticket cannot be alerted by user | ⬜ Not Run | Validation |

## 11. Admin Panel: Users

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-USR-001 | Opening Users page | ⬜ Not Run | Functional |
| AP-USR-002 | “+ User” floating button displays | ⬜ Not Run | UI |
| AP-USR-003 | Clicking “+ User” opens create user form | ⬜ Not Run | Functional |
| AP-USR-004 | Creating end user with valid data | ⬜ Not Run | Functional |
| AP-USR-005 | Creating technician with valid data | ⬜ Not Run | Functional |
| AP-USR-006 | Creating admin with valid data | ⬜ Not Run | Functional |
| AP-USR-007 | Duplicate email validation displays | ⬜ Not Run | Validation |
| AP-USR-008 | Password validation displays | ⬜ Not Run | Validation |
| AP-USR-009 | Technician skill field appears only for technician role | ⬜ Not Run | Functional |
| AP-USR-010 | Adding technician skills | ⬜ Not Run | Functional |
| AP-USR-011 | Editing technician skills | ⬜ Not Run | Functional |
| AP-USR-012 | Deleting technician skills | ⬜ Not Run | Functional |
| AP-USR-013 | Editing existing user details | ⬜ Not Run | Functional |
| AP-USR-014 | Deleting user | ⬜ Not Run | Functional |
| AP-USR-015 | Non-admin user cannot access Users page | ⬜ Not Run | Security |

## 12. Admin Panel: Notifications

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-NOT-001 | Opening notification list | ⬜ Not Run | Functional |
| AP-NOT-002 | Admin receives notification when user clicks Alert | ⬜ Not Run | Functional |
| AP-NOT-003 | Admin receives notification when ticket is updated | ⬜ Not Run | Functional |
| AP-NOT-004 | Unread notification count increases after new notification | ⬜ Not Run | Functional |
| AP-NOT-005 | Marking notification as read | ⬜ Not Run | Functional |
| AP-NOT-006 | Unread count decreases after marking notification as read | ⬜ Not Run | Functional |
| AP-NOT-007 | Clearing all notifications | ⬜ Not Run | Functional |

## 13. Admin Panel: Admin Playbook / AI / Knowledge Base

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-AI-001 | Opening Admin Playbook page | ⬜ Not Run | Functional |
| AP-AI-002 | Generating internal AI solution for eligible ticket | ⬜ Not Run | Functional |
| AP-AI-003 | Displaying generated AI solution in ticket modal | ⬜ Not Run | Functional |
| AP-AI-004 | Saving generated AI solution to Knowledge Base | ⬜ Not Run | Integration |
| AP-AI-005 | Saving generated AI solution to AI Playground | ⬜ Not Run | Integration |
| AP-AI-006 | Preventing AI solution generation for completed ticket | ⬜ Not Run | Validation |
| AP-KB-001 | Opening Knowledge Base list | ⬜ Not Run | Functional |
| AP-KB-002 | Searching Knowledge Base entries | ⬜ Not Run | Functional |
| AP-KB-003 | Filtering Knowledge Base entries by category | ⬜ Not Run | Functional |
| AP-KB-004 | Uploading valid KB CSV file | ⬜ Not Run | Functional |
| AP-KB-005 | Rejecting invalid KB CSV file | ⬜ Not Run | Validation |
| AP-KB-006 | Editing Knowledge Base entry | ⬜ Not Run | Functional |
| AP-KB-007 | Deleting Knowledge Base entry | ⬜ Not Run | Functional |
| AP-KB-008 | Internal KB solution is hidden from end user | ⬜ Not Run | Security |

## 14. Admin Panel: Inventory

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-INV-001 | Opening Inventory page | ⬜ Not Run | Functional |
| AP-INV-002 | Adding inventory item | ⬜ Not Run | Functional |
| AP-INV-003 | Required field validation on inventory form | ⬜ Not Run | Validation |
| AP-INV-004 | Editing inventory item | ⬜ Not Run | Functional |
| AP-INV-005 | Deleting inventory item | ⬜ Not Run | Functional |
| AP-INV-006 | Searching inventory item | ⬜ Not Run | Functional |
| AP-INV-007 | Filtering inventory by device type | ⬜ Not Run | Functional |
| AP-INV-008 | Displaying allocated user | ⬜ Not Run | UI |
| AP-INV-009 | Displaying department | ⬜ Not Run | UI |
| AP-INV-010 | Displaying warranty date | ⬜ Not Run | UI |
| AP-INV-011 | Displaying inventory count on dashboard | ⬜ Not Run | Integration |

## 15. Admin Panel: Audit Logs

| ID | Summary | Status | Type |
|---|---|---|---|
| AP-AUD-001 | Opening Audit Logs page | ⬜ Not Run | Functional |
| AP-AUD-002 | Audit log created when ticket is created | ⬜ Not Run | Integration |
| AP-AUD-003 | Audit log created when ticket is assigned | ⬜ Not Run | Integration |
| AP-AUD-004 | Audit log created when ticket status changes | ⬜ Not Run | Integration |
| AP-AUD-005 | Audit log created when user is created | ⬜ Not Run | Integration |
| AP-AUD-006 | Audit log created when KB entry is updated | ⬜ Not Run | Integration |
| AP-AUD-007 | Audit log created when AI solution is generated | ⬜ Not Run | Integration |
| AP-AUD-008 | Audit log displays correct actor | ⬜ Not Run | Functional |
| AP-AUD-009 | Audit log displays correct action | ⬜ Not Run | Functional |
| AP-AUD-010 | Audit log displays timestamp | ⬜ Not Run | UI |
| AP-AUD-011 | Non-admin user cannot access Audit Logs | ⬜ Not Run | Security |