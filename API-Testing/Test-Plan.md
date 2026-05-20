# Test_Plan.md

# API Test Plan — AI-Powered IT Helpdesk Ticketing System

## 1. Objective

| Section | Details |
|---|---|
| Objective | Validate the API functionality for the AI-Powered IT Helpdesk Ticketing System using Postman. |
| Main Goal | Ensure authentication, logout, user creation, ticket creation, user retrieval, and ticket assignment APIs work correctly. |
| Testing Focus | Functional testing, validation testing, role-based access testing, authentication/session testing, negative testing, and API response verification. |

## 2. Product Overview

| Item | Details |
|---|---|
| Product Name | AI-Powered IT Helpdesk Ticketing System |
| Application Type | Web application with REST APIs |
| Main Users | Admin, Helpdesk Technician, Normal User |
| API Testing Tool | Postman |
| Local Server | `http://localhost:9090` |
| Tested Area | Authentication, Admin User Management, Ticket Creation, Ticket Assignment |

## 3. Scope of API Testing

| Scope Area | Included |
|---|---|
| Login API | Validate admin login, normal user login, invalid login, missing field validation |
| Logout API | Validate authenticated logout and session/token invalidation |
| Create User API | Validate admin can create normal users and helpdesk technicians |
| Get All Users API | Validate only admin can retrieve all user details |
| Ticket Creation API | Validate normal user can create tickets |
| Ticket Assignment API | Validate admin can assign tickets to helpdesk technicians |
| Role-Based Access | Validate normal users cannot access admin-only APIs |
| Validation | Validate missing fields, invalid data, duplicate email, invalid ticket ID, and invalid user ID |
| Security | Validate protected APIs require authentication |

## 4. Out of Scope

| Area | Reason |
|---|---|
| UI Testing | This test plan is focused only on API testing through Postman |
| Performance Testing | Load and stress testing are not included |
| Automation Testing | Automated API scripts are not included in this phase |
| Database Testing | Direct database validation is not included unless required |
| Third-Party API Testing | No external integrations are included |
| Mobile API Testing | Mobile-specific testing is not included |

## 5. API Endpoints Covered

| API Name | Method | Endpoint | Access |
|---|---|---|---|
| Login | POST | `/api/auth/login` | Admin, Helpdesk, User |
| Logout | POST | `/api/auth/logout` | Authenticated users |
| Create User | POST | `/api/admin/users` | Admin only |
| Get All Users | GET | `/api/admin/users` | Admin only |
| Create Ticket | POST | `/api/tickets` | Authenticated user |
| Assign Ticket | POST | `/api/tickets/{ticketid}/assign` | Admin only |

## 6. Test Environment

| Item | Details |
|---|---|
| Environment | Local development environment |
| Base URL | `http://localhost:9090` |
| API Client | Postman |
| Browser Tools | Chrome DevTools / Firefox DevTools if needed |
| Data Format | JSON |
| Authentication | Login session, cookie, bearer token, or server-managed session depending on implementation |
| Operating System | Tester machine local OS |
| Server Port | `9090` |

## 7. Test Data

| Role | Email | Password | Notes |
|---|---|---|---|
| Admin | `admin@gmail.com` | `adminexample` | Used for admin-only API testing |
| Normal User | `user@gmail.com` | `user123` | Created through admin API |
| Helpdesk Technician | `helpdesk@gmail.com` | `desk123` | Created through admin API |
| Invalid User | `invalid@gmail.com` | `wrongpass` | Used for negative login testing |

## 8. Request Headers

| Header | Value |
|---|---|
| Content-Type | `application/json` |
| Accept | `application/json` |
| Authorization | Required only if API uses bearer token |
| Cookie | Required only if API uses session cookie |

## 9. Testing Strategy

| Strategy | Description |
|---|---|
| Positive Testing | Verify APIs work with valid request body, valid role, and valid authentication |
| Negative Testing | Verify APIs fail with invalid credentials, missing fields, wrong roles, invalid IDs, and duplicate data |
| Role-Based Testing | Verify admin-only APIs cannot be accessed by normal users or unauthenticated users |
| Validation Testing | Verify required fields and data formats are enforced |
| Session Testing | Verify logout prevents further access using the same session/token |
| Integration Testing | Verify created users can log in, created tickets can be assigned, and assigned tickets reference valid helpdesk users |
| Regression Testing | Re-run critical API tests after bug fixes or code changes |

## 10. Entry Criteria

| Criteria | Status |
|---|---|
| API server is running on `localhost:9090` | Required |
| Admin test account exists | Required |
| Postman is installed and configured | Required |
| Base URL is confirmed | Required |
| Required APIs are available | Required |
| Test data is prepared | Required |

## 11. Exit Criteria

| Criteria | Expected Condition |
|---|---|
| Critical APIs Tested | Login, logout, user creation, user retrieval, ticket creation, and ticket assignment are tested |
| High Priority Tests | All high-priority test cases are executed |
| Critical Bugs | No open critical or high-severity API bugs remain |
| Role Access | Admin-only and user-only restrictions are validated |
| Test Evidence | Postman screenshots or exported collection results are saved |
| Final Report | API test execution summary is documented |

## 12. Risks and Mitigation

| Risk | Impact | Mitigation |
|---|---|---|
| Admin-only APIs accessible by normal users | Security risk | Test every admin endpoint with admin, normal user, helpdesk, and unauthenticated sessions |
| Logout does not invalidate session/token | Unauthorized continued access | Test protected endpoint immediately after logout |
| Duplicate users allowed | Data integrity issue | Add duplicate email test cases |
| Ticket assignment accepts invalid technician ID | Incorrect assignment | Validate invalid, blank, and non-helpdesk user IDs |
| Ticket creation accepts missing fields | Poor data quality | Test blank and missing description, priority, and category |
| Field casing mismatch such as `Priority` vs `priority` | API request failure or inconsistent data | Confirm accepted payload schema with developer |
| No clear error messages | Hard to debug API failures | Validate response body contains useful error message |

## 13. Deliverables

| Deliverable | Description |
|---|---|
| API Test Plan | Defines scope, strategy, environment, and risks |
| API Test Cases | Detailed API test cases in Markdown table format |
| Bug Reports | Defects found during Postman testing |
| Postman Collection | Collection of tested requests |
| Test Evidence | Screenshots or exported Postman run results |
| Test Summary Report | Final execution summary with pass/fail status |