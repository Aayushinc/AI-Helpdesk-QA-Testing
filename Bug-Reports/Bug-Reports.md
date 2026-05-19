# Bug Reports — AI-Powered IT Helpdesk Ticketing System

## High Severity Bugs

| Report ID | Module | Title | Environment | Severity | Preconditions | Steps to Reproduce | Actual Result |
|---|---|---|---|---|---|---|---|
| BUG-HIGH-001 | Authentication | End user can access Admin Panel using direct URL | Chrome / Firefox | High | End user account exists and is logged in | 1. Log in as End User.<br>2. Copy/paste Admin Panel URL in browser.<br>3. Press Enter. | End user is able to access the Admin Panel page. |
| BUG-HIGH-002 | Authentication | User remains logged in after clicking Logout | Chrome / Firefox | High | User is logged in | 1. Click Logout.<br>2. Click browser Back button.<br>3. Refresh the page. | User can still view the previous authenticated page. |
| BUG-HIGH-003 | Ticket Creation | Ticket is created with blank required fields | Chrome / Firefox | High | User is logged in as End User | 1. Open Create Ticket page.<br>2. Leave category, title, description, and priority blank.<br>3. Click Submit. | Ticket is created even though required fields are missing. |
| BUG-HIGH-004 | Escalation Logic | MFA reset ticket displays AI self-help solution to user | Chrome / Firefox | High | Public/internal KB entries exist | 1. Log in as End User.<br>2. Create ticket with title “MFA reset request”.<br>3. Submit ticket. | AI troubleshooting steps are shown to the user. |
| BUG-HIGH-005 | Skill-Based Assignment | Technician can access ticket not assigned to them | Chrome / Firefox | High | Two technician accounts exist | 1. Assign ticket to Technician A.<br>2. Log in as Technician B.<br>3. Open ticket URL directly. | Technician B can open and view the unassigned ticket. |
| BUG-HIGH-006 | Final Solution / Admin Solved | Technician can submit final admin solution | Chrome / Firefox | High | Technician is logged in and has assigned ticket | 1. Open assigned ticket as technician.<br>2. Enter final solution.<br>3. Submit final solution. | Technician successfully submits final solution and ticket moves to Admin Solved. |
| BUG-HIGH-007 | Knowledge Base | Internal KB solution is visible to end user | Chrome / Firefox | High | Internal KB entry exists | 1. Log in as End User.<br>2. Create ticket matching internal KB article.<br>3. View suggested solution. | Internal solution is displayed to end user. |

## Medium Severity Bugs

| Report ID | Module | Title | Environment | Severity | Preconditions | Steps to Reproduce | Actual Result |
|---|---|---|---|---|---|---|---|
| BUG-MED-001 | Ticket Status Workflow | Ticket status does not update for end user after technician changes it | Chrome / Firefox | Medium | Ticket is assigned to technician | 1. Log in as technician.<br>2. Change ticket status to Ongoing.<br>3. Log in as ticket owner.<br>4. Open My Tickets. | User still sees the old ticket status. |
| BUG-MED-002 | Notifications | Notification unread count does not decrease after marking as read | Chrome / Firefox | Medium | Admin has unread notifications | 1. Log in as Admin.<br>2. Open notification bell.<br>3. Mark notification as read. | Notification count remains unchanged. |
| BUG-MED-003 | Ticket Comments | Comments display in incorrect order | Chrome / Firefox | Medium | Ticket has multiple comments | 1. Add comment as user.<br>2. Add comment as technician.<br>3. Add comment as admin.<br>4. View comment history. | Comments display out of order. |
| BUG-MED-004 | Knowledge Base | KB category filter shows unrelated entries | Chrome / Firefox | Medium | Multiple KB categories exist | 1. Log in as Admin.<br>2. Open Knowledge Base.<br>3. Filter by category “Hardware”. | Software and Account Access entries also display. |
| BUG-MED-005 | AI Playground | Search by Ticket ID returns no result for existing AI history | Chrome / Firefox | Medium | Ticket has AI-generated solution saved | 1. Open AI Playground.<br>2. Search using valid ticket ID. | No result is returned. |
| BUG-MED-006 | Inventory Management | Inventory search does not return matching device | Chrome / Firefox | Medium | Inventory item exists | 1. Open Inventory page.<br>2. Search for existing device name or allocated user. | Search returns blank result. |
| BUG-MED-007 | Dashboard | Dashboard ticket counts do not match actual ticket records | Chrome / Firefox | Medium | Tickets exist with different statuses | 1. Log in as Admin.<br>2. Count open, escalated, and solved tickets manually.<br>3. Compare with dashboard metrics. | Dashboard count is incorrect. |

