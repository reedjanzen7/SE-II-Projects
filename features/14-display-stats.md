# Feature: Maintaining Sports

**Feature ID:** 14  
**Branch pattern:** `features/14-display-stats`  
**Status:** Draft  
**Created:** 10/21/2026  
**Input:** This feature is for viewing a display of stats.

---

## User Stories

### US-14.1: Viewing stats
**As a** user  
**I want to** be able to view stats on the website
**So that** I know the stats of different things

**Priority:** P1  
**Independent test:** users should be able to know stats of things on the website
**Acceptance scenarios:** see US-14.1 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to show the different stats on the website
- **FR-002**: Everyone MUST be able to view the deferent stats on the website

---

## Key Entities

- **stats**: The thing that is getting displayed

---

## Data Model Requirements

### `stats_display_table` table
| Field | Type | Rules |
|-------|------|-------|
| `type` | player-team-ect | type of stat |
| `stats` | Stats | the stats of this thing |

## Acceptance Criteria

### US-14.1 — Viewing stats

#### Scenario: viewed succesfully
*   **Given** a user wants to view the stats of a thing
*   **When** they go to the website
*   **Then** they can veiw the stats

#### Scenario: not viewed succesfully
*   **Given** a user wants to view the stats of a thing
*   **When** they go to the website
*   **Then** nothing shows up
