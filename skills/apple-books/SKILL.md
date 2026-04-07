---
name: apple-books
description: Read the local Apple Books library on macOS through SQLite. Use when the user wants to inspect books, highlights, notes, collections, and reading progress without modifying the library.
---

# Apple Books

Use this when the user wants real Apple Books data instead of a guessed reading list.

## Why keep this

- genuinely useful for people who read in Apple Books
- clear read-only scope
- transparent implementation: local SQLite queries, no hidden services
- easy to explain and easy to audit

## Expected runtime

- macOS
- Apple Books opened at least once on this Mac
- `sqlite3` available
- Full Disk Access granted to the host process

## Good workflow

1. resolve the Books database paths dynamically instead of hardcoding filenames
2. list or search books first to get the correct asset ID
3. use that asset ID for highlights, notes, and progress lookups
4. keep all queries read-only

## Useful patterns

```bash
BKLIBRARY_DB="$(ls ~/Library/Containers/com.apple.iBooksX/Data/Documents/BKLibrary/*.sqlite 2>/dev/null | head -1)"
AEANNOTATION_DB="$(ls ~/Library/Containers/com.apple.iBooksX/Data/Documents/AEAnnotation/*.sqlite 2>/dev/null | head -1)"

sqlite3 "$BKLIBRARY_DB" "SELECT ZTITLE, ZAUTHOR, ZREADINGPROGRESS, ZASSETID FROM ZBKLIBRARYASSET WHERE ZTITLE IS NOT NULL ORDER BY ZLASTOPENDATE DESC;"
sqlite3 "$BKLIBRARY_DB" "SELECT ZTITLE, ZAUTHOR FROM ZBKLIBRARYASSET WHERE ZTITLE LIKE '%SEARCH_TERM%' OR ZAUTHOR LIKE '%SEARCH_TERM%';"
sqlite3 "$AEANNOTATION_DB" "SELECT ZANNOTATIONSELECTEDTEXT, ZANNOTATIONNOTE FROM ZAEANNOTATION WHERE ZANNOTATIONASSETID = 'ASSET_ID' AND ZANNOTATIONDELETED = 0;"
```

## Caution

Never write to the Apple Books databases. `INSERT`, `UPDATE`, or `DELETE` can corrupt local data or create iCloud sync problems.
