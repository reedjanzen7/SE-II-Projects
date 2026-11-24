# Feature: maintaining the company

**Feature ID:** 4
**Branch pattern:** `feature/4-mainaining-projects`  
**Status:** Draft  
**Created:** 11/24/2026 
**Input:** This feature for is mainaining the projects of that customers are paying the company to do.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-N.1: Adding projects information
**As a** clerk or higher level employee  
**I want to** be able to add project information 
**So that** the company knows the most up to date information about the project

**Priority:** P1  
**Independent test:** Employees will need to the most current informaton about a project, so they know how to manage the project
**Acceptance scenarios:** see US-4.1 under Acceptance Criteria

### US-3.2: Editing projects information
**As a** clerk or higher level employee  
**I want to** be able to edit project information 
**So that** the company knows the most up to date information about the project

**Priority:** P1  
**Independent test:** Employees will need to the most current informaton about a project, so they know how to manage the project
**Acceptance scenarios:** see US-4.2 under Acceptance Criteria

### US-3.3: Archiving projects information
**As a** clerk or higher level employee  
**I want to** be able to archive project information 
**So that** the company knows the most up to date information about the project

**Priority:** P1  
**Independent test:** Employees will need to the most current informaton about a project, so they know how to manage the project
**Acceptance scenarios:** see US-4.2 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain the projects 
- **FR-002**: Users MUST be able to view the project information
- **FR-003**: All users MUST NOT be able to maintain the project information

---

## Assumptions

- The customer has already meet and decided the project information
- The project information needs to be maintained becuase the project might need to change

---

## Edge Cases

- Empty required field → keeps the previous data for that field and alerts user that it was blank 
- Cross-user access → they aren't able to access the maintaining company page
- Duplicate / invalid input → prompt info to be re-written

---

## Success Criteria

- **SC-001**: Every Gherkin scenario has at least one automated test before merge
- **SC-002**: Everyone can view the project information
- **SC-003**: Only higher level eployees, like project leads can edit the project information

---

## Key Entities

- **budget**: How much should be spent on the project
- **status**: What is going on in the project currently

---

## Data Model Requirements

### `company_information` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `name` | string | added manually |
| `customerId` | int | added manually |
| `startDate` | date | added manually |
| `endDate` | date | added manually |
| `inital_budget` | cost | added manually |
| `revised_budget` | cost | added manually |
| `customer_ContactId` | int | added manually |
| `status` | string | set to pending, active, or closed |


### Associations
- customer : The company paying for the project
- customer_contact : The customers contact information

---

## Acceptance Criteria

### US-4.1: Adding project information

#### Scenario: A clerk or high level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can add infomation about the project

#### Scenario: Lower level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the project

### US-4.2: Editing project information

#### Scenario: A clerk or high level employee tries to edit information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit infomation about the project

#### Scenario: Lower level employee tries to edit information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the project

### US-4.3: Archiving project information

#### Scenario: A clerk or high level employee tries to archive information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can archive infomation about the project

#### Scenario: Lower level employee tries to archive information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the project

---

## Data Ownership

- The customer provides the data
- A employee must keep all the information up to date

---

## API Requirements

- The system MUST support information to be updated
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