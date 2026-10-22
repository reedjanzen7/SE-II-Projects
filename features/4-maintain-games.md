# Feature: Maintaining games

**Feature ID:** 4  
**Branch pattern:** `features/4-maintain-games`  
**Status:** Draft  
**Created:** 10/20/2026  
**Input:** This feature is for maintaining game information on the systems website.

---

## User Stories

### US-4.1: Adding a game
**As a** Owner 
**I want to** be able to add a game  
**So that** the different games can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different games that are managed on the website 
**Acceptance scenarios:** see US-4.1 under Acceptance Criteria

### US-4.2: Editing a game
**As a** Owner  
**I want to** be able to edit a game  
**So that** the different game can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different games that are managed on the website 
**Acceptance scenarios:** see US-4.2 under Acceptance Criteria

### US-4.3: De-activating game
**As a** Owner  
**I want to** be able to de-active a game
**So that** I can make the games that aren't happening right now un-active.

**Priority:** P1  
**Independent test:** you need to be able to maintain the different games that are managed on the website 
**Acceptance scenarios:** see US-4.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) games
- **FR-002**: Users MUST be able to view the deferent games on the website
- **FR-003**: All users MUST NOT be able to maintain games

---

## Key Entities

- **Stats**: The stats of a game
- **Teams**: The teams that are playing in this game

---

## Data Model Requirements

### `game_table` table
| Field | Type | Rules |
|-------|------|-------|
| `game_id` | INTEGER PK | Auto-increment |
| `home_team` | Team | Added when created a game |
| `vistor_team` | Team | Added when created a game |
| `games_league` | String | Added upon creation |
| `game_date` | date | Added upon creation |
| `active` | bool | if they thing is active or not |


## Acceptance Criteria

### US-4.1 — Adding a game

#### Scenario: game added successfully
*   **Given** a new game is being added to the website
*   **When** the website owner goes to the website
*   **Then** they can add a game

#### Scenario: game not added successfully
*   **Given** a new game is being added to the website
*   **When** a user goes to the website
*   **Then** they can't add a game

### US-4.2 — Editing a game

#### Scenario: game edited successfully
*   **Given** a game needs to have information updated on the website
*   **When** the website owner goes to the website
*   **Then** they can edit the game

#### Scenario: game not edited successfully
*   **Given** a game needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the game

### US-4.3 — De-activating game

#### Scenario: game is over
*   **Given** a game is over
*   **When** the website owner goes to the website
*   **Then** they can de-activate a game

#### Scenario: game is over not successfully
*   **Given** a game is over
*   **When** a user goes to the website
*   **Then** they can't de-activate a game
