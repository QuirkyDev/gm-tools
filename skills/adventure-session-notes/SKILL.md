---
name: adventure-session-notes
description: Turn supplied tabletop adventure session notes into a session Markdown file, update the adventure README session table, and add relevant character-specific notes to existing player files.
---

# Adventure session notes

Use this skill when the user supplies session notes for an adventure and wants them recorded in this repository.

## Inputs

Collect or infer these from the user's message and current conversation:

- Adventure type: `long`, `short`, or `oneshot` (maps to `adventures/longstories`, `adventures/shortstories`, or `adventures/oneshots`).
- Adventure folder/name within that type.
- Session number.
- Session title.
- Raw session notes.

If a required value is missing or the adventure folder cannot be identified unambiguously, ask only for the missing detail. Resolve adventure names case-insensitively when there is one clear match.

## Workflow

1. Locate the adventure folder at `adventures/<mapped-type>/<adventure>/`. Read its `README.md` and inspect its `players/` directory and existing notes. Create `notes/` if it does not exist.
2. Create `notes/session-<session-number>.md`, preserving the supplied session number in the filename (for example, session `3` becomes `session-3.md`). Start the file with the session title as the highest-level Markdown heading (`# <title>`), followed by a cleaned-up version of the supplied notes.
3. Clean up spelling, punctuation, organization, and readability while preserving the user's meaning, facts, sequence, names, and uncertainty. Do not invent events or resolve ambiguous details. Keep the language of the supplied notes unless the user asks for a translation.
4. Add one row to the existing session-notes table in the adventure `README.md`, with the session number, title, a concise relevant summary, and a relative Markdown link to `notes/session-<session-number>.md`. Preserve the table's existing format and entries. If no session-notes table exists, add a `## Session notes` section with columns for session, title, summary, and session file. Do not modify unrelated README content.
5. Use the adventure README's Players table to identify the players and character files to consider. Match each listed player/character to its existing `.md` file in `players/`, paying attention to alternative names or aliases recorded in the table or character file when checking whether the session notes mention that character. For each listed player whose character has relevant, character-specific content in the session notes, add a section to that character's file. Use a level-two heading containing both session number and title, such as `## Session 3: The Old Bridge`, then summarize only that character's relevant events, knowledge, decisions, relationships, or developments. Preserve existing file content and append the new section. Do not create player files or add generic events.
6. Avoid duplicate README rows or duplicate character sections for the same session. If the session file already exists or an existing session entry/section conflicts with the supplied details, inspect it and update only when it is clearly the same session; if that is uncertain, ask before replacing or merging content.
7. Report the files created or updated and mention any characters for whom a section was added. Do not claim a character was updated if no relevant detail was present.

## Repository conventions

- Supported type folders: `long` → `longstories`, `short` → `shortstories`, `oneshot` → `oneshots`.
- Session files belong in the adventure's `notes/` folder.
- The adventure README's Players table determines which players/characters are considered for character-specific session updates; match them to existing Markdown files in `players/`, accounting for alternative names or aliases.
- All README session links should be relative to the adventure folder and point to the session file.
