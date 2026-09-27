# Workstream Current Status: Maintenance

Name: `maintenance`

Start date: `2026-09-27`

State: active; permanent maintenance

Definition read: WORKFLOW.md@eabe23ed644a, WORKFLOW-LOCAL.md@05687aa6136c

Branch association: `ws-maintenance/`; no branch yet

## Goal

Own the defects that no open workstream covers, on `main` and on maintained
release lines, and drive maintenance releases, while this repository uses
multiple-streams mode.

## Queue

Read from `main`, not from this file: the bug records under
`engineering-docs/bugs/` whose `owner` is `maintenance` and whose `status` is
neither `closed` nor `retired`. See *Bug Intake* in `WORKFLOW.md`.

## Current State

Bug `engineering-docs/bugs/website/2026-09-27-missing-photo-gallery.md` was resolved, verified, and integrated into `main`:
- Restored `/galerie-foto` with 51 cataloged photos across 3 albums (Bran 2024, FISCA Cap Aurora 2022, Juniori 2016).
- Bundled all image assets locally under `ag-flash3.8-site/public/images/galerie/`.
- Built Lightbox modal viewer with keyboard navigation and album filters.
- Added navigation links in desktop dropdown, mobile drawer, and footer.
- Build verified with `npm run build` (19 pages, 0 errors, 0 warnings).
- Currently 0 open bugs in queue.

## Planned Next Step

Triage any bug whose `severity` is `untriaged`, then take the highest-severity open bug on the current release line.

## Open Threads

- None.
