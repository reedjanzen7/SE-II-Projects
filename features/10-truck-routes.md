# Feature: Truck Routes

**Feature ID:** 10  
**Branch pattern:** `feature/10-truck-routes`  
**Status:** Draft  
**Created:** 9/25/2026  
**Input:** This is the truck driver / truck route feature that has all the information for deilveries
**Depends on:** [Feature 11 — Employees](11-employees.md)

---

## User Stories

### US-10.1: Having a List of Customer

**As a** truck driver
**I want to** have a list of customers
**So that** I know where to drive

**Priority:** P1  
**Independent test:** Truck drivers need to know who and where they are deilvering too  
**Acceptance scenarios:** see US-10.1 under Acceptance Criteria

### US-10.2: List of Addresses in Route Order

**As a** truck driver
**I want to** have a list of address in the most effiectent order to deilver them in 
**So that** I can finish the order quickly

**Priority:** P1  
**Independent test:** Customers need to get their items quick, and truck drivers should get the deilveries done quick
**Acceptance scenarios:** see US-10.2 under Acceptance Criteria

### US-10.3: Creating the most Effective Truck Route

**As a** warehouse system
**I want to** create the most effective trucking route
**So that** deilveries go fast

**Priority:** P1  
**Independent test:**  Customers need to get their items quick, and truck drivers should get the deilveries done quick
**Acceptance scenarios:** see US-10.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST create the most effective trucking route
- **FR-002**: Truck driver MUST be able to see the most effective trucking route

---



## Key Entities

- **Routes**: A group of addresses that create a route; the path the truck drivers follow.

---



## Data Model Requirements



### `truck_route_info` table


| Field | Type       | Rules          |
| ----- | ---------- | -------------- |
| `route_id`  | INTEGER PK | Auto-increment |
| `route`   | Address Array          | List of address in most effective route             |
| `trucker_name`   | Name     | Name of the truck driver who route is assigned too             |




### Associations

- 4-supplier-order-form
- 6-customer-order-form

---



## Acceptance Criteria



### US-10.1: Having a List of Customer



#### Scenario: Truck driver departs

- **Given** truck driver departs on route
- **When** the look at the data base
- **Then** they can see the most effective route for them to follow
- **And** then they can map on a mapi=ping deivice



#### Scenario: Customer cancels

- **Given** a customer cancels an order
- **When** the truck driver gets it
- **Then** they skip that location



### US-10.2: List of Addresses in Route Order



#### Scenario: Truck driver departs

- **Given** truck driver departs on route
- **When** the look at the data base
- **Then** they can see the most effective route for them to follow
- **And** then they can map on a mapi=ping deivice



#### Scenario: Customer cancels

- **Given** a customer cancels an order
- **When** the truck driver gets it
- **Then** they skip that location



### US-10.3: Creating the most Effective Truck Route



#### Scenario: Truck driver departs

- **Given** truck driver departs on route
- **When** the look at the data base
- **Then** they can see the most effective route for them to follow
- **And** then they can map on a mapi=ping deivice



#### Scenario: Customer cancels

- **Given** a customer cancels an order
- **When** the truck driver gets it
- **Then** they skip that location