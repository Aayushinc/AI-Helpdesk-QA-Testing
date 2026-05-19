# AI-Powered IT Helpdesk Ticketing System — QA Portfolio

## Project Overview

The **AI-Powered IT Helpdesk Ticketing System** is a web-based IT support platform designed for end users, helpdesk technicians, and admins.

The system allows users to raise IT support tickets, receive AI-assisted troubleshooting suggestions, track ticket progress, and communicate with support staff. Admins and technicians can manage tickets, update statuses, assign technicians, use AI-generated solutions, maintain a Knowledge Base, manage inventory, review audit logs, and handle user accounts.

This repository contains the **manual QA testing documentation** for the project.

---

## Objective

The objective of this QA project is to validate the complete helpdesk workflow from ticket creation to final resolution.

Testing focuses on:

- Functional correctness
- Role-based access control
- Ticket lifecycle workflow
- AI/Knowledge Base solution behavior
- Admin-only escalation logic
- Technician assignment
- User management
- Notifications
- Inventory management
- Audit logging
- Browser compatibility

---

## User Roles

| Role | Description |
|---|---|
| End User | Creates tickets, views own tickets, receives safe AI/KB suggestions, adds comments, and uses Alert if help is still needed |
| Helpdesk Technician | Works on assigned tickets, adds comments, updates ticket status, and uses internal AI support suggestions |
| Admin | Manages users, tickets, KB entries, technician skills, inventory, audit logs, dashboard metrics, and final resolutions |

---

## Application Modules Tested

| Module | Description |
|---|---|
| Authentication | Login, logout, session handling, role-based redirection, unauthorized access prevention |
| Ticket Creation | Create tickets with category, title, description, and priority |
| My Tickets | User ticket tracking and ticket detail view |
| AI + Knowledge Base | AI/KB suggestions for safe issues |
| Escalation Logic | Escalation of sensitive/admin-only requests |
| Ticket Status Workflow | Pending, Assigned, Ongoing, Escalated, Solved, Admin Solved |
| Technician Assignment | Skill-based and manual assignment |
| User Management | Admin creation/edit/deletion of users, technicians, and admins |
| Ticket Comments | User, technician, admin, AI Agent, and system comments |
| Alert Button | User alert when suggested solution does not work |
| Notifications | Admin and technician notifications |
| Knowledge Base | KB search, filter, upload, edit, delete, and visibility |
| AI Playground | AI-generated support history and manual/final solution tracking |
| Admin AI Solutions | Internal AI troubleshooting generation |
| Final Solution | Admin final resolution and Admin Solved workflow |
| Inventory Management | IT asset tracking |
| Audit Logs | Traceability of key system actions |
| Dashboard | Admin/technician operational overview |

---

## Scope of Testing

### In Scope

- User Panel testing
- Admin Panel testing
- Authentication testing
- Ticket creation and tracking
- AI and KB suggestion behavior
- Escalation rules
- Role-based access control
- Ticket comments
- Notifications
- User management
- Inventory management
- Audit logs
- Dashboard metrics
- UI validation
- Browser compatibility on Chrome and Firefox

### Out of Scope

- Mobile app testing
- Automated test scripting
- Load/performance testing
- Security penetration testing
- Third-party integrations not defined in the requirements
- Video-based testing

---

## Test Environment

| Item | Details |
|---|---|
| Application Type | Web Application |
| Browsers | Google Chrome, Mozilla Firefox |
| Tools | Chrome DevTools, Firefox DevTools |
| Testing Type | Manual Testing |
| Test Data | Users, admins, technicians, tickets, KB entries, inventory records |
| Environment | QA/Staging environment |

---

## Testing Strategy

The QA strategy follows a user-centered manual testing approach.

Testing includes:

1. Validating each module independently.
2. Validating end-to-end workflows.
3. Testing positive and negative scenarios.
4. Verifying role-based access restrictions.
5. Testing edge cases and validation rules.
6. Verifying AI/KB safety behavior.
7. Confirming escalation for sensitive requests.
8. Checking audit logs and notifications.
9. Performing regression testing after fixes.

---

## Testing Types

| Testing Type | Purpose |
|---|---|
| Functional Testing | Verify that all features work according to requirements |
| UI Testing | Verify layout, labels, buttons, forms, tables, and messages |
| Validation Testing | Verify required fields and invalid inputs |
| Role-Based Access Testing | Verify each role only accesses allowed features |
| Workflow Testing | Verify ticket lifecycle and status transitions |
| Integration Testing | Verify modules work together correctly |
| Regression Testing | Verify existing functionality after fixes |
| Compatibility Testing | Verify behavior in Chrome and Firefox |
| Negative Testing | Verify invalid or unauthorized actions are blocked |

---

## QA Deliverables

This repository includes the following QA artifacts:

| Deliverable | Description |
|---|---|
| Test Plan | Overall QA approach, scope, tools, risks, and exit criteria |
| Test Scenarios | High-level scenarios for each module |
| Test Cases | Detailed test cases with steps and expected results |
| Checklist | Quick execution checklist for User Panel and Admin Panel |
| Bug Reports | Sample high, medium, and low severity bugs |
| Suggestions | Product improvement and enhancement ideas |
| Risk Analysis | Possible risks and mitigation plans |
| Stakeholder Questions | Requirement gaps and clarification questions |

---

## Repository Structure

```text
AI-Helpdesk-QA-Portfolio/
│
├── README.md
│
├── test-plan/
│   └── Test_Plan.md
│
├── test-cases/
│   └── Test_Cases.md
│
├── checklist/
│   └── QA_Checklist.md
│
├── bug-reports/
│   └── Bug_Reports.md
