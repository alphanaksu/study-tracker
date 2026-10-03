# Study Tracker (YKS Çalışma Takip) — instructions for Claude

## Who you're working with
- Owner: Industrial Engineering student, new to programming. Explain decisions in plain language.
- After each task, add 3–5 lines to LEARNING.md: what changed, the concept behind it,
  and one interview question I should be able to answer about it.

## What we're building
A Turkish, installable web app (PWA) for YKS students: log study blocks (subject, minutes,
questions solved, practice-exam net), see a weekly chart and streak, and share a weekly
summary with a coach over WhatsApp. Spec: docs/SPEC.md. Interview notes: docs/interviews.md.

## Stack
Vite, plain JavaScript (no framework unless I approve), CSS, PWA manifest + service worker,
localStorage, Vitest for tests. Hosted on GitHub Pages from /docs on the main branch.

## Commands
- Install: npm install   (run at the start of every session)
- Tests:   npm test
- Build:   npm run build   (output goes to /docs)
- Smoke:   npm run dev   (start, check there are no console errors, stop)

## Layout
- index.html, src/main.js: UI only
- src/storage.js: read/write entries in localStorage
- src/stats.js: weekly totals, streaks, summary text (pure functions, fully tested)
- src/i18n.js: all user-facing text, in Turkish
- public/manifest.webmanifest, public/sw.js: install and offline support
- tests/: Vitest

## Rules
- All user-facing text is Turkish and lives in src/i18n.js.
- In v1 no student data leaves the device: no accounts, no servers, no analytics.
- Must work on small Android phones and on iPhone Safari; check layouts at 360 px width.
- Must work offline after the first visit.
- For anything touching more than one file, show a plan first. One feature per session.
- Ask before adding a dependency.
- If something is ambiguous, ask me instead of guessing.
- End every session by updating PROGRESS.md: done, next, open questions.

## Definition of done
Tests pass, the build succeeds into /docs, no console errors, PROGRESS.md and LEARNING.md updated.
