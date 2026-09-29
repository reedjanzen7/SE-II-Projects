# Feature:

**Feature ID:** 7 8
**Branch pattern:** `feature/8-bill-of-lading`  
**Status:** Draft  
**Created:** 9/28/2026  
**Input:** This is the legally binding contract automatically made from the other forms.
**Depends on:** [Feature 6 — Customer Order Form](6-customer-order-form.md), [Feature 4 — Supplier Order Form](4-supplier-order-form.md)  

---

## User Stories

### US-8.1: Automatically Creating the Bill of Lading

**As a** warehouse system 
**I want to** automatically create a bill of lading when a supplier order form or customer order form is made
**So that** the warehouse stays out of legal trouble

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-8.1 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST automatically create this when other form is made
- **FR-002**: System MUST have customers agree to it
- **FR-003**: System MUST have suppliers agree to it
- **FR-004**: System MUST automatically create a Delivery Date

---



## Key Entities

- **Supplier Form**: The form that supplier fills out 
- **Customer Form**: The form that customer fills out 

---



## Data Model Requirements



### `bill_of_lading_info` table


| Field              | Type         | Rules                                   |
| ------------------ | ------------ | --------------------------------------- |
| `customer_number`  | INTEGER      | Auto filled from form                   |
| `po_number`        | Phone number | Auto filled from form                   |
| `customer_address` | Address      | Auto filled from form                   |
| `order_date`       | Date         | Auto filled from form                   |
| `deliver_date`     | Date         | Automatically create                    |
| `received_by`      | Date         | Created by customer when order arraives |




### Associations

- 4-supplier-order-form
- 6-customer-order-form

---



## Acceptance Criteria



### US-8.1: Automatically Creating the Bill of Lading



#### Scenario: Order is created

- **Given** an order is created
- **When** it is created
- **Then** it automatically creates the bill of lading



#### Scenario: User doesn't agree to it

- **Given** the user doesn't agree to the bill of lading while making an order
- **When** order is made
- **Then** it doesn't go through

