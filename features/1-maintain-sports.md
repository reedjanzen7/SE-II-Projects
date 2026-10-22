# Feature: Maintaining Sports

**Feature ID:** 1  
**Branch pattern:** `features/1-maintain-sports`  
**Status:** Draft  
**Created:** 10/20/2026  
**Input:** This feature is for maintaining the sport information on the systems website.

---

## User Stories

### US-1.1: Adding a sport
**As a** Owner  
**I want to** be able to add a sport  
**So that** the different sports can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different sports that are managed on the website 
**Acceptance scenarios:** see US-1.1 under Acceptance Criteria

### US-1.2: Editing a sport
**As a** Owner  
**I want to** be able to edit a sport  
**So that** the different sports can be maintained

**Priority:** P1  
**Independent test:** you need to be able to maintain the different sports that are managed on the website 
**Acceptance scenarios:** see US-1.2 under Acceptance Criteria

### US-1.3: De-activating sports
**As a** Owner  
**I want to** be able to de-active sports
**So that** I can make the sports that aren't happening right now un-active.

**Priority:** P1  
**Independent test:** you need to be able to maintain the different sports that are managed on the website 
**Acceptance scenarios:** see US-1.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to maintain (add, edit, de-activate) sports
- **FR-002**: Users MUST be able to view the deferent sports on the website
- **FR-003**: All users MUST NOT be able to maintain sports

---

## Key Entities

- **Leagues**: A group of teams that play eachother in one sport

---

## Data Model Requirements

### `sport_table` table
| Field | Type | Rules |
|-------|------|-------|
| `sport_id` | INTEGER PK | Auto-increment |
| `sports_leagues` | ArrayList of Laegues | Added when adding leagues |
| `sport_name` | String | Added upon creation |
| `sport_description` | String | Added upon creation |
| `active` | bool | if they thing is active or not |


## Acceptance Criteria

### US-1.1 — Adding a sport

#### Scenario: Sport added successfully
*   **Given** a new sport is being added to the website
*   **When** the website owner goes to the website
*   **Then** they can add a sport

#### Scenario: Sport not added successfully
*   **Given** a new sport is being added to the website
*   **When** a user goes to the website
*   **Then** they can't add a sport

### US-1.2 — Editing a sport

#### Scenario: Sport edited successfully
*   **Given** a sport needs to have information updated on the website
*   **When** the website owner goes to the website
*   **Then** they can edit the sport

#### Scenario: Sport not edited successfully
*   **Given** a sport needs to have information updated on the website
*   **When** a user goes to the website
*   **Then** they can't edit the sport

### US-1.3 — De-activating sports

#### Scenario: Sport is no longer happening
*   **Given** a sport is not is season or isn't happening
*   **When** the website owner goes to the website
*   **Then** they can de-activate a sport

#### Scenario: Sport is no longer hapening not successfully
*   **Given** a sport is not is season or isn't happening
*   **When** a user goes to the website
*   **Then** they can't de-activate a sport
