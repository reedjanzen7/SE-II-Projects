# Feature: Maintaining players

**Feature ID:** 6  
**Branch pattern:** `features/6-maintain-players`  
**Status:** Draft  
**Created:** 10/20/2026  
**Input:** This feature is for maintaining players information on the systems website.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-6.1: Adding a player
**As a** Team Manager 
**I want to** be able to add a player  
**So that** the different players can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different players that are managed on the website 
**Acceptance scenarios:** see US-6.1 under Acceptance Criteria

### US-6.2: Editing a player
**As a** Team Manager  
**I want to** be able to edit a player  
**So that** the different player can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different players that are managed on the website 
**Acceptance scenarios:** see US-6.2 under Acceptance Criteria

### US-6.3: De-activating player
**As a** Team Manager  
**I want to** be able to de-active a player
**So that** I can make the players that aren't playing right now un-active.

**Priority:** P1  
**Independent test:** you need to be able to maintain the different players that are managed on the website 
**Acceptance scenarios:** see US-6.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) players
- **FR-002**: Users MUST be able to view the deferent players on the website
- **FR-003**: All users MUST NOT be able to maintain players

---

## Key Entities

- **Stats**: The stats of a player
- **Team**: The team that the player is playing on

---

## Data Model Requirements

### `player_table` table
| Field | Type | Rules |
|-------|------|-------|
| `player_id` | INTEGER PK | Auto-increment |
| `team` | Team | Added when created a player |
| `player_stats` | Array List of player stats | updated after each game |
| `date_joined` | date | Added upon creation |
| `active` | bool | if the player is active or not |


## Acceptance Criteria

### US-6.1 — Adding a player

#### Scenario: player added successfully
*   **Given** a new player is being added to the league
*   **When** the Team Manager goes to the team on the website
*   **Then** they can add a player

#### Scenario: player not added successfully
*   **Given** a new player is being added to the league
*   **When** a user goes to the league on the website
*   **Then** they can't add a player

### US-6.2 — Editing a player

#### Scenario: player edited successfully
*   **Given** a player needs to have information updated on the website
*   **When** the Team Manager goes to the website
*   **Then** they can edit the player

#### Scenario: player not edited successfully
*   **Given** a player needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the player

### US-6.3 — De-activating player

#### Scenario: player is over
*   **Given** a player is over
*   **When** the Team Managerr goes to the website
*   **Then** they can de-activate a player

#### Scenario: player is over not successfully
*   **Given** a player is over
*   **When** a user goes to the website
*   **Then** they can't de-activate a player
