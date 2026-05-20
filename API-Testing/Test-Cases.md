# Test_Cases.md

# API Test Cases — AI-Powered IT Helpdesk Ticketing System

## 1. Authentication API — Login

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-AUTH-001 | `/api/auth/login` | POST | Verify admin can log in with valid credentials | Admin account exists | `{ "email": "admin@gmail.com", "password": "adminexample" }` | 1. Open Postman.<br>2. Select POST method.<br>3. Enter login URL.<br>4. Add valid admin request body.<br>5. Click Send. | API returns success response. Admin is authenticated and session/token is generated. | Functional | High |
| API-AUTH-002 | `/api/auth/login` | POST | Verify normal user can log in with valid credentials | Normal user account exists | `{ "email": "user@gmail.com", "password": "user123" }` | 1. Send POST login request with normal user credentials. | API returns success response. User is authenticated successfully. | Functional | High |
| API-AUTH-003 | `/api/auth/login` | POST | Verify helpdesk technician can log in with valid credentials | Helpdesk user account exists | `{ "email": "helpdesk@gmail.com", "password": "desk123" }` | 1. Send POST login request with helpdesk credentials. | API returns success response. Helpdesk technician is authenticated successfully. | Functional | High |
| API-AUTH-004 | `/api/auth/login` | POST | Verify login fails with wrong password | User account exists | `{ "email": "admin@gmail.com", "password": "wrongpass" }` | 1. Send POST login request with wrong password. | API rejects login and returns proper error response. | Negative | High |
| API-AUTH-005 | `/api/auth/login` | POST | Verify login fails with unregistered email | No account exists for email | `{ "email": "unknown@gmail.com", "password": "adminexample" }` | 1. Send POST login request with unregistered email. | API rejects login and returns user not found or invalid credentials error. | Negative | High |
| API-AUTH-006 | `/api/auth/login` | POST | Verify login validation when email is missing | None | `{ "password": "adminexample" }` | 1. Send POST login request without email. | API returns validation error for missing email. | Validation | Medium |
| API-AUTH-007 | `/api/auth/login` | POST | Verify login validation when password is missing | None | `{ "email": "admin@gmail.com" }` | 1. Send POST login request without password. | API returns validation error for missing password. | Validation | Medium |
| API-AUTH-008 | `/api/auth/login` | POST | Verify login validation with blank email and password | None | `{ "email": "", "password": "" }` | 1. Send POST login request with blank fields. | API returns validation error and login is not allowed. | Validation | Medium |
| API-AUTH-009 | `/api/auth/login` | POST | Verify invalid email format is rejected | None | `{ "email": "adminemail", "password": "adminexample" }` | 1. Send POST login request with invalid email format. | API returns validation error for invalid email format. | Validation | Medium |

## 2. Authentication API — Logout

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-AUTH-010 | `/api/auth/logout` | POST | Verify authenticated admin can log out | Admin is logged in | None | 1. Log in as admin.<br>2. Send POST logout request. | API returns success response and admin session/token is invalidated. | Functional | High |
| API-AUTH-011 | `/api/auth/logout` | POST | Verify normal user can log out | User is logged in | None | 1. Log in as normal user.<br>2. Send POST logout request. | API returns success response and user session/token is invalidated. | Functional | High |
| API-AUTH-012 | `/api/auth/logout` | POST | Verify unauthenticated logout request is handled safely | No user is logged in | None | 1. Clear token/cookies.<br>2. Send POST logout request. | API returns unauthorized or safe logout response without server error. | Negative | Medium |
| API-AUTH-013 | `/api/auth/logout` | POST | Verify protected API cannot be accessed after logout | User is logged in first | None | 1. Log in as admin.<br>2. Send logout request.<br>3. Try GET `/api/admin/users`. | API blocks access after logout. | Security | High |

