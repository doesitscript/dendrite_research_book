# Instructions: research-based versioning + git tags (Neural Cognitive)

## Purpose
This repo is treated like a "binder-book" research artifact. Versioning is snapshot-based (date + increment), not semantic.

## Project provenance
- ChatGPT project context: Neural Cognitive
- Conversation/chat name: Ten
- This repo is an exported "book" of bookmarks/chapters

## 1) Version scheme

### Version format
`rYYYYMMDD.n[-label]`

- YYYYMMDD: snapshot date (America/Chicago)
- n: increment for multiple snapshots on the same day (0, 1, 2, ...)
- label (optional): notes | refs | struct | cleanup | scope | data | proto | initial

### Examples
- r20251230.0-initial
- r20251230.1-notes
- r20260102.0-refs
- r20260105.0-struct

## 2) Git tag scheme

### Tag format
`nc-dendrite-rYYYYMMDD.n[-label]`

### Examples
- nc-dendrite-r20251230.0-initial
- nc-dendrite-r20251230.1-notes
- nc-dendrite-r20260102.0-refs

## 3) Files that must exist

**Root:**
- VERSION.txt (contains only the current version string)
- README.md (includes Source section referencing Neural Cognitive and chat name Ten)
- CHANGELOG.md (short entries per snapshot version)

**Metadata:**
- META/source.md (structured provenance info, kept stable over time)

**Each chapter folder:**
- summary.md (current working summary)

## 4) Apply this now (next commit)

### Step A: Set version
- Decide next snapshot version (likely r20251230.0-initial if you want to align with the first export date, otherwise use today's date).
- Update VERSION.txt to that exact string.

### Step B: Add provenance
- In README.md add a "Source" section:
  - ChatGPT project: Neural Cognitive
  - Conversation/chat name: Ten
  - Intent: binder-book research export

- Create META/source.md with the same information plus a brief note of the initial scope:
  - Chapters: Diet, Supplements, Dendritic_Function, Relaxing_Prefrontal_Cortex, Physician_Conversations

### Step C: Add changelog
- Create/append CHANGELOG.md with an entry for the snapshot version:
  - date
  - what changed (short bullets)

### Step D: Commit and tag
- Commit message format (suggested):
  - "snapshot: rYYYYMMDD.n[-label] - <short description>"

- Create the git tag matching the scheme:
  - nc-dendrite-rYYYYMMDD.n[-label]

## 5) Minimal commit labels (use these consistently)

- notes: content additions to summaries, new ideas captured
- refs: citations added/updated, source validation work
- data: tables, metrics, structured lists added
- struct: folder/chapter restructure, renames, reorg
- cleanup: formatting, typos, dedupe, small edits
- scope: new chapter added or major expansion of coverage
- proto: rough snapshot before refinement

## 6) Reminders: questions to ask later (do not implement today)

Ask Josh (or remind Josh to ask ChatGPT):
- How should versioning expand to leverage Obsidian features (frontmatter, backlinks, properties)?
- Should we introduce Obsidian-friendly metadata (YAML frontmatter) per file, and how does that affect commit labeling?
- What commit scenarios do we want as a selectable menu (notes vs refs vs struct vs cleanup vs scope vs data)?
- For restructure events: do we want "struct" as a label only, or a separate "major snapshot" convention?
- Should we add a "release snapshot" concept distinct from normal commits, or keep everything as snapshots?
- Should we maintain a mapping index file (INDEX.md) that lists chapters + last-updated version to help navigation?


