 Feature: 

**Feature ID:** 3  
**Branch pattern:** `feature/accouncement-system-3`  
**Status:** Ready  
**Created:** 2026-9-19  
**Input:** Church leaders should be able to sign in and create an announcement that will get sent out to church members emails  
**Depends on:** `/church-member-info-1.md` `/van-routes-2.md`

---

## User Stories

### US-3.1: Sending out a church canceled announcement

**As a church leader.**  
**I want to be able to send out announcements.**  
**So that** if the weather is bad, we can cancel church.

**Priority:** P1  
**Independent test:** The weather can be bad and we don't won't people to try to get to church when eather is dangerous.  
**Acceptance scenarios:** see US-3.1 under Acceptance Criteria

### US-3.2: Sending out an update email

**As a church leader.**  
**I want to be able to send out church updates.**  
**So that** if someone passes away or someone gets baptized the church can get updated.

**Priority:** P1  
**Independent test:** The church needs ways to update their members about things going on in the church.  
**Acceptance scenarios:** see US-3.2 under Acceptance Criteria

---



## Requirements



### Functional Requirements

- **FR-001**: System MUST be able to send out announcements to church members emails.
- **FR-002**: Users MUST be able to view the announcements in their email or on the data base.
- **FR-003**: Members and guest MUST NOT be able to send out announcements.

---



## Data Model Requirements



### `announcements` table


| Field               | Type   | Rules          |
| ------------------- | ------ | -------------- |
| `announcement-type` | STRING | Manually input |


---



## Acceptance Criteria



### US-3.1 —  Sending out a church canceled announcement



#### Scenario: Church leader sending out an email

- **Given** the weather is bad.
- **When** a church leader logs into the data base.
- **Then** they can send out an announcements.
- **And all the church members will get an email telling them that church is canceled.**



#### Scenario: **Member tries to send an canceled announcement**

- **Given** a church member or guest 
- **When** they log onto the data base.
- **Then** they don't have the option to send out an canceled announcement



### US-3.2 — Sending out an update email



#### Scenario: Someone is getting babtized

- **Given** someone is getting babtized
- **When** a church leader logs into the data base.
- **Then** they can send out an update announcements.
- **And all the church members will get an email telling them about this update.**



#### Scenario: **Member tries to send an update**

- **Given** a church member or guest 
- **When** they log onto the data base.
- **Then** they don't have the option to send out an update

