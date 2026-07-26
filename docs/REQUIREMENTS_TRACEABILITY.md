# NOOR2 Requirements Traceability

## Purpose

This document connects approved product requirements with GitHub issues, implementation, tests and release evidence.

## Status Values

- Approved
- Planned
- In Progress
- Implemented
- Verified
- Deferred
- Blocked

## MVP Requirements

| ID | Requirement | Priority | Status | GitHub Issue | Implementation | Tests |
|---|---|---:|---|---|---|---|
| MVP-001 | Complete verified Quran text available offline | P0 | Approved | Not created | Not started | Not started |
| MVP-002 | Quran reader with Surah, Ayah and Juz navigation | P0 | Approved | Not created | Not started | Not started |
| MVP-003 | Save and restore the exact last-read position | P0 | Approved | Not created | Not started | Not started |
| MVP-004 | Offline Arabic Quran search | P0 | Approved | Not created | Not started | Not started |
| MVP-005 | Bookmarks and private notes | P0 | Approved | Not created | Not started | Not started |
| MVP-006 | Quran audio with background playback | P0 | Approved | Not created | Not started | Not started |
| MVP-007 | Audio downloads with pause, resume and deletion | P1 | Approved | Not created | Not started | Not started |
| MVP-008 | Approved Tafsir and translations with visible sources | P1 | Approved | Not created | Not started | Not started |
| MVP-009 | Reading and Khatmah goals | P1 | Approved | Not created | Not started | Not started |
| MVP-010 | Verified Adhkar and private Tasbih | P1 | Approved | Not created | Not started | Not started |
| MVP-011 | Privacy center, export and deletion controls | P0 | Approved | Not created | Not started | Not started |
| MVP-012 | Arabic and English interface resources | P0 | Approved | Not created | Not started | Not started |
| MVP-013 | Feedback for technical, content and accessibility issues | P1 | Approved | Not created | Not started | Not started |

## Non-Functional Requirements

| ID | Requirement | Priority | Status | Evidence |
|---|---|---:|---|---|
| NFR-001 | Core reading must work in airplane mode | P0 | Approved | Not available |
| NFR-002 | No advertisements or behavioral tracking | P0 | Approved | Not available |
| NFR-003 | No secrets or signing keys committed to GitHub | P0 | Approved | Repository review |
| NFR-004 | Quranic content must have verified provenance | P0 | Approved | Not available |
| NFR-005 | Database migrations must preserve user data | P0 | Approved | Not available |
| NFR-006 | Essential flows must support TalkBack | P0 | Approved | Not available |
| NFR-007 | Essential screens must support large text and reflow | P0 | Approved | Not available |
| NFR-008 | Network requests must use approved HTTPS sources | P0 | Approved | Not available |
| NFR-009 | Quran search and reader performance must be measured | P1 | Approved | Not available |
| NFR-010 | Storage and downloaded files must be user-controlled | P1 | Approved | Not available |

## Traceability Rules

Every GitHub implementation issue must include:

1. One or more requirement IDs.
2. Clear acceptance criteria.
3. Required tests.
4. Offline behavior.
5. Accessibility impact.
6. Privacy and security impact.
7. Documentation changes.

Every completed requirement must link to:

- GitHub issue.
- Pull request or commit.
- Automated tests.
- Manual test evidence where required.
- Release evidence when applicable.

## Current Gaps

- Initial foundation and decision issues #1-#5 have been created.
- Android source code has not been imported.
- Quran content source has not been approved.
- Architecture decisions have not been finalized.
- No automated or device tests exist.
- No release artifact exists.

## Next Action

Create the first GitHub issues for:

1. Approve the Android application identity.
2. Approve the Quran text source and license.
3. Define the Android technical architecture.
4. Import and audit previous source code.
5. Establish a reproducible Android build.

## Foundation and Decision Issues

| Issue | Purpose | Related Requirements | Status |
|---|---|---|---|
| #1 | Approve Android application identity | Project foundation | Completed |
| #2 | Approve Quran text source and licensing | MVP-001, NFR-004 | Completed |
| #3 | Define Android technical architecture | All technical requirements | Open |
| #4 | Import and audit previous NOOR2 source code | Migration and source audit | Open |
| #5 | Establish a reproducible Android build | Build and testing foundation | Open |

## Current Priority Order

1. Issue #1 completed: application identity approved.
2. Issue #2 completed: Tanzil version 1.1 approved.
3. Resolve issue #3: Android architecture (current priority).
4. Begin issue #4 when previous source files are available.
5. Begin issue #5 from a full computer development environment.
