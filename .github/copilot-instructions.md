<!--
  .github/copilot-instructions.md
  Purpose: Provide concise, repository-specific guidance for AI coding agents working
  on the "OctoFit Tracker" workshop repository.
  Keep this file short (20-50 lines) and concrete. Update when the project structure
  or key workflows change.
-->

# OctoFit Tracker — Copilot agent instructions

This repository is a workshop scaffold for the OctoFit Tracker app (frontend: React, backend: Django REST, DB: MongoDB). Use these concise rules to be productive immediately.

- Repository intent: see `docs/octofit_story.md` for the product goals and feature list (user profiles, activity logging, teams, leaderboard).

- Project layout expectations (convention used by workshop):
  - `octofit-tracker/backend/` — Django REST API project (virtualenv, `requirements.txt` per `.github/instructions` attachments).
  - `octofit-tracker/frontend/` — React app frontend.
  - When creating commands/paths in instructions, use absolute paths rooted at repository workspace (do not `cd`).

- Environment & setup notes:
  - The workshop expects a Python venv at `octofit-tracker/backend/venv` and a `requirements.txt` in the same folder (see `.github/instructions/octofit_tracker_setup_project.instructions.md`).
  - Preferred database is MongoDB (djongo/djongo ORM). Avoid direct MongoDB shell scripts — always prefer Django ORM models/migrations.

- Branching & commits:
  - When making multi-file changes, create a feature branch and open a PR. Keep commits small and focused.

- Coding patterns and project-specific conventions to follow:
  - Backend: prefer Django REST Framework serializers and viewsets for API endpoints instead of hand-rolled JSON responses.
  - Database models should be expressed as Django models (use djongo compatibility shims where needed).
  - Frontend: standard React components and fetch/axios calls to the backend API. Look for existing `frontend/` structure when adding components.

- Helpful examples to reference in your edits:
  - High-level goals and endpoints to implement: `docs/octofit_story.md` (activity logging, teams, leaderboard).
  - Setup and package requirements: `.github/instructions/octofit_tracker_setup_project.instructions.md` (venv creation, required packages).

- Workflows and commands the agent can suggest or run (do not assume outside CI):
  - Create venv: `python3 -m venv octofit-tracker/backend/venv`
  - Activate and install: `source octofit-tracker/backend/venv/bin/activate` then `pip install -r octofit-tracker/backend/requirements.txt`
  - Always use absolute paths for filesystem operations and tests in this repo.

- What NOT to change or assume:
  - Do not expose or modify forwarded port conventions mentioned in the setup instructions (8000, 3000, 27017).
  - Do not remove or rename `docs/octofit_story.md` or the `.github/instructions/` files; they are canonical for the workshop.

- If you need to add a test file or new dependency, include a short note in the PR description explaining the reason and any setup steps.

If anything here is unclear or a specific area of the codebase needs extra coverage (example endpoints, typical model fields), ask for the file or feature to target and I will expand this instruction file with examples.
