# Feature: Inventory

**Feature ID:** 1  
**Branch pattern:** `feature/1-inventory`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** This feature is used for keeping track of the Warehouses inventory, like add, edit, and deleting items.  
**Depends on:** [Feature 2 — Item](2-item.md), [Feature 11 — Employees](11-employees.md) 

---

## User Stories

### US-1.1: Adding New Item

**As a** employee
**I want to** be able to add a new item to the inventory
**So that** the inventory is kept up to date

**Priority:** P1  
**Independent test:** New items will get shipped into warehouse from suppliers, so employees must be able to update them.  
**Acceptance scenarios:** see US-1.1 under Acceptance Criteria

### US-1.2: Item No Longer Sold

**As a** employee
**I want to** be able to delete a old item from the inventory
**So that** the inventory is kept up to date

**Priority:** P1  
**Independent test:** Items will stop getting sold over time, so employees must be able to update them.
**Acceptance scenarios:** see US-1.2 under Acceptance Criteria

### US-1.3: Warehouse Capcity

**As a** employee
**I want to** be able able to see how full the inventory is
**So that** we can know if we can accept new items into the warehouse

**Priority:** P1  
**Independent test:** As customers want the warehouse to sell new items, employees need to see if there is capcity for new items.  
**Acceptance scenarios:** see US-1.3 under Acceptance Criteria

### US-1.4: Viewing Recently Deleted Items

**As a** employee 
**I want to** be able to view recently deleted items
**So that** if we need to start selling something again, it can be viewed

**Priority:** P1  
**Independent test:** Old items could need to be sold again, and haveing access to the items old info could be helpful.
**Acceptance scenarios:** see US-1.4 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST give a way to keep track of inventory in a organized way.
- **FR-002**: Employees MUST be able to manage items in the inventory.
- **FR-003**: Customers and suppliers MUST NOT be able to manage the inventory.
- **FR-004**: Employees MUST be able to see how full the warehouse inventory is.

---



## Key Entities

- **Items**: The thing that is sold in the warehouse; the inventory is fulled of them.
- **Item Locations**: The loaction of where an item is in the warehouse; it allows the user to know where it is in the warehouse.

---



## Data Model Requirements



### `inventory_table` table


| Field                        | Type       | Rules                        |
| ---------------------------- | ---------- | ---------------------------- |
| `amount_of_items`                    | INTEGER PK | Auto-increment               |
| `item_type_count`                | INTEGER    | Auto-increment                   |
| `recently_deleted_items`             | Item-Array       | Auto-created when items deleted                 |




### Associations

- 2-item

---



## Acceptance Criteria



### US-1.1: Adding New Item



#### Scenario: Adding New Item

- **Given** a new item arrives
- **When** employee adds item to inventory
- **Then** system gets updated



#### Scenario: Adding New Item with typo

- **Given** a new item arrives
- **When** employee adds new item with a typo
- **Then** item can be edited later to fix this issue



### US-1.2: Item No Longer Sold



#### Scenario: Removing Item

- **Given** an item is no longer sold
- **When** employee goes into the inventory
- **Then** they can delete the item



#### Scenario: Deleting the wrong item

- **Given** an item is no longer sold
- **When** employee goes to deleted it, but the delete the wrong item
- **Then** item can be seen in recently deleted item
- **And** can then be restored



### US-1.3: Warehouse Capcity



#### Scenario: Warehouse Inventory isn't Full

- **Given** customer or supplier want us to have a new item
- **When** employee goes to see Warehouse Capcity
- **Then** they can see it isn't full
- **And** then go talk to a manager to add the item



#### Scenario:Warehouse Inventory Full

- **Given** customer or supplier want us to have a new item
- **When** employee goes to see Warehouse Capcity
- **Then** they can see it is full, but they can still let the manager know they want this item sold



### US-1.4: Viewing Recently Deleted Items



#### Scenario: Wrong item was deleted

- **Given** an employee deleted the wrong item
- **When** employee goes recently deleted items
- **Then** item can be restored



#### Scenario: Warehouse deletes lots of old items

- **Given** the warehouse decided to stop selling lots of items
- **When** manager goes to recently deleted
- **Then** they can permently delete them to not take up too much storage