## 3. Admin API — Create Normal User

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-USER-001 | `/api/admin/users` | POST | Verify admin can create normal user | Admin is logged in | `{ "name": "user", "email": "user@gmail.com", "password": "user123", "role": "user" }` | 1. Log in as admin.<br>2. Send POST create user request with valid data. | User is created successfully and response contains created user details. | Functional | High |
| API-USER-002 | `/api/admin/users` | POST | Verify normal user cannot create another user | Normal user is logged in | `{ "name": "test", "email": "test@gmail.com", "password": "test123", "role": "user" }` | 1. Log in as normal user.<br>2. Send POST create user request. | API returns forbidden or unauthorized response. | Security | High |
| API-USER-003 | `/api/admin/users` | POST | Verify unauthenticated user cannot create user | No user is logged in | `{ "name": "test", "email": "test@gmail.com", "password": "test123", "role": "user" }` | 1. Clear authentication.<br>2. Send POST create user request. | API blocks request and returns unauthorized response. | Security | High |
| API-USER-004 | `/api/admin/users` | POST | Verify duplicate email is rejected | User email already exists | `{ "name": "user", "email": "user@gmail.com", "password": "user123", "role": "user" }` | 1. Log in as admin.<br>2. Create user once.<br>3. Send same request again. | API rejects duplicate email and does not create another user. | Validation | High |
| API-USER-005 | `/api/admin/users` | POST | Verify name is required during user creation | Admin is logged in | `{ "email": "missingname@gmail.com", "password": "user123", "role": "user" }` | 1. Send create user request without name. | API returns validation error for missing name. | Validation | Medium |
| API-USER-006 | `/api/admin/users` | POST | Verify email is required during user creation | Admin is logged in | `{ "name": "user", "password": "user123", "role": "user" }` | 1. Send create user request without email. | API returns validation error for missing email. | Validation | Medium |
| API-USER-007 | `/api/admin/users` | POST | Verify password is required during user creation | Admin is logged in | `{ "name": "user", "email": "nopassword@gmail.com", "role": "user" }` | 1. Send create user request without password. | API returns validation error for missing password. | Validation | Medium |
| API-USER-008 | `/api/admin/users` | POST | Verify role is required during user creation | Admin is logged in | `{ "name": "user", "email": "norole@gmail.com", "password": "user123" }` | 1. Send create user request without role. | API returns validation error for missing role. | Validation | Medium |
| API-USER-009 | `/api/admin/users` | POST | Verify invalid email format is rejected during user creation | Admin is logged in | `{ "name": "user", "email": "invalidemail", "password": "user123", "role": "user" }` | 1. Send create user request with invalid email format. | API returns validation error for invalid email. | Validation | Medium |
| API-USER-010 | `/api/admin/users` | POST | Verify invalid role is rejected | Admin is logged in | `{ "name": "user", "email": "badrole@gmail.com", "password": "user123", "role": "manager" }` | 1. Send create user request with unsupported role. | API rejects invalid role value. | Validation | Medium |

## 4. Admin API — Create Helpdesk Technician

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-HD-001 | `/api/admin/users` | POST | Verify admin can create helpdesk technician user | Admin is logged in | `{ "name": "helpdesk", "email": "helpdesk@gmail.com", "password": "desk123", "role": "helpdesk" }` | 1. Log in as admin.<br>2. Send POST create helpdesk user request. | Helpdesk technician is created successfully. | Functional | High |
| API-HD-002 | `/api/admin/users` | POST | Verify created helpdesk technician can log in | Helpdesk user exists | `{ "email": "helpdesk@gmail.com", "password": "desk123" }` | 1. Create helpdesk user as admin.<br>2. Send login request using helpdesk credentials. | Helpdesk technician logs in successfully. | Integration | High |
| API-HD-003 | `/api/admin/users` | POST | Verify duplicate helpdesk email is rejected | Helpdesk email already exists | `{ "name": "helpdesk", "email": "helpdesk@gmail.com", "password": "desk123", "role": "helpdesk" }` | 1. Create helpdesk user once.<br>2. Send same request again. | API rejects duplicate helpdesk email. | Validation | High |
| API-HD-004 | `/api/admin/users` | POST | Verify normal user cannot create helpdesk technician | Normal user is logged in | `{ "name": "helpdesk2", "email": "helpdesk2@gmail.com", "password": "desk123", "role": "helpdesk" }` | 1. Log in as normal user.<br>2. Send create helpdesk request. | API returns forbidden or unauthorized response. | Security | High |

