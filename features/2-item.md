# Feature: Item

**Feature ID:** 2  
**Branch pattern:** `feature/2-item`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** This feature is used for keeping track of the Warehouses items, like viewing and editing items.  
**Depends on:** [Feature 1 — Inventory](1-inventory.md)  

---

## User Stories

### US-2.1: Increasing Item Stock

**As a** employee
**I want to** be able to add more of an item to the inventory
**So that** the inventory is kept up to date

**Priority:** P1  
**Independent test:** New items will get shipped into warehouse from suppliers, so employees must be able to update them.  
**Acceptance scenarios:** see US-2.1 under Acceptance Criteria

### US-2.2: Decreasing Item Stock

**As a** employee
**I want to** be able to decrease some of an item from the inventory
**So that** the inventory is kept up to date

**Priority:** P1  
**Independent test:** Items will be sold to customers or damanged, so employees must be able to update them.  
**Acceptance scenarios:** see US-2.2 under Acceptance Criteria

### US-2.3: Editing Item

**As a** employee
**I want to** be able to edit an item in the inventory
**So that** the inventory is kept up to date

**Priority:** P1  
**Independent test:** Item information could get messed up so employees should be able to go in and fix them, so employees must be able to update them.  
**Acceptance scenarios:** see US-2.3 under Acceptance Criteria

### US-2.4: Viewing Item History

**As a** employee 
**I want to** be able to view the item history
**So that** if something doesn't add up, I can go check what happened in the item history

**Priority:** P1  
**Independent test:** Item information could get messed up so employees should be able to see what happened, so employees must be able to update them.  
**Acceptance scenarios:** see US-2.4 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST give a way to keep track of item info in a organized way.
- **FR-002**: Users MUST be able to manage items.
- **FR-003**: Customers and suppliers MUST NOT be able to manage the items.

---



## Key Entities

- **Items**: The thing that is sold in the warehouse; the inventory is fulled of them.
- **Item Locations**: The loaction of where an item is in the warehouse; it allows the user to know where it is in the warehouse.

---



## Data Model Requirements



### `item_table` table


| Field                        | Type       | Rules                        |
| ---------------------------- | ---------- | ---------------------------- |
| `item_id`                    | INTEGER PK | Auto-increment               |
| `item_amount`                | INTEGER    | User-input                   |
| `deilvered_date`             | DATE       | Auto-created                 |
| `expiration_date`            | DATE       | User-input                   |
| `history`                    | ITEM       | Created after an item update |
| `items_supplier`             | SUPPLIER   | User-input                   |
| `item_location_in_warehouse` | Location   | User-input                   |
| `item_being_deilvered`       | bool       | User-input                   |
| `item_sold`                  | bool       | User-input                   |
| `sold_item_history`          | ITEM       | Created after sold           |
| `deleted_item_history`       | ITEM       | Created after deleted        |




### Associations (if known)

- 2-suppliers

---



## Acceptance Criteria



### US-2.1: Increasing Item Stock



#### Scenario: Increasing Item Stock

- **Given** a new shipment arrives
- **When** employee adds more of an item to inventory
- **Then** system gets updated



#### Scenario: Adding to many of an item

- **Given** a new shipment arrives
- **When** employee adds to many of an item
- **Then** item amount can be edited later to fix this issue



### US-2.2: Decreasing Item Stock



#### Scenario: Damaged item

- **Given** an item is severely damaged
- **When** employee goes to item on data base
- **Then** they can decrease the amount of that item



#### Scenario: Decreasing the wrong item

- **Given** an item is severely damaged
- **When** employee goes to decrease the amount of it, but the does the wrong item
- **Then** old item amount will appear in history so error can be seen



### US-2.3: Editing Item



#### Scenario: Item moved

- **Given** an item is moved to a different part of the warehouse
- **When** employee goes to item on data base
- **Then** they can edit the items location



#### Scenario: Item edited wrong

- **Given** an employee edited the wrong item
- **When** another employee is looks at the item
- **Then** they can look at the history and catch the error



#### Scenario: Item sent off

- **Given** an item is sent to delievery
- **When** an employee puts it in the truck
- **Then** they can set its statis to being delievered
- **And** they can decrease the amount of the item in warehouse



### US-2.4: Viewing Item History



#### Scenario: Item edited

- **Given** an employee edited an item
- **When** employee saves this edit
- **Then** the past version gets saved in the history



#### Scenario: Item edited wrong

- **Given** an employee edited the wrong item
- **When** another employee is looks at the item
- **Then** they can look at the history and catch the error



#### Scenario: Item deleted

- **Given** an employee deletes an item
- **When** an employee logs on to data base
- **Then** they can see recently sold or deleted items

