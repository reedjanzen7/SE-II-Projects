# Feature: Maintaining locations

**Feature ID:** 7  
**Branch pattern:** `features/7-maintain-locations`  
**Status:** Draft  
**Created:** 10/20/2026
**Input:** This feature is for maintaining locations games are played at on the systems website.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-7.1: Adding a location
**As a** Team Manager or website owner
**I want to** be able to add a location  
**So that** the different locations can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different locations that are managed on the website 
**Acceptance scenarios:** see US-7.1 under Acceptance Criteria

### US-7.2: Editing a location
**As a** Team Manager or website owner
**I want to** be able to edit a location  
**So that** the different locations can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different locations that are managed on the website 
**Acceptance scenarios:** see US-7.2 under Acceptance Criteria

### US-7.3: De-activating location
**As a** Team Manager or website owner 
**I want to** be able to de-active a location
**So that** I can make the locations that aren't playing right now un-active.

**Priority:** P1  
**Independent test:** you need to be able to maintain the different locations that are managed on the website 
**Acceptance scenarios:** see US-7.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) locations
- **FR-002**: Users MUST be able to view the deferent locations on the website
- **FR-003**: All users MUST NOT be able to maintain locations

---

## Key Entities

- **Team**: The team that location is their home feild

---

## Data Model Requirements

### `location_table` table
| Field | Type | Rules |
|-------|------|-------|
| `location_id` | INTEGER PK | Auto-increment |
| `home_team` | Team | Added when created a location |
| `address` | String | added upon creation |
| `active` | bool | if the location is active or not |


## Acceptance Criteria

### US-7.1 — Adding a location

#### Scenario: location added successfully
*   **Given** a new location is being added to the system
*   **When** the Team Manager or website owner goes to the locations on the website
*   **Then** they can add a location

#### Scenario: location not added successfully
*   **Given** a new location is being added to the system
*   **When** a user goes to the locations on the website
*   **Then** they can't add a location

### US-7.2 — Editing a location

#### Scenario: location edited successfully
*   **Given** a location needs to have information updated on the website
*   **When** the Team Manager or website owner goes to the website
*   **Then** they can edit the location

#### Scenario: location not edited successfully
*   **Given** a location needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the location

### US-7.3 — De-activating location

#### Scenario: location can't be used anymore
*   **Given** a location can't be used anymore
*   **When** the Team Manager or website owner goes to the website
*   **Then** they can de-activate a location

#### Scenario: location can't be used anymore not successfully
*   **Given** a location can't be used anymore
*   **When** a user goes to the website
*   **Then** they can't de-activate a location