## 5. Admin API — Get All Users

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-GET-USERS-001 | `/api/admin/users` | GET | Verify admin can get all users | Admin is logged in | None | 1. Log in as admin.<br>2. Send GET request to `/api/admin/users`. | API returns list of users. | Functional | High |
| API-GET-USERS-002 | `/api/admin/users` | GET | Verify response contains normal user details | Admin is logged in and normal user exists | None | 1. Create normal user.<br>2. Send GET all users request. | Response includes created normal user details. | Integration | Medium |
| API-GET-USERS-003 | `/api/admin/users` | GET | Verify response contains helpdesk user details | Admin is logged in and helpdesk user exists | None | 1. Create helpdesk user.<br>2. Send GET all users request. | Response includes created helpdesk user details. | Integration | Medium |
| API-GET-USERS-004 | `/api/admin/users` | GET | Verify normal user cannot get all users | Normal user is logged in | None | 1. Log in as normal user.<br>2. Send GET request to `/api/admin/users`. | API returns forbidden or unauthorized response. | Security | High |
| API-GET-USERS-005 | `/api/admin/users` | GET | Verify helpdesk technician cannot get all users if admin-only | Helpdesk user is logged in | None | 1. Log in as helpdesk technician.<br>2. Send GET request to `/api/admin/users`. | API returns forbidden or unauthorized response. | Security | High |
| API-GET-USERS-006 | `/api/admin/users` | GET | Verify unauthenticated request cannot get all users | No user is logged in | None | 1. Clear authentication.<br>2. Send GET request to `/api/admin/users`. | API returns unauthorized response. | Security | High |

## 6. Ticket API — Create Ticket

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-TICKET-001 | `/api/tickets` | POST | Verify normal user can create ticket with valid data | Normal user is logged in | `{ "description": "Outlook opens on webapp not on laptop app", "Priority": "Low", "Category": "Email" }` | 1. Log in as normal user.<br>2. Send POST create ticket request with valid body. | Ticket is created successfully and ticket ID is returned. | Functional | High |
| API-TICKET-002 | `/api/tickets` | POST | Verify admin can create ticket if allowed | Admin is logged in | `{ "description": "Admin test ticket", "Priority": "Medium", "Category": "Software" }` | 1. Log in as admin.<br>2. Send POST create ticket request. | Ticket is created if admin ticket creation is supported. | Functional | Medium |
| API-TICKET-003 | `/api/tickets` | POST | Verify unauthenticated user cannot create ticket | No user is logged in | `{ "description": "Test issue", "Priority": "Low", "Category": "Email" }` | 1. Clear authentication.<br>2. Send POST create ticket request. | API returns unauthorized response. | Security | High |
| API-TICKET-004 | `/api/tickets` | POST | Verify ticket creation fails when description is missing | Normal user is logged in | `{ "Priority": "Low", "Category": "Email" }` | 1. Send create ticket request without description. | API returns validation error for missing description. | Validation | High |
| API-TICKET-005 | `/api/tickets` | POST | Verify ticket creation fails when priority is missing | Normal user is logged in | `{ "description": "Test issue", "Category": "Email" }` | 1. Send create ticket request without priority. | API returns validation error for missing priority. | Validation | High |
| API-TICKET-006 | `/api/tickets` | POST | Verify ticket creation fails when category is missing | Normal user is logged in | `{ "description": "Test issue", "Priority": "Low" }` | 1. Send create ticket request without category. | API returns validation error for missing category. | Validation | High |
| API-TICKET-007 | `/api/tickets` | POST | Verify blank description is rejected | Normal user is logged in | `{ "description": "", "Priority": "Low", "Category": "Email" }` | 1. Send create ticket request with blank description. | API returns validation error. | Validation | Medium |
| API-TICKET-008 | `/api/tickets` | POST | Verify invalid priority value is rejected | Normal user is logged in | `{ "description": "Test issue", "Priority": "UrgentNow", "Category": "Email" }` | 1. Send create ticket request with invalid priority. | API rejects invalid priority value. | Validation | Medium |
| API-TICKET-009 | `/api/tickets` | POST | Verify invalid category value is handled correctly | Normal user is logged in | `{ "description": "Test issue", "Priority": "Low", "Category": "UnknownCategory" }` | 1. Send create ticket request with invalid category. | API rejects invalid category or handles it according to business rule. | Validation | Medium |
| API-TICKET-010 | `/api/tickets` | POST | Verify long description is handled correctly | Normal user is logged in | `{ "description": "Very long text...", "Priority": "Medium", "Category": "Software" }` | 1. Send create ticket request with very long description. | API accepts within allowed limit or returns max-length validation error. | Edge Case | Medium |
| API-TICKET-011 | `/api/tickets` | POST | Verify special characters in ticket description are handled safely | Normal user is logged in | `{ "description": "<script>alert('x')</script>", "Priority": "Low", "Category": "Email" }` | 1. Send create ticket request with script/special characters. | API stores data safely or rejects unsafe input. No script execution occurs. | Security | High |
| API-TICKET-012 | `/api/tickets` | POST | Verify field casing for priority is handled correctly | Normal user is logged in | `{ "description": "Test issue", "priority": "Low", "Category": "Email" }` | 1. Send request using lowercase `priority` field. | API either accepts correct schema or returns clear validation error. | Validation | Medium |

