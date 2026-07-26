# AI Handoff Guide

This file tells any developer or AI assistant how to continue NOOR2 without losing context.

## Required Reading Order

Before making changes, read:

1. `README.md`
2. `PROJECT_STATUS.md`
3. `ROADMAP.md`
4. `docs/DECISIONS.md`
5. Relevant specifications and GitHub issues

## Source of Truth

GitHub is the official source of truth.

Do not rely only on chat history or undocumented assumptions.

## Before Starting Work

- Confirm the current branch.
- Run `git status`.
- Read the latest project-status file.
- Review open GitHub issues.
- Confirm that the requested task is approved.
- Do not invent product requirements.

## After Completing Work

- Update `PROJECT_STATUS.md`.
- Update `ROADMAP.md` when milestones change.
- Record important decisions in `docs/DECISIONS.md`.
- Add or update tests where applicable.
- Create a clear commit message.
- State what was completed and what remains.

## Important Constraints

- Privacy-first.
- Offline-first wherever technically possible.
- Arabic-first user experience.
- Quranic text accuracy is critical.
- No secret keys or sensitive user information may be committed.
- Do not silently change approved requirements.
- Major architectural changes require an explicit decision record.

## Current Handoff

The repository foundation has been created.

No Android application source code exists yet.

The next task is to organize the approved comprehensive specification and convert it into implementable requirements and GitHub issues.
