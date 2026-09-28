# Feature: Customer Order Form

**Feature ID:** 6  
**Branch pattern:** `feature/6-customer-order-form`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** One sentence — This feature is the the form that the customer will fill out when creating an order and gets put into data base.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-6.1: Filling out form

**As a** customer
**I want to** be able to fill out an Customer Order Form
**So that** the warehouse knows what to send me

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see ### US-N.2 under Acceptance Criteria

### US-6.2: Receiving form

**As a** employee / warehouse manager
**I want to** know when the form is filled out
**So that** I can send them the order

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see ### US-N.2 under Acceptance Criteria

### US-6.3: Form History

**As a** form
**I want to** get saved into a list of past forms
**So that** employees can go see what orders where made in the past

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see ### US-N.2 under Acceptance Criteria

### US-6.4: Form Authorized

**As a** form
**I want to** get authorized by a manager
**So that** manager can check that form is right and should be made

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see ### US-N.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: Customers MUST be able to fill out a form when making an order.
- **FR-002**: System MUST be able to save old forms.
- **FR-003**: System MUST notify managers that form was filled out.

---



## Key Entities

- **Entity**: short description; relationships in plain language
- **Entity**: …

---



## Data Model Requirements



### `supplier_order_form_info` table


| Field              | Type         | Rules                          |
| ------------------ | ------------ | ------------------------------ |
| `customer_number`  | INTEGER      | Auto filled from customer info |
| `po_number`        | Phone number | Auto filled from customer info |
| `customer_address` | Address      | Auto filled from customer info |
| `order_date`       | Date         | Auto filled                    |
| `authorized_by`    | Manager      | Manager approves form          |




### Associations

- 5-customers

---



## Acceptance Criteria



### US-6.1: Filling out form



#### Scenario: requests a new order

- **Given** customer is requesting a new order
- **When** the are creating the order
- **Then** they have to fill out an order form



#### Scenario: typo in form

- **Given** there is a typo in the form
- **When** it is read over when authorized
- **Then** it can be fixed



### US-6.2: Receiving form



#### Scenario: Form received

- **Given** form is received
- **When** manager sees it
- **Then** they can authorize the form



#### Scenario: typo in form

- **Given** there is a typo in the form
- **When** it is read over when authorized
- **Then** it can be fixed



### US-6.3: Form History



#### Scenario: Order Completed

- **Given** the order is completed
- **When** the order is completed
- **Then** form can be put into the form history



#### Scenario: Order Never Completed

- **Given** the order is never cancled or not completed
- **When** decision that it will not be completed is final
- **Then** order can be cancled and put into form history



### US-6.4: Form Authorized



#### Scenario: typo in form

- **Given** there is a typo in the form
- **When** it is read over when authorized
- **Then** it can be fixed



#### Scenario: typo missed in authorization

- **Given** there is a typo in the form
- **When** it is read over when authorized and typo missed
- **Then** it can be fixed later when typo is noticed

