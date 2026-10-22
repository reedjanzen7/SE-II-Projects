# Feature: Maintaining Leagues

**Feature ID:** 2  
**Branch pattern:** `features/2-maintain-leagues`  
**Status:** Draft  
**Created:** 10/20/2026  
**Input:** This feature is for maintaining the league information on the systems website.

---

## User Stories

### US-2.1: Adding a League
**As a** Owner  
**I want to** be able to add a league  
**So that** the different leagues can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different leagues that are managed on the website 
**Acceptance scenarios:** see US-2.1 under Acceptance Criteria

### US-2.2: Editing a League
**As a** Owner  
**I want to** be able to edit a league  
**So that** the different leagues can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different leagues that are managed on the website 
**Acceptance scenarios:** see US-2.2 under Acceptance Criteria

### US-2.3: De-activating Leagues
**As a** Owner  
**I want to** be able to de-active leagues
**So that** I can make the leagues that aren't happening right now un-active.

**Priority:** P1  
**Independent test:** you need to be able to maintain the different leagues that are managed on the website 
**Acceptance scenarios:** see US-2.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) leagues
- **FR-002**: Users MUST be able to view the deferent leagues on the website
- **FR-003**: All users MUST NOT be able to maintain leagues

---

## Key Entities

- **Sport**: The type of sport the league is in
- **Teams**: The different teams that a league has

---

## Data Model Requirements

### `leagues_table` table
| Field | Type | Rules |
|-------|------|-------|
| `league_id` | INTEGER PK | Auto-increment |
| `leagues_teams` | ArrayList of Teams | Added when created a team |
| `league_name` | String | Added upon creation |
| `league_description` | String | Added upon creation |
| `leagues_sport` | String | Added upon creation |
| `leagues_current_session` | Season | edited upon seasons creation |
| `active` | bool | if they thing is active or not |


## Acceptance Criteria

### US-2.1 — Adding a League

#### Scenario: League added successfully
*   **Given** a new league is being added to the website
*   **When** the website owner goes to the website
*   **Then** they can add a league

#### Scenario: League not added successfully
*   **Given** a new league is being added to the website
*   **When** a user goes to the website
*   **Then** they can't add a league

### US-2.2 — Editing a League

#### Scenario: league edited successfully
*   **Given** a league needs to have information updated on the website
*   **When** the website owner goes to the website
*   **Then** they can edit the league

#### Scenario: league not edited successfully
*   **Given** a league needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the league

### US-2.3 — De-activating League

#### Scenario: league is no longer happening
*   **Given** a league is not is season or isn't happening
*   **When** the website owner goes to the website
*   **Then** they can de-activate a league

#### Scenario: league is no longer hapening not successfully
*   **Given** a league is not is season or isn't happening
*   **When** a user goes to the website
*   **Then** they can't de-activate a league