## Low Severity Bugs

| Report ID | Module | Title | Environment | Severity | Preconditions | Steps to Reproduce | Actual Result |
|---|---|---|---|---|---|---|---|
| BUG-LOW-001 | UI | Login error message has spelling or grammar issue | Chrome / Firefox | Low | User is on login page | 1. Enter invalid credentials.<br>2. Click Login.<br>3. Review error message. | Message contains typo or unclear wording. |
| BUG-LOW-002 | Ticket Creation | Priority dropdown alignment is inconsistent | Chrome / Firefox | Low | User is on Create Ticket page | 1. Open Create Ticket page.<br>2. View Priority dropdown. | Priority dropdown appears misaligned. |
| BUG-LOW-003 | Dashboard | Quick action button text is not centered | Chrome / Firefox | Low | Admin is logged in | 1. Open Dashboard.<br>2. Review quick action buttons. | Button text appears slightly off-center. |
| BUG-LOW-004 | Knowledge Base | KB table columns have inconsistent spacing | Chrome / Firefox | Low | Admin is logged in | 1. Open Knowledge Base page.<br>2. Review KB table layout. | Some columns appear too narrow or uneven. |
| BUG-LOW-005 | Inventory Management | Warranty date format is inconsistent across inventory screens | Chrome / Firefox | Low | Inventory item with warranty date exists | 1. Open Inventory list.<br>2. Open inventory detail page.<br>3. Compare warranty date format. | Date format differs between list and detail pages. |
| BUG-LOW-006 | Notifications | Notification text wraps awkwardly on smaller browser width | Chrome / Firefox | Low | User has notifications | 1. Resize browser window.<br>2. Open notification bell.<br>3. Review notification text. | Text wraps awkwardly or overlaps. |
| BUG-LOW-007 | Ticket Comments | Long comment text does not wrap cleanly | Chrome / Firefox | Low | Ticket comment field is available | 1. Add a long comment without spaces.<br>2. Save comment.<br>3. View comment history. | Long text stretches outside the comment container. |

## Suggestions / Enhancements

| Report ID | Module | Title | Environment | Severity | Preconditions | Details | Current Behavior |
|---|---|---|---|---|---|---|---|
| SUG-001 | Ticket Creation | Add duplicate ticket warning before submission | Chrome / Firefox | N/A | User is creating a ticket | When user enters a title/description similar to an existing open ticket, show a possible duplicate warning. | User can submit similar tickets without warning. |
| SUG-002 | Dashboard | Add date range filter to dashboard metrics | Chrome / Firefox | N/A | Admin or technician is on dashboard | Add filters such as Today, This Week, This Month, and Custom Range. | Dashboard shows counts without date filtering. |
| SUG-003 | Notifications | Add notification preference settings | Chrome / Firefox | N/A | Staff user has notifications enabled | Allow admins/technicians to choose which events trigger notifications. | All supported notifications appear without user preference control. |
| SUG-004 | Knowledge Base | Add KB article approval workflow | Chrome / Firefox | N/A | Admin manages KB entries | New or edited KB entries should require admin approval before becoming public. | KB entries may become available without approval workflow. |
| SUG-005 | Ticket Status Workflow | Add status change reason field | Chrome / Firefox | N/A | Staff user updates ticket status | Require or allow staff to enter a reason when changing ticket status. | Status can be changed without explanation. |
| SUG-006 | Inventory Management | Add warranty expiry alert | Chrome / Firefox | N/A | Inventory item has warranty date | Notify admin when warranty is near expiration. | Warranty date is displayed but no proactive alert is shown. |
| SUG-007 | AI Playground | Add AI confidence score or relevance rating | Chrome / Firefox | N/A | AI solution is generated | Display confidence/relevance rating for AI-generated suggestions. | AI suggestion displays without confidence or relevance indicator. |