# Feature: Maintaining Sports

**Feature ID:** 13  
**Branch pattern:** `features/13-display-players`  
**Status:** Draft  
**Created:** 10/21/2026  
**Input:** This feature is for viewing a display of players.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-13.1: Viewing players
**As a** user  
**I want to** be able to view players on the website
**So that** I know what players are playing

**Priority:** P1  
**Independent test:** users should be able to know what is happening on the website
**Acceptance scenarios:** see US-13.1 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to show the different players on the website
- **FR-002**: Everyone MUST be able to view the deferent players on the website

---

## Key Entities

- **players**: The thing that is getting displayed

---

## Data Model Requirements

### `players_display_table` table
| Field | Type | Rules |
|-------|------|-------|
| `players` | List | list of active players |
| `player_stats` | stats | stats of the player |
| `player_names` | List | list of players names |
| `player_team` | team | what team the player is one |

## Acceptance Criteria

### US-13.1 — Viewing players

#### Scenario: viewed succesfully
*   **Given** a user wants to view the active players
*   **When** they go to the website
*   **Then** they can veiw the active players

#### Scenario: not viewed succesfully
*   **Given** a user wants to view the active players
*   **When** they go to the website
*   **Then** nothing shows up
