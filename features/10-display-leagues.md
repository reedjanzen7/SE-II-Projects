# Feature: Maintaining Sports

**Feature ID:** 10  
**Branch pattern:** `features/10-display-leagues`  
**Status:** Draft  
**Created:** 10/21/2026  
**Input:** This feature is for viewing a display of leagues.

---

## User Stories

### US-10.1: Viewing leagues
**As a** user  
**I want to** be able to view leagues on the website
**So that** I know what leagues are playing

**Priority:** P1  
**Independent test:** users should be able to know what is happening on the website
**Acceptance scenarios:** see US-10.1 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to show the different leagues on the website
- **FR-002**: Everyone MUST be able to view the deferent leagues on the website

---

## Key Entities

- **Leagues**: The thing that is getting displayed

---

## Data Model Requirements

### `leagues_display_table` table
| Field | Type | Rules |
|-------|------|-------|
| `leagues` | List | list of active leagues |

## Acceptance Criteria

### US-10.1 — Viewing leagues

#### Scenario: viewed succesfully
*   **Given** a user wants to view the active leagues
*   **When** they go to the website
*   **Then** they can veiw the active leagues

#### Scenario: not viewed succesfully
*   **Given** a user wants to view the active leagues
*   **When** they go to the website
*   **Then** nothing shows up