## 7. Ticket API — Assign Ticket

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-ASSIGN-001 | `/api/tickets/{ticketid}/assign` | POST | Verify admin can assign ticket to helpdesk technician | Admin is logged in, ticket exists, helpdesk user exists | `{ "assignedTo": "{HD User ID}" }` | 1. Log in as admin.<br>2. Create or use existing ticket.<br>3. Create or use helpdesk user.<br>4. Send assign request with valid ticket ID and helpdesk user ID. | Ticket is assigned successfully to helpdesk technician. | Functional | High |
| API-ASSIGN-002 | `/api/tickets/{ticketid}/assign` | POST | Verify assigned ticket response contains assigned helpdesk user | Admin is logged in and ticket is assigned | `{ "assignedTo": "{HD User ID}" }` | 1. Assign ticket to helpdesk user.<br>2. Review response body. | Response shows assigned technician ID or assigned technician details. | Functional | Medium |
| API-ASSIGN-003 | `/api/tickets/{ticketid}/assign` | POST | Verify normal user cannot assign ticket | Normal user is logged in | `{ "assignedTo": "{HD User ID}" }` | 1. Log in as normal user.<br>2. Send assign request. | API returns forbidden or unauthorized response. | Security | High |
| API-ASSIGN-004 | `/api/tickets/{ticketid}/assign` | POST | Verify helpdesk technician cannot assign ticket if admin-only | Helpdesk user is logged in | `{ "assignedTo": "{HD User ID}" }` | 1. Log in as helpdesk technician.<br>2. Send assign request. | API returns forbidden or unauthorized response. | Security | High |
| API-ASSIGN-005 | `/api/tickets/{ticketid}/assign` | POST | Verify unauthenticated user cannot assign ticket | No user is logged in | `{ "assignedTo": "{HD User ID}" }` | 1. Clear authentication.<br>2. Send assign request. | API returns unauthorized response. | Security | High |
| API-ASSIGN-006 | `/api/tickets/{ticketid}/assign` | POST | Verify assignment fails with invalid ticket ID | Admin is logged in | `{ "assignedTo": "{HD User ID}" }` | 1. Send assign request using invalid ticket ID. | API returns ticket not found or validation error. | Negative | High |
| API-ASSIGN-007 | `/api/tickets/{ticketid}/assign` | POST | Verify assignment fails with missing assignedTo field | Admin is logged in and ticket exists | `{ }` | 1. Send assign request without assignedTo. | API returns validation error for missing assignedTo. | Validation | High |
| API-ASSIGN-008 | `/api/tickets/{ticketid}/assign` | POST | Verify assignment fails with invalid helpdesk user ID | Admin is logged in and ticket exists | `{ "assignedTo": "invalid-user-id" }` | 1. Send assign request with invalid assignedTo ID. | API returns user not found or validation error. | Negative | High |
| API-ASSIGN-009 | `/api/tickets/{ticketid}/assign` | POST | Verify assignment fails when assignedTo is normal user ID | Admin is logged in, normal user exists, ticket exists | `{ "assignedTo": "{Normal User ID}" }` | 1. Send assign request using normal user ID instead of helpdesk ID. | API rejects assignment because assignee must be helpdesk technician. | Validation | High |
| API-ASSIGN-010 | `/api/tickets/{ticketid}/assign` | POST | Verify reassignment from one helpdesk technician to another | Admin is logged in, two helpdesk users exist, ticket exists | `{ "assignedTo": "{Second HD User ID}" }` | 1. Assign ticket to Helpdesk A.<br>2. Assign same ticket to Helpdesk B. | Ticket assignment updates to new helpdesk technician if reassignment is allowed. | Functional | Medium |

