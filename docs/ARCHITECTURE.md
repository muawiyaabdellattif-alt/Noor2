# NOOR2 Android Architecture

## 1. Purpose

This document defines the approved initial Android architecture for NOOR2.

It implements the decisions recorded in DEC-008 and must be reviewed before creating or importing Android source code.

## 2. Technology Baseline

| Area | Approved Choice |
|---|---|
| Language | Kotlin |
| Minimum Android version | Android 8.0 / API 26 |
| UI | Jetpack Compose |
| Application model | Single Activity |
| Architecture | UI, Domain and Data layers |
| State | ViewModel and StateFlow |
| Data flow | Unidirectional Data Flow |
| Database | Room over SQLite |
| Settings | DataStore |
| Dependency injection | Hilt |
| Concurrency | Coroutines and Flow |
| Navigation | Navigation Compose |
| Audio | AndroidX Media3 ExoPlayer |
| Background playback | MediaLibraryService |
| Audio downloads | Media3 DownloadService |
| Deferred work | WorkManager |

## 3. Architecture Principles

- Offline-first.
- Privacy-first.
- Arabic-first.
- Local-first personal data.
- No mandatory account.
- Immutable Quran source assets.
- Stable Quran, Surah, Ayah and page identifiers.
- Clear separation between canonical content and user data.
- Features must depend on interfaces rather than storage implementations.
- UI must not access databases or network clients directly.

## 4. Initial Modules

### app

Responsibilities:

- Android application entry point.
- Main activity.
- Root navigation.
- Dependency assembly.
- Global theme.
- Application-level lifecycle.

### core:model

Responsibilities:

- Shared domain models.
- Stable Quran references.
- Page, Surah and Ayah identifiers.
- Bookmark, note and playback models.
- No Android UI dependencies.

### core:database

Responsibilities:

- Quran metadata database.
- User database.
- Room entities and DAOs.
- Database migrations.
- Repository implementations for structured local data.

Canonical Mushaf page assets must not be modified through Room.

### core:datastore

Responsibilities:

- Language.
- Theme.
- Reading preferences.
- Selected reciter.
- Notification preferences.
- Non-sensitive application settings.

### core:designsystem

Responsibilities:

- Colors.
- Typography.
- Spacing.
- Reusable Compose components.
- Accessibility defaults.
- Arabic and RTL behavior.

### core:testing

Responsibilities:

- Test data.
- Fake repositories.
- Coroutine test utilities.
- Database test helpers.
- Accessibility-test helpers.

### feature:mushaf

Responsibilities:

- Full-page Madinah Mushaf display.
- Page turning.
- Zoom and pan.
- Page position restoration.
- Ayah overlay interaction.
- Page-to-Ayah mapping.
- Offline page availability.

The visible page layout must not be reflowed.

### feature:search

Responsibilities:

- Offline Quran search.
- Arabic query normalization.
- Search-result mapping to Mushaf pages.
- Search history when enabled locally.

### feature:audio

Responsibilities:

- Reciter selection.
- Playback.
- Background service.
- System media controls.
- Repeat.
- Sleep timer.
- Download management.

### feature:library

Responsibilities:

- Bookmarks.
- Notes.
- Collections.
- History.
- Export and deletion.

### feature:settings

Responsibilities:

- General settings.
- Accessibility settings.
- Privacy controls.
- Storage controls.
- Quran content attribution.
- Support information.

## 5. Data Boundaries

### Mushaf Page Assets

- Complete Madinah Mushaf pages.
- Read-only.
- Immutable.
- Stored locally.
- Checksum-verified.
- Accessed only through a Mushaf asset provider interface.

### Quran Metadata Database

Contains:

- Page numbers.
- Surah and Ayah references.
- Juz mapping.
- Ayah interaction regions.
- Search index references.
- Audio synchronization references.

### User Database

Contains:

- Bookmarks.
- Notes.
- Collections.
- Reading history.
- Goals.
- Download records where appropriate.

User-data migrations must never reset or overwrite existing user data silently.

### Settings DataStore

Contains small configuration values only.

### Audio Storage

Contains downloaded recitations controlled by the user.

Deleting audio must not delete Quran pages, notes or bookmarks.

## 6. Mushaf Rendering Contract

The primary reader must:

- Display a complete Madinah Mushaf page.
- Preserve page composition and word positions.
- Support zoom without text reflow.
- Work entirely offline.
- Restore the last page.
- Allow Ayah interaction through a separate overlay.
- Keep the page source independent from the UI framework.

The following interface concept must be preserved:

```text
MushafPageSource
  ├── getPage(pageNumber)
  ├── verifyPage(pageNumber)
  └── getPageMetadata(pageNumber)

## الكتلة الثانية: تحديث الحالة والرفع وإغلاق Issue #3

```bash
sed -i 's/| #3 | Define Android technical architecture | All technical requirements | Open |/| #3 | Define Android technical architecture | All technical requirements | Completed |/' docs/REQUIREMENTS_TRACEABILITY.md

sed -i 's/3. Resolve issue #3: Android architecture (current priority)./3. Issue #3 completed: Android architecture approved./' docs/REQUIREMENTS_TRACEABILITY.md

cat > PROJECT_STATUS.md <<'EOF'
# NOOR2 Project Status

## Current Phase

Phase 1 — Architecture approved and source preparation.

## Completed

- GitHub repository foundation created.
- Product specification documented.
- Requirements traceability matrix created.
- GitHub Issues #1 through #5 created.
- Android application identity approved in DEC-005.
- Issue #1 completed.
- Quran content source policy documented in DEC-006.
- Full-page Madinah Mushaf reader approved in DEC-007.
- Issue #2 completed.
- Android technical architecture approved in DEC-008.
- Architecture document created.
- Issue #3 ready to be closed.

## In Progress

- Preparing to locate and audit any previous NOOR2 source code.
- Preparing the reproducible Android build plan.
- Defining the Mushaf page-asset prototype.

## Open Foundation Issues

- #4 — Import and audit previous NOOR2 source code.
- #5 — Establish a reproducible Android build.

## Not Started

- Android project source code.
- Gradle build files.
- Quran page asset import.
- Quran metadata database.
- Application UI.
- Automated CI.
- APK or AAB artifacts.

## Current Working Environment

The project owner is currently working from an Android phone using Termux.

Documentation and GitHub administration may continue from the phone.

Android Studio, emulator, full build and extensive source-import work should be performed from the computer.

## Next Recommended Task

Proceed with Issue #4 if previous source code exists.

Otherwise, prepare Issue #5 for execution when computer access is available.

## Last Updated

2026-07-27
