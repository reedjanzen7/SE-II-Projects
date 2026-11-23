# Feature: maintaining the company

**Feature ID:** 1  
**Branch pattern:** `feature/1-mainaining-the-company`  
**Status:** Draft  
**Created:** 11/23/2026 
**Input:** This feature for is mainaining the company of that runs the invoicing projects, so customers can see their info.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-1.1: Adding company information
**As a** company manager  
**I want to** be able to add company information 
**So that** customers know the most up to date information about our company

**Priority:** P1  
**Independent test:** Customers would like to have up to date information on a company before they work with them. 
**Acceptance scenarios:** see US-1.1 under Acceptance Criteria

### US-1.2: Editing company information
**As a** company manager  
**I want to** be able to edit company information 
**So that** customers know the most up to date information about our company

**Priority:** P1  
**Independent test:** Customers would like to have up to date information on a company before they work with them. 
**Acceptance scenarios:** see US-1.2 under Acceptance Criteria

### US-1.3: Archiving company information
**As a** company manager  
**I want to** be able to archive old company information 
**So that** customers know the most up to date information about our company

**Priority:** P1  
**Independent test:** Customers would like to have up to date information on a company before they work with them. 
**Acceptance scenarios:** see US-1.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain the company 
- **FR-002**: Users MUST be able to view the public company information
- **FR-003**: All users MUST NOT be able to maintain the company information

---

## Assumptions

- The company already has all this information in the table
- This information shouldn't be updated very much, and is important to the company, so only the manager should be able to maintain it

---

## Edge Cases

- Empty required field → keeps the previous data for that field and alerts user that it was blank 
- Cross-user access → they aren't able to access the maintaining company page
- Duplicate / invalid input → prompt info to be re-written

---

## Success Criteria

- **SC-001**: Every Gherkin scenario has at least one automated test before merge
- **SC-002**: Only manager can access the page

---

## Key Entities

- **website**: The companies link to the website; displays public information about the company.
- **banking_info**: The companies banking account that other companies pay too; this is not public informatio1.

---

## Data Model Requirements

### `company_information` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `name` | string | added manually |
| `address` | string | added manually |
| `website_url` | string | added manually |
| `phone_number` | int | added manually |
| `email` | string | added manually |
| `banking_info` | string | added manually |

---

## Acceptance Criteria

### US-1.1: Adding company information

#### Scenario: Manager tries to add information
*   **Given** the manager logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can add infomation about the company

#### Scenario: Employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the company

### US-1.2: Editing company information

#### Scenario: Manager tries to edit information
*   **Given** the manager logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit infomation about the company

#### Scenario: Employee tries to edit information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the company

### US-1.3: Archiving company information

#### Scenario: Manager tries to archive information
*   **Given** the manager logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can archive infomation about the company

#### Scenario: Employee tries to archive information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the company

---

## Data Ownership

- The companies information is maintained by the company manager
- Company manager must keep all the information up to date

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
- Managing employees
- Managing customers

---