## 8. End-to-End API Flow

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-E2E-001 | Multiple APIs | POST / GET | Verify complete admin creates users and user creates ticket flow | Admin account exists | Admin login body, create user body, create helpdesk body, ticket body, assign body | 1. Log in as admin.<br>2. Create normal user.<br>3. Create helpdesk technician.<br>4. Log out admin.<br>5. Log in as normal user.<br>6. Create ticket.<br>7. Log out normal user.<br>8. Log in as admin.<br>9. Assign ticket to helpdesk technician. | Full API workflow completes successfully without authorization or data errors. | Integration | High |
| API-E2E-002 | Multiple APIs | POST / GET | Verify admin can retrieve created users after user creation | Admin is logged in | Create user and create helpdesk body | 1. Create normal user.<br>2. Create helpdesk technician.<br>3. Send GET `/api/admin/users`. | Both created users appear in the users list. | Integration | High |
| API-E2E-003 | Multiple APIs | POST | Verify logout prevents reuse of protected admin API | Admin is logged in | None | 1. Log in as admin.<br>2. Send logout request.<br>3. Try creating user using same session/token. | API blocks create user request after logout. | Security | High |

## 9. API Response and Header Checks

| TC ID | API | Method | Scenario | Preconditions | Request Data | Steps | Expected Result | Type | Priority |
|---|---|---|---|---|---|---|---|---|---|
| API-RESP-001 | All APIs | Multiple | Verify API returns JSON response | API is available | Valid request body | 1. Send valid request.<br>2. Review response headers and body. | Response body is valid JSON and `Content-Type` is application/json or compatible. | API Standard | Medium |
| API-RESP-002 | All APIs | Multiple | Verify successful POST requests return proper success status | Valid authenticated request | Valid request body | 1. Send valid POST request.<br>2. Review status code. | API returns expected success status such as 200 or 201. | API Standard | Medium |
| API-RESP-003 | Protected APIs | Multiple | Verify unauthorized requests return proper error status | No authentication | Valid request body | 1. Clear token/cookies.<br>2. Send request to protected endpoint. | API returns 401 Unauthorized or equivalent. | Security | High |
| API-RESP-004 | Admin APIs | Multiple | Verify forbidden requests return proper error status | Normal user is logged in | Valid request body | 1. Log in as normal user.<br>2. Access admin-only API. | API returns 403 Forbidden or equivalent. | Security | High |
| API-RESP-005 | Validation APIs | Multiple | Verify validation errors include useful message | Authenticated user | Invalid request body | 1. Send request with missing or invalid fields.<br>2. Review error body. | API returns clear validation message explaining the issue. | Validation | Medium |