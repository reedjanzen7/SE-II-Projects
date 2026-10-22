# Feature: Maintaining Sports

**Feature ID:** 12  
**Branch pattern:** `features/12-display-teams`  
**Status:** Draft  
**Created:** 10/21/2026  
**Input:** This feature is for viewing a display of teams.

---

## User Stories

### US-12.1: Viewing teams
**As a** user  
**I want to** be able to view teams on the website
**So that** I know what teams are playing

**Priority:** P1  
**Independent test:** users should be able to know what is happening on the website
**Acceptance scenarios:** see US-12.1 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to show the different teams on the website
- **FR-002**: Everyone MUST be able to view the deferent teams on the website

---

## Key Entities

- **teams**: The thing that is getting displayed

---

## Data Model Requirements

### `teams_display_table` table
| Field | Type | Rules |
|-------|------|-------|
| `teams` | List | list of active teams |
| `teams_league` | league | league of the team |
| `teams_games` | games | games the team plays on |
| `team_stats` | stats | stats of the team |

## Acceptance Criteria

### US-12.1 — Viewing teams

#### Scenario: viewed succesfully
*   **Given** a user wants to view the active teams
*   **When** they go to the website
*   **Then** they can veiw the active teams

#### Scenario: not viewed succesfully
*   **Given** a user wants to view the active teams
*   **When** they go to the website
*   **Then** nothing shows up
