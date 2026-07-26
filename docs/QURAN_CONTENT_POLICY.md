# NOOR2 Quran Content Policy

## Primary Reader

The default Quran reader must display complete pages matching the printed Madinah Mushaf.

- Narration: Hafs from Asim.
- Visual source: official digital Madinah Mushaf issued by King Fahd Glorious Quran Printing Complex.
- Reading style: complete Mushaf pages.
- Offline availability: required.
- Verse cards: prohibited as the primary reading interface.
- Reflowed individual ayat: prohibited in the default reader.

## Reader Interaction

Users may:

- Turn complete pages.
- Zoom without changing the page composition.
- Select an ayah through an invisible or translucent overlay.
- Play an ayah.
- Open tafsir or translation.
- Add a bookmark or note.

These interactions must not change the original page layout.

## Text and Search Data

Structured Quran text may be used internally for:

- Offline search.
- Ayah identification.
- Audio synchronization.
- Bookmarks.
- Tafsir and translation links.
- Accessibility support.

Internal text data must remain aligned with the visible Mushaf page and must never replace it in the primary reader.

## Integrity Requirements

- Original page assets must remain immutable.
- Every source asset must have a SHA-256 checksum.
- Page-to-ayah mapping must be verified.
- Surah, ayah, juz and page identifiers must remain stable.
- No page may be manually edited.
- Any conversion of official source assets must be reproducible and verified.
- Visual comparison tests must be performed against the approved Madinah Mushaf.

## Accessibility

A separate accessible text presentation may be provided for TalkBack and large-text users.

It must be clearly identified as an accessibility mode and must not replace the full-page Mushaf as the default visual experience.

## Release Gate

No Quran reader release is permitted unless:

- Complete-page rendering is verified.
- Page order is verified.
- Page-to-ayah mapping is verified.
- Offline reading succeeds.
- Source rights and attribution are documented.
- No unexplained visual or textual difference exists.
