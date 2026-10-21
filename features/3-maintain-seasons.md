# Feature: Maintaining Seasons

**Feature ID:** 3  
**Branch pattern:** `features/3-maintain-seasons`  
**Status:** Draft  
**Created:** 10/20/2026  
**Input:** This feature is for maintaining the season information on the systems website.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-3.1: Adding a Season
**As a** Owner  
**I want to** be able to add a season  
**So that** the different seasons can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different seasons that are managed on the website 
**Acceptance scenarios:** see US-3.1 under Acceptance Criteria

### US-3.2: Editing a season
**As a** Owner  
**I want to** be able to edit a season  
**So that** the different season can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different seasons that are managed on the website 
**Acceptance scenarios:** see US-3.2 under Acceptance Criteria

### US-3.3: De-activating season
**As a** Owner  
**I want to** be able to de-active a season
**So that** I can make the seasons that aren't happening right now un-active.

**Priority:** P1  
**Independent test:** you need to be able to maintain the different seasons that are managed on the website 
**Acceptance scenarios:** see US-3.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) seasons
- **FR-002**: Users MUST be able to view the deferent seasons on the website
- **FR-003**: All users MUST NOT be able to maintain seasons

---

## Key Entities

- **Sport**: The type of sport the season is in
- **Teams**: The different teams that a season's league has
- **League**: The league that the season is happening on

---

## Data Model Requirements

### `season_table` table
| Field | Type | Rules |
|-------|------|-------|
| `season_id` | INTEGER PK | Auto-increment |
| `seasons_teams` | ArrayList of Teams | Added when created a team |
| `seasons_league` | String | Added upon creation |
| `seasons_start` | Date | Added upon creation |
| `seasons_end` | date | Added upon creation or added later|
| `active` | bool | if they thing is active or not |


## Acceptance Criteria

### US-3.1 — Adding a Season

#### Scenario: Season added successfully
*   **Given** a new season is being added to the website
*   **When** the website owner goes to the website
*   **Then** they can add a season

#### Scenario: Season not added successfully
*   **Given** a new season is being added to the website
*   **When** a user goes to the website
*   **Then** they can't add a season

### US-3.2 — Editing a Season

#### Scenario: season edited successfully
*   **Given** a season needs to have information updated on the website
*   **When** the website owner goes to the website
*   **Then** they can edit the season

#### Scenario: season not edited successfully
*   **Given** a season needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the season

### US-3.3 — De-activating Season

#### Scenario: season is over
*   **Given** a season is over
*   **When** the website owner goes to the website
*   **Then** they can de-activate a season

#### Scenario: season is over not successfully
*   **Given** a season is over
*   **When** a user goes to the website
*   **Then** they can't de-activate a season
