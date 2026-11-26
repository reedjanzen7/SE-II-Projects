# Feature: maintaining customers

**Feature ID:** 3  
**Branch pattern:** `feature/3-mainaining-customers`  
**Status:** Draft  
**Created:** 11/23/2026 
**Input:** This feature is for maintaining the customer of that runs the invoicing projects, so customers can see their info.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-3.1: Adding customer information
**As a** clerk or higher level employee  
**I want to** be able to add customer information 
**So that** the company knows the most up to date information about our customer

**Priority:** P1  
**Independent test:** Employees will need to be able to contact the customer to send invoices or bring up concerns, and they will need up to date information
**Acceptance scenarios:** see US-3.1 under Acceptance Criteria

### US-3.2: Editing customer information
**As a** clerk or higher level employee  
**I want to** be able to edit customer information 
**So that** the company knows the most up to date information about our customer

**Priority:** P1  
**Independent test:** Employees will need to be able to contact the customer to send invoices or bring up concerns, and they will need up to date information
**Acceptance scenarios:** see US-3.2 under Acceptance Criteria

### US-3.3: Archiving customer information
**As a** clerk or higher level employee  
**I want to** be able to archive customer information 
**So that** the company knows the most up to date information about our customer

**Priority:** P1  
**Independent test:** Employees will need to be able to contact the customer to send invoices or bring up concerns, and they will need up to date information
**Acceptance scenarios:** see US-3.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain the customer information
- **FR-002**: Employees MUST be able to view the customer information
- **FR-003**: All users MUST NOT be able to maintain the customer information

---

## Assumptions

- The customer already has all this information in the table
- The customer's company will have a contact person
- THe customer's information may change, as other companies might do things differently

---

## Edge Cases

- Empty required field → keeps the previous data for that field and alerts user that it was blank 
- Cross-user access → they aren't able to access the maintaining customer page
- Duplicate / invalid input → prompt info to be re-written

---

## Success Criteria

- **SC-001**: Every Gherkin scenario has at least one automated test before merge
- **SC-002**: All employees can view this information
- **SC-003**: Only clerks and high level employees can edit this

---

## Key Entities

- **customer**: The company that we are creating a project for and is a customer.
- **customer contact**: The contact we have at a company to comnunicate.
- **billing terms**: The terms we agreed with the customer to bill them.

---

## Data Model Requirements

### `customer` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `name` | string | added manually |
| `address` | string | added manually |
| `companys_number` | int | added manually |
| `billing_terms` | string | added manually |

### `customer_contact` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `customerId` | int | added manually |
| `name` | string | added manually |
| `phone_number` | int | added manually |
| `email` | string | added manually |

---

## Acceptance Criteria

### US-3.1: Adding customer information

#### Scenario: A clerk or high level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can add infomation about the customer

#### Scenario: Lower level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the customer

### US-3.2: Editing customer information

#### Scenario: A clerk or high level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can edit infomation about the customer

#### Scenario: Lower level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the customer

### US-3.3: Archiving customer information

#### Scenario: A clerk or high level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can archive infomation about the customer

#### Scenario: Lower level employee tries to add information
*   **Given** the employee logs onto the data base
*   **When** they go to maintaince screen
*   **Then** they can't access the mainaince screen for the customer

---

## Data Ownership

- The customer provides the data
- A clerk must keep all the information up to date

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