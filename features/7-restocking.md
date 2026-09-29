# Feature:

**Feature ID:** 7  
**Branch pattern:** `feature/7-restocking`  
**Status:** Draft  
**Created:** 9/28/2026  
**Input:** This feature is how employees restock the warehouse, it can be dome manually or automatically.
**Depends on:** [Feature 3 — Suppliers](3-suppliers.md), [Feature 4 — Supplier Order Form](4-supplier-order-form.md)

---

## User Stories

### US-7.1: Automatic Restock

**As a** item 
**I want to** automatically notify the supplier for more of an item if inventory amount + quantity on order is less than the items set minium
**So that** the warehouse won't run out of inventory

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-7.1 under Acceptance Criteria

### US-7.2: Manaully Restock

**As a** warehouse manager 
**I want to** be able to easly notify a supplier for more of an item
**So that** the warehouse won't run out of inventory

**Priority:** P1  
**Independent test:** <how to verify this story alone, in one sentence>  
**Acceptance scenarios:** see US-7.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST automatically restock items
- **FR-002**: Users MUST be able to see the orders placed

---



## Key Entities

- **Supplier**: the compainy who supplies items for the warehouse
- **Supplier Form**: The form that supplier fills out 
- **Items**: The thing that is sold in the warehouse; the inventory is fulled of them.

---



## Data Model Requirements



### `resstocking_status` table


| Field | Type       | Rules          |
| ----- | ---------- | -------------- |
| `number_items_order`  | INTEGER PK | Auto-increment |
| `items_ordered`   | Item Array          | Auto created from orders              |




### Associations (if known)

- 1-inventory
- 2-items
- 4-supplier-order-form

---



## Acceptance Criteria



### US-7.1: Automatic Restock



#### Scenario: Restock order successfully

- **Given** an item quantity is below the items min
- **When** system sees it is below the min
- **Then** it automatically orders more items up to the max of items



#### Scenario: Item quantity was wrong

- **Given** the system automatically placed a new order, but the item quantity was wrong
- **When** the shipment arraives or error is noticed
- **Then** the can fix the error in the system
- **And** cancle the order or hold on to the extra order



### US-7.2: Manaully Restock



#### Scenario: They need extra of an item

- **Given** a customer needs a large amount of an item
- **When** manager notices
- **Then** they can manaully order extra of an item



#### Scenario: Orderd the wrong item

- **Given** manager orders extra of the wrong item
- **When** they notice
- **Then** the order can try and be canceled or hold on to the extra order

