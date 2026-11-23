# Feature: maintaining the company

**Feature ID:** N  
**Branch pattern:** `feature/N-mainaining-the-company`  
**Status:** Draft  
**Created:** 11/23/2026 
**Input:** This feature for is mainaining the company of that runs the invoicing projects, so customers can see their info.
**Depends on:** [Feature X — …](feature-X-….md)  
**Related:** optional links to ADRs or reference docs  

---

## User Stories

### US-N.1: Adding company information
**As a** company manager  
**I want to** be able to add company information 
**So that** customers know the most up to date information about our company

**Priority:** P1  
**Independent test:** Customers would like to have up to date information on a company before they work with them. 
**Acceptance scenarios:** see US-N.1 under Acceptance Criteria

### US-N.2: Editing company information
**As a** company manager  
**I want to** be able to edit company information 
**So that** customers know the most up to date information about our company

**Priority:** P1  
**Independent test:** Customers would like to have up to date information on a company before they work with them. 
**Acceptance scenarios:** see US-N.2 under Acceptance Criteria

### US-N.3: Deleting company information
**As a** company manager  
**I want to** be able to delete old company information 
**So that** customers know the most up to date information about our company

**Priority:** P1  
**Independent test:** Customers would like to have up to date information on a company before they work with them. 
**Acceptance scenarios:** see US-N.3 under Acceptance Criteria

---

## Requirements

### Functional Requirements

- **FR-001**: System MUST …
- **FR-002**: Users MUST be able to …
- **FR-003**: … MUST NOT …

---

## Assumptions

- What already exists (e.g. Feature 1 auth is on `dev`)
- What you are deliberately not building yet

---

## Edge Cases

- Empty required field → …
- Cross-user access → …
- Duplicate / invalid input → …

---

## Success Criteria

- **SC-001**: Every Gherkin scenario has at least one automated test before merge
- **SC-002**: <measurable outcome for this feature>

---

## Key Entities

- **Entity**: short description; relationships in plain language
- **Entity**: …

---

## Data Model Requirements

### `company_information` table
| Field | Type | Rules |
|-------|------|-------|
| `id` | INTEGER PK | Auto-increment |
| `Name` | string | added manually |
| `Address` | string | added manually |
| `website_url` | string | added manually |
| `phone_number` | int | added manually |
| `email` | string | added manually |
| `banking_info` | string | added manually |

### Associations (if known)
- …

---

## Acceptance Criteria

### US-N.1 — Short title (same as the story)

#### Scenario: Descriptive name (happy path)
*   **Given** <starting state>
*   **When** <action>
*   **Then** <observable result>
*   **And** <extra result if needed>

#### Scenario: Descriptive name (failure / edge)
*   **Given** …
*   **When** …
*   **Then** …

### US-N.2 — Short title (same as the story)

#### Scenario: Descriptive name (happy path)
*   **Given** …
*   **When** …
*   **Then** …

#### Scenario: Descriptive name (failure / edge)
*   **Given** …
*   **When** …
*   **Then** …
