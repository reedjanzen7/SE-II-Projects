# Feature: Reporting

**Feature ID:** 9  
**Branch pattern:** `feature/9-reporting`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** One sentence — This is a feature for the reports that need to get sent back to the manager.  
**Depends on:** [Feature 4 — Supplier Order Form](4-supplier-order-form.md), [Feature 3 — Suppliers](3-suppliers.md) 

---

## User Stories

### US-9.1: Supplier Amount Sent

**As a Warehouse manager**  
**I want to receive a report of how much of an item was sent to the warehouse**  
**So that I can check that the right amount was recieved**

**Priority:** P1  
**Independent test:** The managers should be able to check that they were sent the right number of items for the inventory  
**Acceptance scenarios:** see US-9.1 under Acceptance Criteria

### US-9.2: Amount of Items Packed into Deilvery

**As a Warehouse manager**  
**I want to receive a report of how many items were packed into the deilvery truck**  
**So that I can check that the right amount is getting sent**

**Priority:** P1  
**Independent test:** The managers should be able to check that they are sending the right number of items for the customer  
**Acceptance scenarios:** see US-9.2 under Acceptance Criteria

### US-9.3: Amount of Items Deilvered

**As a Warehouse manager**  
**I want to receive a report of how much of an item was deilvered to the customer**  
**So that I can check that the right amount was sent**

**Priority:** P1  
**Independent test:** The managers should be able to check that the right amount was sent and none of it was lost somewhere in the process.  
**Acceptance scenarios:** see US-9.3 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST be able to send these reports electronically
- **FR-002**: Users MUST be able to send these reports to the manager
- **FR-003**: Customers and suppliers MUST NOT be able to sent these reports.

---



## Key Entities

- **Employees**: The group of people who work at the warehouse; they help send in the reports

---



## Data Model Requirements



### `reporting_table` table


| Field            | Type       | Rules                                |
| ---------------- | ---------- | ------------------------------------ |
| `report-id`      | INTEGER PK | Auto-increment                       |
| `report-type`    | String     | Based off user who inputs it         |
| `employee-name`  | String     | User who inputs data's name          |
| `date`           | Date       | Date report was made                 |
| `item`           | String     | Must connect with the amount of item |
| `amount-of-item` | Int        | Must connect with the item name      |




### Associations (if known)

- inventory
- employees

---



## Acceptance Criteria



### US-9.1: Supplier Amount Sent



#### Scenario: Good Supplier Report

- **Given** employee unloads items into warehouse
- **When** employee counts up the items
- **Then** inputs the number into the system
- **And** it matches up with amount supplier sent



#### Scenario: Bad Supplier Report

- **Given** employee unloads items into warehouse
- **When** employee counts up the items
- **Then** inputs the number into the system
- **And** it doesn't match up with the amount supplier sent



### US-9.2: Amount of Items Packed into Deilvery



#### Scenario: Good Loading the Deilvery Report

- **Given** employee loads items into deilvery truck
- **When** employee counts up the items
- **Then** inputs the number into the system
- **And** it matches up with amount in the data base



#### Scenario: Bad Loading the Deilvery Report

- **Given** employee loads items into deilvery truck
- **When** employee counts up the items
- **Then** inputs the number into the system
- **And** it doesn't matche up with amount in the data base



### US-9.3: Amount of Items Deilvered



#### Scenario: Good Deilvery Report

- **Given** deilver unloads items from truck
- **When** deilver counts up the items
- **Then** inputs the number into the system
- **And** it matches up with amount in the data base



#### Scenario: Bad Deilvery Report

- **Given** deilver unloads items from truck
- **When** deilver counts up the items
- **Then** inputs the number into the system
- **And** it doesn't matche up with amount in the data base

