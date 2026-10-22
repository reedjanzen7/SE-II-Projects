# Feature: Maintaining teams

**Feature ID:** 5  
**Branch pattern:** `features/5-maintain-teams`  
**Status:** Draft  
**Created:** 10/20/2026  
**Input:** This feature is for maintaining teams information on the systems website.

---

## User Stories

### US-5.1: Adding a team
**As a** Owner 
**I want to** be able to add a team  
**So that** the different teams can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different teams that are managed on the website 
**Acceptance scenarios:** see US-5.1 under Acceptance Criteria

### US-5.2: Editing a team
**As a** Owner  
**I want to** be able to edit a team  
**So that** the different team can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different teams that are managed on the website 
**Acceptance scenarios:** see US-5.2 under Acceptance Criteria

### US-5.3: De-activating team
**As a** Owner  
**I want to** be able to de-active a team
**So that** I can make the teams that aren't playing right now un-active.

**Priority:** P1  
**Independent test:** you need to be able to maintain the different teams that are managed on the website 
**Acceptance scenarios:** see US-5.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) teams
- **FR-002**: Users MUST be able to view the deferent teams on the website
- **FR-003**: All users MUST NOT be able to maintain teams

---

## Key Entities

- **Stats**: The stats of a team
- **Games**: The games that are team is playing in
- **season**: The season the team is playing in

---

## Data Model Requirements

### `team_table` table
| Field | Type | Rules |
|-------|------|-------|
| `team_id` | INTEGER PK | Auto-increment |
| `players` | ArrayList of players | Added when created a team |
| `team_stats` | W - L ratio | updated after each game |
| `teams_league` | String | Added upon creation |
| `date_created` | date | Added upon creation |
| `active` | bool | if they thing is active or not |


## Acceptance Criteria

### US-5.1 — Adding a team

#### Scenario: team added successfully
*   **Given** a new team is being added to the league
*   **When** the website owner goes to the league on the website
*   **Then** they can add a team

#### Scenario: team not added successfully
*   **Given** a new team is being added to the league
*   **When** a user goes to the league on the website
*   **Then** they can't add a team

### US-5.2 — Editing a team

#### Scenario: team edited successfully
*   **Given** a team needs to have information updated on the website
*   **When** the website owner goes to the website
*   **Then** they can edit the team

#### Scenario: team not edited successfully
*   **Given** a team needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the team

### US-5.3 — De-activating team

#### Scenario: team is over
*   **Given** a team is over
*   **When** the website owner goes to the website
*   **Then** they can de-activate a team

#### Scenario: team is over not successfully
*   **Given** a team is over
*   **When** a user goes to the website
*   **Then** they can't de-activate a team
