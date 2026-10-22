# Feature: Maintaining games

**Feature ID:** 15  
**Branch pattern:** `features/15-sending-emails`  
**Status:** Draft  
**Created:** 10/21/2026  
**Input:** This feature is for sending out emails. 

---

## User Stories

### US-15.1: sending a email
**As a** Owner 
**I want to** be able to send out an email either too refs for a game, all players, all refs, all team managers
**So that** people can stay update

**Priority:** P1  
**Independent test:** you need to be able to maintain the different games that are managed on the website 
**Acceptance scenarios:** see US-15.1 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST be able to send out emails to refs for a game
- **FR-002**: System MUST be able to send out emails to all players
- **FR-003**: System MUST be able to send out emails to all refs
- **FR-004**: System MUST be able to send out emails to all team managers
- **FR-005**: All users MUST NOT be able send out emails

---

## Key Entities

- **players**: The people who play on the teams
- **refs**: the people who ref the games
- **team managers**: the people who manage the teams

---

## Data Model Requirements

### `email_table` table
| Field | Type | Rules |
|-------|------|-------|
| `type` | players - refs - team managers | who it is getting sent too |


## Acceptance Criteria

### US-15.1 — sending a email

#### Scenario: emailed successfully
*   **Given** a email needs to get sent out
*   **When** the website owner goes to the website
*   **Then** they can email who they need too

#### Scenario:emailed not successfully
*   **Given** a email needs to get sent out
*   **When** a user goes to the website
*   **Then** they can't email everyone
