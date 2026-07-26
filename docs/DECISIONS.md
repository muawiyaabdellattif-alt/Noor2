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

## DEC-006 — Canonical Quran Text Source

Status: Accepted

The canonical Quran text source for NOOR2 is Tanzil Project Quran Text version 1.1.

Approved corpora:

- Primary display corpus: Tanzil Uthmani.
- Offline search corpus: Tanzil Simple Clean.
- Source website: https://tanzil.net
- License: Creative Commons Attribution 3.0 with Tanzil terms of use.

Mandatory rules:

- Quran text files must be obtained only from the official Tanzil download source.
- The downloaded Quran text must be stored and distributed verbatim.
- The canonical Quran text must never be edited, corrected, normalized or reformatted in place.
- Tanzil Project attribution and a link to Tanzil must be visible in the application.
- The official copyright and license notice must accompany distributed copies as required.
- Search processing must use a separate official search corpus or derived index keys without altering the stored canonical display text.
- Every imported source file must have a recorded SHA-256 checksum.
- The original downloaded files must be retained as immutable audit artifacts.
- Any future source-version change requires a new approved decision and verification report.

This decision resolves GitHub issue #2.

## DEC-008 — Android Technical Architecture

Status: Accepted

The approved Android technical architecture for NOOR2 is:

- Primary language: Kotlin.
- Minimum Android version: Android 8.0, API 26.
- User-interface framework: Jetpack Compose.
- Application model: Single Activity.
- Architectural layers: UI, Domain and Data.
- State management: ViewModel with StateFlow.
- UI data flow: Unidirectional Data Flow.
- Structured local database: Room over SQLite.
- Application settings: DataStore.
- Dependency injection: Hilt.
- Concurrency and reactive streams: Kotlin Coroutines and Flow.
- Navigation: Navigation Compose.
- Quran audio playback: AndroidX Media3 ExoPlayer.
- Background audio: MediaLibraryService.
- Audio downloads: Media3 DownloadService.
- Deferred background work: WorkManager.
- Product direction: local-first and no account required for core use.

Initial modules:

- `app`
- `core:model`
- `core:database`
- `core:datastore`
- `core:designsystem`
- `core:testing`
- `feature:mushaf`
- `feature:search`
- `feature:audio`
- `feature:library`
- `feature:settings`

The full-page Madinah Mushaf renderer must remain isolated behind the `feature:mushaf` boundary.

The exact local page-asset format and packaging method must be validated through a prototype before being treated as final.

This decision resolves GitHub issue #3.
