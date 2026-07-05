# File Structure Modes

> Read this before resolving any material or asset path. Referenced by `:init-course`, `:scaffold-course`, `:create-session`, `:promote-session`, `:coauthor-materials`, `:quick-fix`, `:validate-course`, `:assemble-bundle`, `:create-project`, `:update-project`, `:analyze-existing`, `:create-image`, and `:generate-image`.

Every course runs in exactly one **File Structure** mode, recorded in `journal.md` → `## Course Context` → `__File Structure:__`. Tasks that read or write a material or asset path must resolve it from the active mode below — never hardcode a path shape inline.

## single-file

The entire course is one LiaScript document.

- Course content: `/README.md` (project root). Every session/unit is a `##` chapter inside this one file — not a separate file.
- Assets: `/assets/images/`, `/assets/videos/`, etc. — project root, shared across the whole course.
- No `materials/` folder is created.
- Typical for: `single-lesson`, or any course the instructor explicitly wants as one file.

## multi-file

Each session/unit is its own LiaScript document in its own folder.

- Course content: `materials/{number}-{slug}/README.md` — one folder per session.
- Assets: `materials/{number}-{slug}/assets/images/`, `materials/{number}-{slug}/assets/videos/`, etc. — scoped to that session, not shared with others.
- `{slug}` is a kebab-case slug derived from the session title: lowercase, strip punctuation, spaces → hyphens, truncate to ~5 significant words if the title is long (e.g. "Are You in Scope? Essential vs. Important Entities" → `are-you-in-scope-essential-vs-important`).
- **Compute the slug once**, when the session's material file/folder is first created (`:promote-session`). If the session title changes afterward, do not silently rename the folder — flag the mismatch and ask before renaming, since links and assets may reference the existing path.
- Typical for: `lecture-series`, `self-paced`, `workshop`, or any course with multiple sessions.

## Default by course type

| Course type | Default mode |
|---|---|
| single-lesson | single-file |
| lecture-series | multi-file |
| self-paced | multi-file |
| workshop | multi-file |
| improve-existing | detected from the existing project (see `:analyze-existing`) |

`:init-course` and `:scaffold-course` set this default automatically and state it to the instructor; it can be overridden any time by editing `journal.md` → `## Course Context` → `__File Structure:__`. Structural tasks re-read the field on every run — changing the field alone does not migrate already-existing files (see "Changing mode later").

## Resolving paths

| Task | single-file target | multi-file target |
|---|---|---|
| `:promote-session`, `:coauthor-materials`, `:quick-fix`, `:validate-course` (session mode) | the `##` chapter matching this session inside root `/README.md` | `materials/{number}-{slug}/README.md` |
| `:create-image` / `:generate-image` asset path | `assets/images/{image-slug}.png` (or `/videos/`) | `materials/{number}-{slug}/assets/images/{image-slug}.png` (or `/videos/`) |
| `:assemble-bundle` | copies `README.md` + `assets/` | copies `materials/` (each session folder keeps its own nested `assets/`) |
| `:create-project` / `:update-project` (`project.yaml` → `collection:`) | one entry pointing at root `README.md` | one entry per `materials/{number}-{slug}/README.md` |
| `:analyze-existing` scan | root `README.md` with multiple `##` chapters, no `materials/` folder | `materials/*/README.md` folders |

Note: the **session-folder slug** (`{slug}` above, from the session title) and an **image slug** (from an image's description, used only for the filename) are independent — do not conflate them. A session folder never needs to be renamed when a new image is added to it.

## Changing mode later

Switching modes on an existing course (splitting one file into many, or merging many into one) is a structural migration, not an automatic effect of editing the field. If the instructor asks to switch:
1. Confirm the new mode and the consequences (file moves/merges) before touching anything.
2. Move, split, or merge the material files and their assets accordingly.
3. Update `journal.md` → `## Course Context` → `__File Structure:__` and any path references in `## Agenda` / `## Sessions` to match.
