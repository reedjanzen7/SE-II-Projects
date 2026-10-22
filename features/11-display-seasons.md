# Feature: Maintaining Sports

**Feature ID:** 11  
**Branch pattern:** `features/11-display-seasons`  
**Status:** Draft  
**Created:** 10/21/2026  
**Input:** This feature is for viewing a display of seasons.

---

## User Stories

### US-11.1: Viewing seasons
**As a** user  
**I want to** be able to view seasons on the website
**So that** I know what seasons are going on

**Priority:** P1  
**Independent test:** users should be able to know what is happening on the website
**Acceptance scenarios:** see US-11.1 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to show the different seasons on the website
- **FR-002**: Everyone MUST be able to view the deferent seasons on the website

---

## Key Entities

- **seasons**: The thing that is getting displayed

---

## Data Model Requirements

### `seasons_display_table` table
| Field | Type | Rules |
|-------|------|-------|
| `seasons` | List | list of active seasons |

## Acceptance Criteria

### US-11.1 — Viewing seasons

#### Scenario: viewed succesfully
*   **Given** a user wants to view the active seasons
*   **When** they go to the website
*   **Then** they can veiw the active seasons

#### Scenario: not viewed succesfully
*   **Given** a user wants to view the active seasons
*   **When** they go to the website
*   **Then** nothing shows up
