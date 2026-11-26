# Feature: maintaining project time // needs to be finished

**Feature ID:** 7
**Branch pattern:** `feature/7-mainaining-project-time`  
**Status:** Draft  
**Created:** 11/25/2026 
**Input:** This feature is for maintaining the time spent on a project.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-7.1: Adding project time
**As a** employee
**I want to** be able to add project time
**So that** the company can accurately keep track of work spent and done on a project

**Priority:** P1  
**Independent test:** The company needs accurately know how much time was spent on a project to charge cost correctly
**Acceptance scenarios:** see US-7.1 under Acceptance Criteria

### US-7.2: Editing project time
**As a** employee
**I want to** be able to edit project time
**So that** the company can accurately keep track of work spent and done on a project

**Priority:** P1  
**Independent test:** The company needs accurately know how much time was spent on a project to charge cost correctly
**Acceptance scenarios:** see US-7.2 under Acceptance Criteria

### US-7.3: Removing project time 
**As a** employee
**I want to** be able to remove project time
**So that** the company can accurately keep track of work spent and done on a project

**Priority:** P1  
**Independent test:** The company needs accurately know how much time was spent on a project to charge cost correctly
**Acceptance scenarios:** see US-7.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain the project roles 
- **FR-002**: All users MUST NOT be able to maintain project roles

---

## Assumptions

- The invoicing company has a way to manage paying employees
- The project roles need to be able to be maintained becuase there maybe a need to change them for different projects

---

## Edge Cases

- Empty required field → keeps the previous data for that field and alerts user that it was blank 
- Cross-user access → they aren't able to access the maintaining company page
- Duplicate / invalid input → prompt info to be re-written

---

## Success Criteria

- **SC-001**: Every Gherkin scenario has at least one automated test before merge
- **SC-002**: Everyone can see their own project role
- **SC-003**: Only higher level eployees, like project leads can edit the project roles

---

## Key Entities

- **rate**: The rate that this role is getting paid for this project

---

## Data Model Requirements

### `project_time` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `projectId` | int | added manually | 
| `date` | date | added manually | 
| `hours` | int | added manually | 
| `project_role_assignmentId` | int | added manually | 
| `inv_Line_itemId` | int | added manually | 
| `status` | statuc type | set to entered, approved or denayed | 


### Associations
- role : The role that this project role is based off of
- project : The project this role is for

---

## Acceptance Criteria

### US-6.1: Adding project roles

#### Scenario: A clerk or high level employee tries to add a project role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can add a project role

#### Scenario: Lower level employee tries to add a project role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for project roles

### US-6.2: Editing roles

#### Scenario: A clerk or high level employee tries to edit a project role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit a project role

#### Scenario: Lower level employee tries to edit a project role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for project roles

### US-6.3: Archiving roles

#### Scenario: A clerk or high level employee tries to archive a project role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit a project role

#### Scenario: Lower level employee tries to archive a project role
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for project roles

---

## Data Ownership

- The project manager manages the different project roles in the company

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