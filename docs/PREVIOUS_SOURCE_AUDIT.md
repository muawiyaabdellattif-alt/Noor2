# Previous NOOR Source Audit

## Audit Status

Status: In Progress

GitHub issue: #4

## Selected Candidate

- Archive: `Noor_GitHub_Fixed.zip`
- Original location: `/storage/emulated/0/3/نور/Noor_GitHub_Fixed.zip`
- SHA-256: `5e678c29a1580d6e3e71d33c12c00a193ea329bd77dfbd784e68d60a2e7d4039`
- Modified: 2026-07-21
- Archive entries: 530
- Kotlin and Kotlin-script files: 179
- Test-related entries: 99
- Generated build directories in archive: 0
- Project root: `Noor_GitHub_Fixed`

## Comparison Reference

The candidate was compared with:

- `Noor-Flagship-Architecture-Reviewed-2026-07-19.zip`

The comparison found 38 changed or additional paths.

The candidate is a real development of the Flagship version and not only a renamed archive.

## Positive Findings

- Gradle Wrapper JAR is present and structurally valid.
- Room schema exports are present.
- Database integrity check returns `ok`.
- Quran database contains 114 Surahs.
- Quran database contains 6236 Ayahs.
- FTS Quran-search tables contain 6236 indexed Ayahs.
- The archive contains no detected build or Gradle-cache directories.
- The candidate contains extensive unit-test material.
- No obvious committed secret was identified by the initial pattern scan.

## Database Findings

Detected tables include:

- `ayahs`
- `ayahs_fts`
- `bookmarks`
- `surahs`
- `tafsirs`
- Room metadata tables

Key counts:

- Surahs: 114
- Ayahs: 6236
- FTS Ayahs: 6236
- Packaged bookmarks: 0
- Packaged Tafsir records: 0

The packaged database must not yet be treated as an approved Quran source.

Its provenance, generation script and textual contents require comparison with the approved project content policy.

## Critical Mushaf Finding

No complete Madinah Mushaf page assets were found.

No implementation indicating a full-page, fixed-layout Madinah Mushaf reader was found by the current source scan.

Therefore, the previous Reader implementation does not satisfy DEC-007.

The old Reader must not be adopted as the primary NOOR2 Quran reader.

`feature:mushaf` must be implemented or rebuilt according to these requirements:

- Complete Madinah Mushaf pages.
- Hafs from Asim.
- Fixed original page composition.
- No verse-card primary reader.
- No default Ayah text reflow.
- Offline page assets.
- Separate Ayah interaction overlay.
- Verified page-to-Ayah mapping.

## Potentially Reusable Areas

Subject to code review and build verification:

- Domain models.
- Quran search and FTS approach.
- Audio playback components.
- Bookmark and notes logic.
- Adhkar implementation.
- Design-system components.
- Test utilities and existing tests.
- Database migration concepts.

## Areas Requiring Replacement or Major Review

- Primary Quran Reader.
- Application identity and package namespace.
- Quran database provenance.
- Quran database-generation script.
- Tafsir provider implementation.
- Backup and data-extraction configuration.
- Release-signing guidance.
- GitHub Actions security workflows.
- Replit and agent-specific files.

## CI and Security Findings

The candidate contains a phone-oriented APK build workflow.

Compared with the Flagship archive, it does not include all previously available workflows such as:

- CodeQL.
- Dependency review.
- Dependency submission.
- Baseline-profile workflow.
- Full Android CI workflow.

These workflows must be reviewed and restored appropriately.

## Import Decision

The candidate is approved only as the primary legacy-source candidate for further audit.

It is not approved for direct merge into `main`.

A controlled import must occur on a dedicated branch after:

1. Clean build verification.
2. Dependency audit.
3. Complete secret scan.
4. License review.
5. Database-provenance review.
6. Package-identity migration plan.
7. Replacement plan for the old Reader.
8. Review of all GitHub workflows.

## Next Action

When the computer environment is available:

- Create branch `audit/legacy-noor-github-fixed`.
- Import the clean source without build artifacts.
- Attempt a reproducible clean build.
- Run all tests.
- Produce a dependency and security report.
- Catalogue reusable and replaceable components.
