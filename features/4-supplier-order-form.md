# Feature: Supplier Order Form

**Feature ID:** 4  
**Branch pattern:** `feature/4-supplier-order-form`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** This feature is the the form that the suppliers fill out when creating an order and gets put into data base.
**Depends on:** [Feature 3 — Suppliers](3-suppliers.md)

---

## User Stories

### US-4.1: Filling out form

**As a** supplier
**I want to** be able to fill out an Supplier Order Form
**So that** the warehouse knows what I am shipping

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-4.2 under Acceptance Criteria

### US-4.2: Receiving form

**As a** employee / warehouse manager
**I want to** know when the form is filled out
**So that** I know an order is coming

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-4.2 under Acceptance Criteria

### US-4.3: Form History

**As a** form
**I want to** get saved into a list of past forms
**So that** employees can go see what orders where made in the past

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-4.2 under Acceptance Criteria

### US-4.4: Form Authorized

**As a** form
**I want to** get authorized by a manager
**So that** manager can check that form is right and should be made

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-4.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: Suppliers MUST be able to fill out a form when making an order.
- **FR-002**: System MUST be able to save old forms.
- **FR-003**: System MUST notify managers that form was filled out.

---



## Key Entities

- **Supplier**: the compainy who supplies items for the warehouse
- **Supplier Form**: The form that supplier fills out 

---



## Data Model Requirements



### `supplier_order_form_info` table


| Field              | Type         | Rules                          |
| ------------------ | ------------ | ------------------------------ |
| `customer_number`  | INTEGER      | Auto filled from supplier info |
| `po_number`        | Phone number | Auto filled from supplier info |
| `supplier_address` | Address      | Auto filled from supplier info |
| `order_date`       | Date         | Auto filled                    |
| `authorized_by`    | Manager      | Manager approves form          |




### Associations

- 3-suppliers

---



## Acceptance Criteria



### US-4.1: Filling out form



#### Scenario: Sending new order

- **Given** supplier is sending a new order
- **When** they send the order
- **Then** they have to fill out an order form



#### Scenario: typo in form

- **Given** there is a typo in the form
- **When** it is read over when authorized
- **Then** it can be fixed



### US-4.2: Receiving form



#### Scenario: Form received

- **Given** form is received
- **When** manager sees it
- **Then** they can authorize the form



#### Scenario: typo in form

- **Given** there is a typo in the form
- **When** it is read over when authorized
- **Then** it can be fixed



### US-4.3: Form History



#### Scenario: Order Completed

- **Given** the order is completed
- **When** the order is completed
- **Then** form can be put into the form history



#### Scenario: Order Never Completed

- **Given** the order is never cancled or not completed
- **When** decision that it will not be completed is final
- **Then** order can be cancled and put into form history



### US-4.4: Form Authorized



#### Scenario: typo in form

- **Given** there is a typo in the form
- **When** it is read over when authorized
- **Then** it can be fixed



#### Scenario: typo missed in authorization

- **Given** there is a typo in the form
- **When** it is read over when authorized and typo missed
- **Then** it can be fixed later when typo is noticed

