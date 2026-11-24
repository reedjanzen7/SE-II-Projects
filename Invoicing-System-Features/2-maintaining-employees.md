# Feature: maintaining employees

**Feature ID:** 2               // Should an employee be able to manage their own stuff?
**Branch pattern:** `feature/2-mainaining-the-employees`  
**Status:** Draft  
**Created:** 11/23/2026 
**Input:** This feature for is mainaining the employees that work at the company.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-2.1: Adding employee information
**As a** company manager
**I want to** be able to add employee information 
**So that** information about our employee says up to date

**Priority:** P1  
**Independent test:** Employee information should stay up to date so others in the company can know how to conntact them and what they do.
**Acceptance scenarios:** see US-2.1 under Acceptance Criteria

### US-2.2: Editing employee information
**As a** company manager
**I want to** be able to edit employee information 
**So that** information about our employee says up to date

**Priority:** P1  
**Independent test:** Employee information should stay up to date so others in the company can know how to conntact them and what they do.
**Acceptance scenarios:** see US-2.2 under Acceptance Criteria

### US-2.3: Archiving employee information
**As a** company manager
**I want to** be able to archive old employee information 
**So that** information about our employee says up to date

**Priority:** P1  
**Independent test:** Employee information should stay up to date so others in the company can know how to conntact them and what they do.
**Acceptance scenarios:** see US-2.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain the employees information 
- **FR-002**: Employees MUST be able to view other employees information
- **FR-003**: All users MUST NOT be able to maintain the employee information

---

## Assumptions

- The employee already has all this information in the table
- Employees should be able to see this information to connect with their fellow employees

---

## Edge Cases

- Empty required field → keeps the previous data for that field and alerts user that it was blank 
- Cross-user access → they aren't able to access the maintaining employee page
- Duplicate / invalid input → prompt info to be re-written

---

## Success Criteria

- **SC-001**: Every Gherkin scenario has at least one automated test before merge
- **SC-002**: Only manager can access the page//

---

## Key Entities

- **title**: The title of what the employees job is.

---

## Data Model Requirements

### `employee_information` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `name` | string | added manually |
| `title` | string | added manually |
| `email` | string | added manually |

### Associations
- ProjectRoleAssign: that employees role in a project

---

## Acceptance Criteria

### US-2.1: Adding employee information

#### Scenario: Manager tries to add information
*   **Given** the manager logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can add infomation about the employee

#### Scenario: Employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the employee

### US-2.2: Editing employee information

#### Scenario: Manager tries to edit information
*   **Given** the manager logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit infomation about the employee

#### Scenario: Employee tries to edit information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the employee

### US-2.3: Archiving employee information

#### Scenario: Manager tries to archive information
*   **Given** the manager logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can archive infomation about the employee

#### Scenario: Employee tries to archive information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the employee

---

## Data Ownership

- The companies information is maintained by the company manager
- company manager must keep all the information up to date

---

## API Requirements

- The system MUST support information to be updated
- The system MUST support information to be edited
- The system MUST support information to be archived
- The system MUST limit only the manager to maintaining the companies information

---

## Screen Requirements

- 

---

## Definition of Done

- All users stories are completed
- All the information in the table can be maintained
- Only the manager can edit the information

---

## Out of Scope

- Managing information not listed in the table
- Managing payment
- Managing invoices
- Managing the company
- Managing customers

---