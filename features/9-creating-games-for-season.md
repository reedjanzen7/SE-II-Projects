# Feature: Maintaining users

**Feature ID:** 9  
**Branch pattern:** `features/9-creating-games-for-season`  
**Status:** Draft  
**Created:** 10/21/2026
**Input:** This feature is for how games are auto generated for a season.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or usererence docs  

---

## User Stories

### US-9.1: Generating games
**As a** website owner
**I want to** be able to automatically generate a game schedule  
**So that** it doesn't have to be done manually

**Priority:** P1  
**Independent test:** you need to not have to deal with having to create a game schedule
**Acceptance scenarios:** see US-9.1 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to automatically create a game schedule
- **FR-002**: Users MUST be able to view the schedule
- **FR-003**: All users MUST NOT be able to make one

---

## Key Entities

- **games**: The thing the schedule is made for

---

## Data Model Requirements

### `auto_generated_schedule_table` table
| Field | Type | Rules |
|-------|------|-------|
| `schedule_id` | INTEGER PK | Auto-increment |
| `season` | string | The season the schedule is for |
| `game_days` | days | days games happen on |
| `how_often` | time | how often games are |
| `active` | bool | if the schedule is active or not |


## Acceptance Criteria

### US-9.1 — generating games

#### Scenario: schedule added successfully
*   **Given** a new schedule needs to be made
*   **When** the website owner gets on the website
*   **Then** they can generate one

#### Scenario: schedule not added successfully
*   **Given** a new schedule needs to be made
*   **When** a users gets on the website
*   **Then** they can't generate one