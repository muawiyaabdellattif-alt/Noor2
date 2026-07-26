# NOOR2 Product Specification

## 1. Product Vision

NOOR2 is a privacy-first, offline-first Quran companion for Android.

The application should provide a calm, trustworthy and accessible experience for:

- Reading the Quran.
- Listening to recitation.
- Searching Quranic content.
- Viewing approved tafsir and translations.
- Saving bookmarks and private notes.
- Managing reading and khatmah goals.
- Using verified Adhkar and Tasbih tools.

## 2. Core Principles

### Privacy First

- No account is required for core use.
- No advertising identifiers.
- No behavioral tracking.
- Personal data remains local by default.
- Users can export and delete their personal data.

### Offline First

The following must work without internet access:

- Quran reading.
- Quran search.
- Bookmarks.
- Notes.
- Reading history.
- Goals.
- Adhkar.
- Downloaded audio.

### Trust and Accuracy

- Quranic text must use a verified source.
- Quran content must be protected from accidental modification.
- Tafsir and translations must show their sources.
- Religious content changes require review.
- Content versions and corrections must be documented.

### Calm Experience

The application must not include:

- Advertisements.
- Public devotional rankings.
- Shame-based messages.
- Manipulative notifications.
- Artificial urgency.

### Accessibility

Essential flows must support:

- TalkBack.
- Large text.
- Screen magnification.
- External keyboard navigation.
- Clear focus order.
- Accessible touch targets.
- Arabic right-to-left layout.

## 3. MVP Scope

### Quran Reader

- Complete offline Quran text.
- Surah navigation.
- Ayah navigation.
- Juz navigation.
- Last-read position.
- Light and dark modes.
- Adjustable Quran text size.
- Reliable Arabic RTL display.

### Search

- Offline Arabic Quran search.
- Safe Arabic normalization.
- Clear loading, result, empty and error states.

### Audio

- Approved reciter selection.
- Ayah and surah playback.
- Background playback.
- System media controls.
- Ayah and range repeat.
- Sleep timer.

### Downloads

- Audio download.
- Pause and resume.
- Download progress.
- Offline availability indicator.
- Storage usage.
- Delete downloaded files.

### Personal Library

- Bookmarks.
- Private notes.
- Tags or collections.
- Sorting and filtering.
- Export and deletion.

### Tafsir and Translation

- Approved sources.
- Clear separation from Quranic text.
- Source and version information.
- Offline packages where legally permitted.

### Goals and Khatmah

- Goals by pages, ayat, reading time or listening time.
- Optional reminders.
- Flexible catch-up.
- No guilt-based language.

### Adhkar and Tasbih

- Verified source information.
- Private local counter.
- Favorites.
- Editable and removable reminders.

### Privacy and Settings

- Permission explanation.
- Local-data explanation.
- Diagnostic controls.
- Export personal data.
- Delete personal data.
- Stop notifications.

## 4. Non-Functional Requirements

### Reliability

- Stable reading position after restart.
- No known critical crashes.
- Safe database migrations.
- Clear error recovery.

### Performance

- Fast application startup.
- Fast local Quran search.
- Smooth reader scrolling.
- Efficient audio playback.
- Controlled battery and storage use.

### Security

- HTTPS-only approved network sources.
- No secrets committed to GitHub.
- Restricted Android exported components.
- Dependency security review.
- Download integrity verification.

### Content Integrity

- Quran corpus checksums.
- Stable surah and ayah identifiers.
- Versioned content packages.
- Documented content provenance.
- Recorded correction history.

## 5. Explicit Non-Goals

The initial release will not include:

- Advertising.
- Behavioral targeting.
- Public social feeds.
- Mandatory registration.
- Public devotional leaderboards.
- Unreviewed AI religious answers.
- AI presented as an authoritative recitation corrector.

## 6. Current Repository Status

The repository currently contains:

- Project documentation.
- Project status.
- Roadmap.
- AI handoff instructions.
- Decision records.
- GitHub contribution templates.

The repository does not yet contain:

- Android source code.
- Quran database.
- Application UI.
- Automated tests.
- APK or AAB release files.

## 7. Open Decisions

The following decisions must be approved before implementation:

1. Official application name.
2. Android application ID.
3. Minimum Android version.
4. Quran text source and license.
5. Quran font and Mushaf asset license.
6. Recitation providers.
7. Tafsir and translation providers.
8. Database technology.
9. Android architecture and module structure.
10. Diagnostics policy.
11. Backup and synchronization policy.
12. Signing-key custody.
13. Release and rollback process.

## 8. Definition of Done

A feature is complete only when:

- It has an approved GitHub issue.
- Acceptance criteria are satisfied.
- Tests are completed.
- Offline behavior is verified.
- Accessibility is verified.
- Privacy and security are reviewed.
- Arabic and English content are reviewed.
- Documentation and project status are updated.

## 9. Next Step

The next controlled step is to create:

- Requirements traceability documentation.
- GitHub MVP issues.
- Architecture decision records.
- Previous-source import and audit plan.
