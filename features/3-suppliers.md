# Feature: Suppliers

**Feature ID:** 3  
**Branch pattern:** `feature/3-suppliers`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** One sentence — This feature is the Supplier which allows them to manage the orders they send to the warehouse.  
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-3.1: Getting Notified for a New Order

**As a** supplier
**I want to** get notified if the warehouse needs another shipment
**So that** I can know when to send an order

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see ### US-N.1 under Acceptance Criteria

### US-3.2: Filling out form

**As a** supplier
**I want to** be able to fill out an Supplier Order Form
**So that** the warehouse knows what I am shipping

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see ### US-N.2 under Acceptance Criteria

### US-3.3: Order Recieved

**As a** supplier
**I want to** know when the order is recieved
**So that** I know it made it there

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see ### US-N.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST notify me when another order is needed.
- **FR-002**: System MUST let me fill out the supplier form.
- **FR-003**: System MUST notify me when order was received.
- **FR-004**: System MUST be able to handle many orders at once
- **FR-005**: Suppliers MUST NOT have the same access to the system that employees have.

---



## Key Entities

- **Entity**: short description; relationships in plain language
- **Entity**: …

---



## Data Model Requirements



### `supplier_table` table


| Field              | Type                | Rules                  |
| ------------------ | ------------------- | ---------------------- |
| `customer_number`  | INTEGER PK          | Auto-increment         |
| `po_number`        | Phone number        | User input             |
| `supplier_address` | Address             | User input             |
| `current_orders`   | Supplier Order Form | User input             |
| `past_orders`      | Supplier Order Form | Saved from past orders |




### Associations

- 4-supplier-order-forms

---



## Acceptance Criteria



### US-3.1: Getting Notified for a New Order



#### Scenario: Needing more Stock

- **Given** the warehouse is running low on stock
- **When** it gets to low
- **Then** supplier will get notified
- **And** they can send more supply



#### Scenario: Notification Missed

- **Given** a notification doesn't get sent or gets missed
- **When** items stock gets empty
- **Then** they can check up on the order to see the problem



### US-3.2: Filling out form



#### Scenario: Sending new order

- **Given** supplier is sending a new order
- **When** they send the order
- **Then** they have to fill out an order form



#### Scenario: typo in form

- **Given** there is a typo in the form
- **When** it is read over
- **Then** it can be fixed



### US-3.3: Order Recieved



#### Scenario: Order Recieved

- **Given** the supplier order arriaves at the warehouse
- **When** they start unloading it
- **Then** they can tell the supplier the order was recieved



#### Scenario: Order not Recieved

- **Given** the order never shows up
- **Then** the can notify the supplier

