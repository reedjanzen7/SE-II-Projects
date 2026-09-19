# Feature: Van routes

**Feature ID:** 2  
**Branch pattern:** `feature/van-routes-2`  
**Status:** Ready  
**Created:** 2026-9-19  
**Input:** A easier way for drivers to know where to pick up people who need a ride to church on the data base.  
**Depends on:** `/church-member-info-1.md` `/accouncement-system-3`

---

## User Stories

### US-2.1: Driver being able to follow van routes

**As a van driver.**  
**I want to be able to see an updated van route.**  
**So that** I can drive efficientlyto pick people up.

**Priority:** P1  
**Independent test:** Van drivers need to know where they need to go to pick people up.  
**Acceptance scenarios:** see US-2.1 under Acceptance Criteria

### US-2.2: Being able to change van routes

**As a church leader.**  
**I want to be able to go and edit van routes.**  
**So that** when different places don't need to be picked up, they can go in and change the van route.

**Priority:** P1  
**Independent test:** Van routes change as more people need to be picked up and other places don't need pick up anymore.  
**Acceptance scenarios:** see US-2.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST be able to save van routes.
- **FR-002**: Van driver MUST be able to look at a van route.
- **FR-003**: Guest MUST NOT be able to go in and change van routes.

---



## Data Model Requirements



### `van-route` table


| Field          | Type    | Rules          |
| -------------- | ------- | -------------- |
| `route-number` | INTEGER | Auto-increment |
| `route`        | MAP     | Manually input |


---



## Acceptance Criteria



### US-2.1 — Driver being able to follow van routes



#### Scenario: Subsitute van driver

- **Given** main van driver is sick.
- **Then** another driver can take his place.
- **When** subsitute driver goes to get the van route.
- **Then** he can log in and get access.
- **And** follow the route and pick everyone up.



#### Scenario: Van driver trying to veiw the route, but it fails

- **Given** the van driver needs to log into view the route.
- **When** the route doesn't show up.
- **Then** they can go to a church leader and they can update it.



### US-2.2 — Being able to change van routes



#### Scenario: Removing from van route

- **Given** A school no longer needs to be on a van route.
- **When** a church leader or van driver logs into the data base.
- **Then** they can go in and change the van route.



#### Scenario: Member without van access.

- **Given** a member without van access logs into the data base.
- **When** they try to edit van routes.
- **Then** they can't view van routes and they don't show up.

