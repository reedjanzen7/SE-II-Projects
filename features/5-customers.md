# Feature: Suppliers

**Feature ID:** 5  
**Branch pattern:** `feature/5-customer`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** This feature is the customer of the warehouse, where they are about to make an order
**Depends on:** [Feature 6 — Customer Order Form](6-customer-order-form.md)  

---

## User Stories

### US-5.1: Veiwing Warehouses Inventory

**As a** customer
**I want to** be able view the warehouses inventory
**So that** I can see if they have the item I need

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-5.1 under Acceptance Criteria

### US-5.2: Creating an order

**As a** customer
**I want to** be able to create an order
**So that** I can get the items I want

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-5.1 under Acceptance Criteria

### US-5.3: Filling out form

**As a** customer
**I want to** be able to fill out an Customer Order Form when making an order
**So that** the warehouse knows what items I want

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-5.2 under Acceptance Criteria

### US-5.4: View Order Statis

**As a** customer
**I want to** be able to view the order statis
**So that** I know how the order is going

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-5.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST notify warehouse when a customer order is made.
- **FR-002**: Customer MUST be able create an order.
- **FR-003**: System MUST be able to handle many orders at once
- **FR-004**: Customers MUST NOT have the same access to the system that employees have.

---



## Key Entities

- **Customer**: the compainy who buys items form the warehouse
- **Customer Form**: The form that customer fills out 

---



## Data Model Requirements



### `supplier_table` table


| Field              | Type                | Rules                  |
| ------------------ | ------------------- | ---------------------- |
| `customer_number`  | INTEGER PK          | Auto-increment         |
| `po_number`        | Phone number        | User input             |
| `customer_address` | Address             | User input             |
| `current_orders`   | Customer Order Form | User input             |
| `past_orders`      | Customer Order Form | Saved from past orders |




### Associations

- 6-customer-order-form

---



## Acceptance Criteria


### US-5.1: Veiwing Warehouses Inventory



#### Scenario: Viewing items

- **Given** a customer wants to buy something from the warehouse
- **When** they go to the data base
- **Then** they can view the items and quantity of items in the warehouse



#### Scenario: The item they want is out of stock

- **Given** the item the customer wants is out of stock
- **When** they go to the data base
- **Then** they can still put in the order, it just won't happen until the warehouse is restocked



### US-5.2: Creating an order



#### Scenario: Order Created

- **Given** the customer creates an order
- **When** the customer creates it
- **Then** the warehosue will receive the order
- **And** they can complete it



#### Scenario: Order with Typo

- **Given** the order doesn't look quite right
- **When** a manager reviews it
- **Then** they don't have to authorize the order
- **And** they can double check with the customer that they filled it out correctly



### US-5.3: Filling out form



#### Scenario: Order Created

- **Given** the customer creates an order
- **When** they create it
- **Then** they have to fill out a customer order form



#### Scenario: Order with Typo

- **Given** the order form doesn't look quite right
- **When** a manager reviews it
- **Then** they don't have to authorize the order form
- **And** they can double check with the customer that they filled it out correctly



### US-5.4: View Order Statis



#### Scenario: View Order Statis

- **Given** the customer views the order statis
- **When** the system loads it
- **Then** they can view the order and where it is in the process



#### Scenario: Order not Recieved

- **Given** the order never shows up
- **When** the customer relizes this
- **Then** the can check the statis
- **And** if needed they can call the warehouse to further address the issue

