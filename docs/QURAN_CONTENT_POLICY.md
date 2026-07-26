# NOOR2 Quran Content Policy

## Approved Source

- Provider: Tanzil Project
- Approved version: 1.1
- Display text: Uthmani
- Search text: Simple Clean
- Official source: https://tanzil.net

## Integrity Rules

1. Canonical Quran text is immutable.
2. Application formatting must not alter stored Quran text.
3. Search normalization must not overwrite canonical content.
4. Every source file requires a SHA-256 checksum.
5. The application database must preserve stable Surah and Ayah identifiers.
6. Imported content must be checked against the approved source package.
7. Quran content updates require documented review and migration tests.

## License Compliance

NOOR2 must:

- Credit Tanzil Project clearly.
- Provide a link to Tanzil.
- Preserve the required copyright and license notice.
- Distribute Quran text only as an unchanged copy.
- Record the source version used in every release.

## Import Workflow

Before importing Quran data:

1. Download the approved files from the official Tanzil source.
2. Preserve the original files without modification.
3. Generate SHA-256 checksums.
4. Record file names, sizes and checksums.
5. Validate the expected Surah and Ayah mapping.
6. Build application databases from a reproducible import script.
7. Compare imported output against the approved source.
8. Retain the verification report under `docs/evidence/`.

## Release Gate

A release must not ship Quran content unless:

- Source attribution is visible.
- License obligations are satisfied.
- Checksums are recorded.
- Corpus verification succeeds.
- No unexplained text difference exists.
