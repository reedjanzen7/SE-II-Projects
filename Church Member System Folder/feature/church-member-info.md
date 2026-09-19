# Feature: Church member information Data base

**Feature ID:** 1  
**Branch pattern:** `feature/church-member-info`  
**Status:** Ready  
**Created:** 2026-9-19  
**Input:** A Data base that can keep all of a members inforamtion for a church.  
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-N.1: Church members access to their information

**As a church member**  
**I want to be able to talk to a church leader or go in myself and add or change my information in the data base**  
**So that** the church has up to date information

**Priority:** P1  
**Independent test:** The church needs a better way to organize there church member information  
**Acceptance scenarios:** see US-N.1 under Acceptance Criteria

### US-N.2: Church leaders filling in attendance

**As a church leader**  
**I want to be able to easly mark someone as at church or not, just by having there name**  
**So that** we can keep tract of who was at church and follow up with them

**Priority:** P1  
**Independent test:** The church needs a better way to organize there church member information  
**Acceptance scenarios:** see US-N.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST keep a data of a guest and church members name, address, email, phone number, school, how long they have been a member, baptized, house hold, and if they are a church member or not.
- **FR-002**: Users MUST be able to go in and change their infomation so they can keep it up to date
- **FR-003**: Users MUST NOT be able to edit other church members or guests information that isn't theirs
- **FR-004**: Church leaders must be able to change, edit, or add to members and guest information.

---



## Data Model Requirements



### `Info_table` table


| Field                 | Type   | Rules          |
| --------------------- | ------ | -------------- |
| `First Name`          | STRING | Manually input |
| `Address`             | STRING | Manually input |
| `Email`               | STRING | Manually input |
| `phone number`        | INT    | Manually input |
| `School`              | STRING | Manually input |
| `Age`                 | INT    | Manually input |
| `First date attended` | DATE   | Manually input |
| `Baptized`            | BOOL   | Manually input |
| `House hold`          | STRING | Manually input |
| `Church member`       | BOOL   | Manually input |
| `Limited Access`      | BOOL   | Manually input |


---



## Acceptance Criteria



### US-N.1 — Church member access to their information



#### Scenario: Guest wants to become member

- **Given** A church guest wants to become a member.
- **When** they go to a leader to get there membership set up.
- **Then** the church leader gets all there information and makes them a member.
- **And** the member gets set up with an account to the data base so they can go in and update their information when they need too.



#### Scenario: Member tries to change there info incorrectly

- **Given** a church member signs into change there info.
- **When** they try to put in invailed Age.
- **Then** it will return with an error and make them retype it.



### US-N.2 — Church leaders filling in attendance



#### Scenario: Church leadermarking someone as here (happy path)

- **Given** the leader has the name of the church member.
- **When** they pull up the data base.
- **Then** they can type their name and mark them as attended.



#### Scenario: None church leader messing with attendance (failure / edge)

- **Given** someone tries to change there attendance.
- **When** they log onto the data base.
- **Then** they can only edit there own attendance and don't have the option to change other peoples.

