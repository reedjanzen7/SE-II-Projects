# Feature: Employees

**Feature ID:** 11  
**Branch pattern:** `feature/11-employees`  
**Status:** Draft  
**Created:** 9/28/2026  
**Input:** This is a feature for the employees on the warehouse floor and waht access they have 
**Depends on:** [Feature 3 — Suppliers](3-suppliers.md)  

---

## User Stories

### US-11.1: Unloading

**As a** employee
**I want to** be able to unload trucks and move items into the warehouse, editing items info in the process
**So that** I can do my job

**Priority:** P1  
**Independent test:** Employees need to able to update the item info so the system knows where the items are
**Acceptance scenarios:** see US-11.1 under Acceptance Criteria

### US-11.2: Shipping

**As a** employee
**I want to** be able to load orders into a truck and update it on the system
**So that** I can do my job

**Priority:** P1  
**Independent test:** Employees need to able to update the item info so the system knows where the items are
**Acceptance scenarios:** see US-11.2 under Acceptance Criteria

### US-11.3: manage Item

**As a** employee
**I want to**  be able to manage items
**So that** I can do my job

**Priority:** P1  
**Independent test:** Employees need to able to update the item info so the system knows where the items are
**Acceptance scenarios:** see US-11.3 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST be able to edit invenotry items
- **FR-002**: Employees MUST be able to edit items
- **FR-003**: Customers and suppliers MUST NOT be able to edit items

---



## Key Entities

- **Employees**: The group of people who work at the warehouse; they are the employees

---



## Data Model Requirements



### `employee_info` table


| Field          | Type         | Rules                            |
| -------------- | ------------ | -------------------------------- |
| `employee_id`  | INTEGER PK   | Auto-increment                   |
| `email`        | Email        | Created when employee gets hired |
| `phone_number` | Phone Number | Created when employee gets hired |
| `manger`       | bool         | Gives them more access           |


---



## Acceptance Criteria



### US-11.1: Unloading



#### Scenario: item unloaded

- **Given** a supplier truck shows
- **When** items unload
- **Then** item information, like loaction, can be edited



#### Scenario: Wrong item edited

- **Given** the wrong item is edited
- **When** the mistake is relized
- **Then** the error can be fixed



### US-11.2: Shipping



#### Scenario: item shipped

- **Given** items are shipped
- **When** items are loaded
- **Then** item information, like loaction, can be edited



#### Scenario: Wrong item edited

- **Given** the wrong item is edited
- **When** the mistake is relized
- **Then** the error can be fixed



### US-11.3: Manage Item



#### Scenario: item edited

- **Given** an item needs to be edited
- **When** item is edited
- **Then** item information, like loaction, can be edited



#### Scenario: Wrong item edited

- **Given** the wrong item is edited
- **When** the mistake is relized
- **Then** the error can be fixed

