QA Test Cases — AI-Powered IT Helpdesk Ticketing System
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-001	Authentication	Verify end user can log in with valid credentials	1. Open login page. 2. Enter valid end user email and password. 3. Click Login.	User is logged in and redirected to the end user dashboard or ticket page.	High
TC-002	Authentication	Verify technician is redirected to technician view after login	1. Log in as technician. 2. Observe landing page and menu options.	Technician sees only technician-allowed features and assigned-ticket views.	High
TC-003	Authentication	Verify admin is redirected to admin dashboard after login	1. Log in as admin. 2. Observe dashboard and navigation menu.	Admin sees admin dashboard, user management, KB, inventory, audit logs, and ticket management.	High
TC-004	Authentication	Verify login fails with invalid password	1. Enter valid email. 2. Enter wrong password. 3. Click Login.	Login is denied and a clear error message is displayed.	High
TC-005	Authentication	Verify empty login fields validation	1. Leave email and password blank. 2. Click Login.	Required field validation is displayed for email and password.	Medium
TC-006	Authentication	Verify logout ends user session	1. Log in. 2. Click Logout. 3. Try accessing a protected page using browser back or URL.	User is logged out and cannot access protected pages without logging in again.	High
TC-007	Authentication	Verify direct URL access is blocked for unauthenticated user	1. Log out. 2. Paste a protected admin/technician/user URL.	User is redirected to login or shown unauthorized access message.	High
TC-008	Authentication	Verify role-based access restriction	1. Log in as end user. 2. Try accessing admin user management URL.	Access is denied. End user cannot view or use admin-only features.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-009	Ticket Creation	Verify user can create a valid ticket	1. Log in as end user. 2. Open Create Ticket. 3. Select category. 4. Enter title, description, and priority. 5. Submit.	Ticket is created successfully with a unique ticket ID. Confirmation is displayed.	High
TC-010	Ticket Creation	Verify required field validation on ticket form	1. Open Create Ticket. 2. Leave category, title, description, or priority blank. 3. Submit.	User sees validation messages and ticket is not created.	High
TC-011	Ticket Creation	Verify created ticket appears in user ticket list	1. Create a valid ticket. 2. Navigate to My Tickets.	Newly created ticket appears with correct title, category, priority, status, and ticket ID.	High
TC-012	Ticket Creation	Verify long description is handled correctly	1. Enter a very long issue description. 2. Submit ticket.	System either accepts within allowed limit or displays clear max-length validation.	Medium
TC-013	Ticket Creation	Verify special characters in title/description do not break ticket creation	1. Enter special characters in title and description. 2. Submit ticket.	Ticket is created safely or validation appears. No UI break or script execution occurs.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-014	AI + Knowledge Base	Verify matching KB solution is shown for safe issue	1. Create ticket matching an existing public KB entry. 2. Submit ticket.	Relevant KB/AI suggested solution is displayed to the user.	High
TC-015	AI + Knowledge Base	Verify AI solution is saved to ticket comments	1. Create safe ticket that receives AI solution. 2. Open ticket detail/comments.	AI-generated solution appears in ticket comment history with AI Agent/System author.	High
TC-016	AI + Knowledge Base	Verify AI solution history is saved in AI Playground	1. Create ticket with AI suggestion. 2. Log in as admin/technician. 3. Open AI Playground. 4. Search ticket ID.	AI suggestion history is available and linked to the ticket.	High
TC-017	AI + Knowledge Base	Verify no irrelevant KB solution is displayed	1. Create ticket with issue unrelated to KB entries. 2. Submit ticket.	No incorrect solution is shown, or the ticket is routed to support.	Medium
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-018	Escalation Logic	Verify MFA reset ticket is escalated	1. Create ticket with title/description requesting MFA reset. 2. Submit ticket.	Ticket is escalated. User sees safe escalation message only. No self-help steps are exposed.	High
TC-019	Escalation Logic	Verify password reset ticket is escalated	1. Create ticket requesting password reset. 2. Submit ticket.	Ticket is escalated and routed to authorized staff.	High
TC-020	Escalation Logic	Verify account lockout ticket is escalated	1. Create ticket mentioning locked account. 2. Submit ticket.	Ticket is escalated and no sensitive troubleshooting steps are shown to user.	High
TC-021	Escalation Logic	Verify safe ticket does not escalate unnecessarily	1. Create ticket for simple printer issue or browser cache issue. 2. Submit ticket.	Safe KB/AI solution is shown if available and ticket is not incorrectly escalated.	High
TC-022	Escalation Logic	Verify access request hides admin-only solution	1. Create ticket requesting access or permission change. 2. Submit ticket.	User receives safe message; internal solution is hidden from user.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-023	Ticket Status Workflow	Verify initial ticket status after creation	1. Create normal ticket. 2. View ticket detail/list.	Initial status is correct, such as Pending or Assigned based on assignment logic.	High
TC-024	Ticket Status Workflow	Verify technician can update assigned ticket status	1. Log in as assigned technician. 2. Open assigned ticket. 3. Change status to Ongoing.	Status updates successfully and is visible to user/admin/technician.	High
TC-025	Ticket Status Workflow	Verify unauthorized status update is blocked	1. Log in as unrelated technician. 2. Attempt to update unassigned ticket status.	Update is blocked and access is denied.	High
TC-026	Ticket Status Workflow	Verify solved ticket behavior	1. Technician/admin marks ticket as Solved. 2. Open ticket as user.	Ticket displays solved status and resolution-related information according to role permissions.	High
TC-027	Ticket Status Workflow	Verify Admin Solved workflow	1. Log in as admin. 2. Submit final solution.	Ticket status changes to Admin Solved and appears in Admin Solved section.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-028	Skill-Based Assignment	Verify ticket is assigned to technician with matching skill	1. Create technician with skill “Network”. 2. Create ticket with Network category/issue.	Ticket is assigned to technician with matching skill and status becomes Assigned.	High
TC-029	Skill-Based Assignment	Verify assigned technician can view assigned ticket	1. Log in as assigned technician. 2. Open assigned tickets list.	Ticket appears in technician’s assigned queue.	High
TC-030	Skill-Based Assignment	Verify other technicians cannot access unassigned ticket	1. Log in as non-assigned technician. 2. Try opening another technician’s ticket.	Access is denied or ticket is hidden.	High
TC-031	Skill-Based Assignment	Verify admin can manually assign ticket	1. Log in as admin. 2. Open ticket. 3. Assign technician manually.	Ticket assignment updates and selected technician can access the ticket.	High
TC-032	Skill-Based Assignment	Verify assignment behavior when no technician skill matches	1. Create ticket with category/issue that matches no technician skill.	Ticket remains pending, escalated, or routed to default queue according to business rule.	Medium
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-033	User Management	Verify admin can create end user	1. Log in as admin. 2. Open User Management. 3. Create user with valid details.	User is created successfully and appears in user list.	High
TC-034	User Management	Verify admin can create technician with skills	1. Select Technician role. 2. Enter user details and technician skills. 3. Save.	Technician is created with assigned skills.	High
TC-035	User Management	Verify technician skill field appears only for technician role	1. Select End User role. 2. Observe form. 3. Select Technician role.	Skill field is hidden for non-technician roles and visible for technician role.	Medium
TC-036	User Management	Verify duplicate email validation	1. Create user with existing email. 2. Submit form.	Duplicate email validation is displayed and user is not created.	High
TC-037	User Management	Verify admin can edit user details	1. Open existing user. 2. Edit name/role/skills. 3. Save.	Updated details are saved and displayed correctly.	High
TC-038	User Management	Verify admin can delete user	1. Select user. 2. Click Delete. 3. Confirm deletion.	User is removed or deactivated according to expected behavior.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-039	Ticket Comments	Verify user can comment on own ticket	1. Log in as ticket owner. 2. Open own ticket. 3. Add comment.	Comment is saved with correct author and timestamp.	High
TC-040	Ticket Comments	Verify user cannot comment on another user’s ticket	1. Log in as different user. 2. Attempt to access/comment on another user’s ticket.	Access/comment action is denied.	High
TC-041	Ticket Comments	Verify technician can comment on assigned ticket	1. Log in as assigned technician. 2. Add comment to assigned ticket.	Comment is added and visible in history.	High
TC-042	Ticket Comments	Verify comments display in chronological order	1. Add comments from user, technician, admin, and AI/System. 2. View history.	Comments display in correct order with author and timestamp.	Medium
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-043	Alert Button	Verify user can alert staff when suggested solution fails	1. Create ticket with suggested solution. 2. Click Alert.	Alert is submitted and notification is sent to assigned technician/admin.	High
TC-044	Alert Button	Verify ticket remains Assigned after alert if technician is assigned	1. Open assigned ticket as user. 2. Click Alert.	Ticket status remains Assigned and comment/update is added.	High
TC-045	Alert Button	Verify alert escalates when no technician is assigned	1. Create ticket with no assigned technician. 2. Click Alert.	Ticket is escalated or routed according to escalation rule.	High
TC-046	Alert Button	Verify solved ticket cannot be alerted	1. Open solved ticket as user. 2. Attempt to click Alert.	Alert button is hidden/disabled or validation prevents alert.	Medium
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-047	Notifications	Verify admin receives alert notification	1. User clicks Alert on ticket. 2. Log in as admin. 3. Open notification bell.	Admin sees notification with correct ticket details.	High
TC-048	Notifications	Verify assigned technician receives ticket notification	1. Assign ticket to technician. 2. Trigger ticket update/alert. 3. Log in as technician.	Technician receives relevant notification.	High
TC-049	Notifications	Verify unread count updates correctly	1. Trigger notification. 2. Observe unread count. 3. Mark as read.	Count increases when new notification arrives and decreases after marking read.	Medium
TC-050	Notifications	Verify user does not see admin/technician notifications	1. Log in as end user. 2. Open notifications.	User cannot view admin or technician-only notifications.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-051	Knowledge Base	Verify admin can view KB entries	1. Log in as admin. 2. Open Knowledge Base.	KB list loads successfully.	High
TC-052	Knowledge Base	Verify KB search returns matching results	1. Enter keyword from known KB entry. 2. Search.	Matching KB entries are displayed.	Medium
TC-053	Knowledge Base	Verify KB category filter works	1. Select a category filter.	Only KB entries from selected category are shown.	Medium
TC-054	Knowledge Base	Verify valid CSV upload creates KB entries	1. Upload valid CSV file. 2. Confirm import.	KB entries are created successfully.	High
TC-055	Knowledge Base	Verify invalid CSV upload is rejected	1. Upload CSV with missing required columns or invalid data.	File is rejected with clear validation message.	High
TC-056	Knowledge Base	Verify internal KB solution is not shown to end user	1. Create ticket matching internal-only KB entry.	End user does not see internal/admin solution.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-057	AI Playground	Verify AI logs are saved for ticket	1. Generate user AI solution. 2. Open AI Playground. 3. Search ticket ID.	AI log appears with ticket details and generated content.	High
TC-058	AI Playground	Verify search by ticket ID works	1. Open AI Playground. 2. Enter valid ticket ID.	Matching AI history is displayed.	Medium
TC-059	AI Playground	Verify search by title/category/description works	1. Search using ticket title, category, or description keyword.	Relevant AI history records are displayed.	Medium
TC-060	AI Playground	Verify technician access restriction	1. Log in as technician. 2. Open AI Playground.	Technician sees only allowed/assigned ticket AI records.	High
TC-061	AI Playground	Verify manual solution saves	1. Open AI history. 2. Add manual solution. 3. Save.	Manual solution is stored and linked to the ticket.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-062	Admin AI Solutions	Verify AI Solutions button generates internal solution	1. Log in as admin/assigned technician. 2. Open eligible ticket. 3. Click AI Solutions.	Internal AI troubleshooting steps are generated and displayed.	High
TC-063	Admin AI Solutions	Verify generated internal solution is saved to AI Playground	1. Generate internal AI solution. 2. Open AI Playground.	Generated solution is saved in AI history.	High
TC-064	Admin AI Solutions	Verify generated solution can be saved to KB	1. Generate internal solution. 2. Click Save to KB.	Solution is saved as KB entry with correct ticket/category details.	High
TC-065	Admin AI Solutions	Verify completed tickets cannot generate AI solution	1. Open solved/admin-solved ticket. 2. Attempt to generate AI solution.	Button is hidden/disabled or action is blocked.	Medium
TC-066	Admin AI Solutions	Verify technician can generate AI solution only for assigned tickets	1. Log in as technician. 2. Try AI Solutions on unassigned ticket.	Access is denied.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-067	Final Solution / Admin Solved	Verify only admin can submit final solution	1. Log in as technician/user. 2. Attempt to submit final solution.	Final solution action is unavailable or access is denied.	High
TC-068	Final Solution / Admin Solved	Verify required validation for final solution	1. Log in as admin. 2. Submit final solution form blank.	Required validation message is displayed.	High
TC-069	Final Solution / Admin Solved	Verify final solution changes ticket to Admin Solved	1. Admin enters final solution. 2. Submit.	Ticket status changes to Admin Solved.	High
TC-070	Final Solution / Admin Solved	Verify final solution is saved to KB and AI Playground	1. Submit final solution. 2. Check KB and AI Playground.	Final solution is stored in both locations with correct ticket reference.	High
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-071	Inventory Management	Verify admin can add inventory item	1. Open Inventory. 2. Add laptop/device with required details. 3. Save.	Inventory item is created and appears in list.	High
TC-072	Inventory Management	Verify inventory required field validation	1. Open Add Inventory form. 2. Leave required fields blank. 3. Save.	Required validation messages are displayed.	High
TC-073	Inventory Management	Verify inventory item can be edited	1. Open existing item. 2. Edit allocated user, department, warranty, or notes. 3. Save.	Updated details are displayed correctly.	Medium
TC-074	Inventory Management	Verify inventory item can be deleted	1. Select inventory item. 2. Delete and confirm.	Item is removed or marked inactive according to business rule.	Medium
TC-075	Inventory Management	Verify inventory search and filter work	1. Search by device name/user. 2. Filter by device type.	Correct matching devices are shown.	Medium
TC-076	Inventory Management	Verify warranty date displays correctly	1. Add item with warranty date. 2. View inventory list/detail.	Warranty date is displayed in correct format.	Low
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-077	Audit Logs	Verify audit log is created when ticket is created	1. Create ticket. 2. Log in as admin. 3. Open Audit Logs.	Audit log shows ticket created action with correct actor and timestamp.	High
TC-078	Audit Logs	Verify audit log is created for ticket assignment	1. Assign ticket to technician. 2. Check Audit Logs.	Log shows ticket assigned action with correct actor, ticket, and timestamp.	High
TC-079	Audit Logs	Verify audit log is created for KB update	1. Edit KB entry. 2. Check Audit Logs.	KB update action is recorded.	Medium
TC-080	Audit Logs	Verify audit logs are admin-only	1. Log in as end user/technician. 2. Try accessing Audit Logs.	Access is denied unless role is allowed by requirement.	High
TC-081	Audit Logs	Verify audit log search/filter works	1. Search/filter by actor, action, or date.	Matching audit records are displayed.	Medium
TC ID	Module	Test Case Title	Steps	Expected Result	Priority
TC-082	Dashboard	Verify admin dashboard metrics load correctly	1. Log in as admin. 2. View dashboard.	Open, escalated, solved, admin solved, inventory, and KB counts are displayed.	High
TC-083	Dashboard	Verify dashboard counts match actual records	1. Note ticket/inventory/KB records. 2. Compare dashboard counts.	Dashboard counts match actual system data.	High
TC-084	Dashboard	Verify recent tickets display correctly	1. Create/update tickets. 2. Open dashboard.	Recent tickets section displays latest relevant tickets.	Medium
TC-085	Dashboard	Verify quick action buttons navigate correctly	1. Click each quick action button.	User is routed to the correct page/form.	Medium
TC-086	Dashboard	Verify technician dashboard shows only allowed data	1. Log in as technician. 2. View dashboard metrics and recent tickets.	Technician sees only assigned/allowed ticket data.	High