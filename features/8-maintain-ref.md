# Feature: Maintaining refs

**Feature ID:** 8  
**Branch pattern:** `features/8-maintain-refs`  
**Status:** Draft  
**Created:** 10/21/2026
**Input:** This feature is for maintaining refs that ref games.

---

## User Stories

### US-8.1: Adding a ref
**As a** Team Manager or website owner
**I want to** be able to add a ref  
**So that** the a list of refs can stay up to date

**Priority:** P1  
**Independent test:** you need to be able to maintain the different refs that are managed on the website 
**Acceptance scenarios:** see US-8.1 under Acceptance Criteria

### US-8.2: Editing a ref
**As a** Team Manager or website owner
**I want to** be able to edit a refs info 
**So that** the a list of refs can stay up to date

**Priority:** P1  
**Independent test:** you need to be able to maintain the different refs that are managed on the website 
**Acceptance scenarios:** see US-8.2 under Acceptance Criteria

### US-8.3: De-activating ref
**As a** Team Manager or website owner 
**I want to** be able to de-active a ref
**So that** a ref who isn't reffing won't be assigned to a game

**Priority:** P1  
**Independent test:** you need to be able to maintain the different refs that are managed on the website 
**Acceptance scenarios:** see US-8.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) a list of refs
- **FR-002**: Users MUST be able to view the deferent refs on the website
- **FR-003**: All users MUST NOT be able to maintain refs

---

## Key Entities

- **sport**: The the sport that they reffery

---

## Data Model Requirements

### `ref_table` table
| Field | Type | Rules |
|-------|------|-------|
| `ref_id` | INTEGER PK | Auto-increment |
| `name` | string | Added when created a ref |
| `email` | String | added upon creation |
| `phone_number` | String | added upon creation |
| `sport` | Sport | added upon creation |
| `active` | bool | if the ref is active or not |


## Acceptance Criteria

### US-8.1 — Adding a ref

#### Scenario: ref added successfully
*   **Given** a new ref is being added to the system
*   **When** the Team Manager or website owner goes to the refs on the website
*   **Then** they can add a ref

#### Scenario: ref not added successfully
*   **Given** a new ref is being added to the system
*   **When** a user goes to the refs on the website
*   **Then** they can't add a ref

### US-8.2 — Editing a ref

#### Scenario: ref edited successfully
*   **Given** a ref needs to have information updated on the website
*   **When** the Team Manager or website owner goes to the website
*   **Then** they can edit the ref

#### Scenario: ref not edited successfully
*   **Given** a ref needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the ref

### US-8.3 — De-activating ref

#### Scenario: ref can't be used anymore
*   **Given** a ref can't be used anymore
*   **When** the Team Manager or website owner goes to the website
*   **Then** they can de-activate a ref

#### Scenario: ref can't be used anymore not successfully
*   **Given** a ref can't be used anymore
*   **When** a user goes to the website
*   **Then** they can't de-activate a ref
