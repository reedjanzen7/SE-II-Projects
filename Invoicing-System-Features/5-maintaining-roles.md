# Feature: maintaining roles

**Feature ID:** 5
**Branch pattern:** `feature/5-mainaining-roles`  
**Status:** Draft  
**Created:** 11/24/2026 
**Input:** This feature for is mainaining the different roles of an employee.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-5.1: Adding role
**As a** clerk or higher level employee  
**I want to** be able to add a role
**So that** the company has the the best roles that fit for a project.

**Priority:** P1  
**Independent test:** roles in the company or in different projects will change, so roles need to be able to be maintained
**Acceptance scenarios:** see US-5.1 under Acceptance Criteria

### US-5.2: Editing role
**As a** clerk or higher level employee  
**I want to** be able to edit a role
**So that** the company has the the best roles that fit for a project.

**Priority:** P1  
**Independent test:** roles in the company or in different projects will change, so roles need to be able to be maintained
**Acceptance scenarios:** see US-5.2 under Acceptance Criteria

### US-5.3: Archiving role 
**As a** clerk or higher level employee  
**I want to** be able to archive a un-used role
**So that** the company has the the best roles that fit for a project.

**Priority:** P1  
**Independent test:** roles in the company or in different projects will change, so roles need to be able to be maintained
**Acceptance scenarios:** see US-5.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain the roles 
- **FR-002**: All users MUST NOT be able to maintain roles

---

## Assumptions

- TheThe invoicing company has a way to manage paying employees
- The roles need to be able to be maintained becuase there maybe a need to change them for a project 

---

## Edge Cases

- Empty required field → keeps the previous data for that field and alerts user that it was blank 
- Cross-user access → they aren't able to access the maintaining company page
- Duplicate / invalid input → prompt info to be re-written

---

## Success Criteria

- **SC-001**: Every Gherkin scenario has at least one automated test before merge
- **SC-002**: Everyone can see their own role
- **SC-003**: Only higher level eployees, like project leads can edit the roles

---

## Key Entities

- ****: How much should be spent on the project
- ****: What is going on in the project currently

---

## Data Model Requirements

### `company_information` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `name` | string | added manually |
| `standard_rate` | int | added manually |


### Associations
- ProjectRole : The role connected to the project

---

## Acceptance Criteria

### US-4.1: Adding project information

#### Scenario: A clerk or high level employee tries to add a role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can add a role

#### Scenario: Lower level employee tries to add a role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for roles

### US-4.2: Editing project information

#### Scenario: A clerk or high level employee tries to edit a role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit a role

#### Scenario: Lower level employee tries to edit a role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for roles

### US-4.3: Archiving project information

#### Scenario: A clerk or high level employee tries to archive a role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit a role

#### Scenario: Lower level employee tries to archive a role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for roles

---

## Data Ownership

- Company manager or a office clerk manages the different roles in the company

---

## API Requirements

- The system MUST support information to be added
- The system MUST support information to be edited
- The system MUST support information to be archived
- The system MUST limit only to a clerk or high level to be able to maintain the customers information

---

## Screen Requirements

- 

---

## Definition of Done

- All users stories are completed
- All the information in the table can be maintained
- Only the clerks and high level employees can edit the information

---

## Out of Scope

- Managing information not listed in the table
- Managing payment
- Managing invoices
- Managing employees
- Managing the company

---