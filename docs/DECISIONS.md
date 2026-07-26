# NOOR2 Decision Log

## DEC-001 — GitHub as the Source of Truth

Status: Accepted

All project requirements, decisions, tasks, progress, tests, bugs, and releases must be documented in GitHub.

Reason:

This allows any developer or AI assistant to understand the exact project state and continue work without depending on previous chat history.

## DEC-002 — Privacy-First Product Direction

Status: Accepted

The application must minimize data collection and avoid unnecessary transmission of user information.

## DEC-003 — Offline-First Product Direction

Status: Accepted

Core Quran reading functionality should remain available without an internet connection wherever technically possible.

## DEC-004 — No Unapproved Technology Assumptions

Status: Accepted

The Android technology stack, database, dependency-injection framework, Quran data source, and module structure must not be treated as final until documented and approved.

## DEC-005 — Android Application Identity

Status: Accepted

The official NOOR2 Android application identity is:

- Arabic display name: نور
- English display name: NOOR2
- Android application ID: `io.github.muawiyaabdellattifalt.noor2`
- Publisher identity: NOOR2 Project
- Support email: `muawiyaabdellattif@gmail.com`
- Debug display name: NOOR2 Debug
- Production display name: NOOR2

This identity must be used when creating the Android project unless a later approved decision explicitly replaces it.
