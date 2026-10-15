# Versioning

Parallax versions have three numbers: **MAJOR.MINOR.PATCH**. A version ending in `.0` is
shown without it, so releases read `1.0`, `1.1`, `1.1.1`, `1.2`, `2.0`.

The first release under these rules is **1.0**. Everything before it (0.1.0 to 0.5.113) was
the development line and keeps its old numbers.

## Which number moves

| Change | Example | Number |
|---|---|---|
| Revamp | 1.4 → **2.0** | MAJOR |
| New feature | 1.4 → **1.5** | MINOR |
| Fix or tweak | 1.4 → **1.4.1** | PATCH |

### Patch: fixes and tweaks (1.4 → 1.4.1)

Something that already exists works better or reads better. Nobody has to learn anything new.

- A bug fix, including a fix to how an amount is calculated or posted
- Wording, labels, layout, colours, print fit
- Speed
- A missing button or field added to an existing screen

A patch never changes the database structure.

### Minor: something new (1.4 → 1.5)

The app can do something it could not do before, or the data underneath it changed.

- A new screen, report, document type or workflow
- A new setting or business rule
- **Any database change**: a new table, a new column, a migration that rewrites data
- A change to *what* gets posted to the books (as opposed to fixing a wrong amount)
- Anything that HQ and the tills must run at the same version

### Major: a revamp (1.x → 2.0)

The app is rebuilt in a way people will notice on day one.

- A module or the whole interface redesigned
- A data migration that cannot be rolled back
- Anything that needs every till set up again, or staff retrained

## Rules

1. **The biggest change in a release decides its number.** Nine tweaks and one new column
   make a minor release.
2. **Lower numbers reset.** After 1.4.3 comes 1.5, then 1.5.1. After 1.9.2 comes 2.0.
3. **Numbers do not stop at 9.** 1.4.9 is followed by 1.4.10. 1.9 is followed by 1.10 (or 2.0
   if it is a revamp).
4. **No leading zeros.** Write `1.0.1`, not `1.0.01`. The auto-updater reads versions as
   semantic versions and refuses a leading zero. `1.0.10` already sorts after `1.0.9`, so
   padding is never needed.
5. **A published number is never reused.** A broken release is fixed by the next patch. It
   is not deleted or replaced, because tills may already have installed it.
6. **Same-day fixes are separate patches.** 1.5 in the morning and 1.5.1 in the evening is
   normal.

## How a version is written where

| Where | Form | Example |
|---|---|---|
| In the app (login screen, Settings) | short | Parallax 1.5 |
| GitHub release title | short | Parallax 1.5 |
| Git tag, `package.json`, update manifests | full | v1.5.0 / 1.5.0 |

The full form exists because the updater needs all three numbers. A `.0` patch is dropped
only when the version is shown to people.

## Release notes

Every release on GitHub has a title (`Parallax 1.5`) and notes in this shape. Leave out any
heading with nothing under it.

```markdown
## New
- Inventory ▸ Price Update: raise sale prices on everything a material goes into.

## Changed
- Printed reports fit A4 without splitting words.

## Fixed
- Supplier List search no longer blanks the window.

## Before you update
- Database update. Take a backup on HQ first. Update HQ before the tills.
```

Write for the person using the app, not the person who built it. One line per change,
named by where it is in the app. No ticket numbers, file names or internal terms.
