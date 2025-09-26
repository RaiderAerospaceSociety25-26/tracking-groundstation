# Contributing Guide

Thanks for contributing! This guide explains the **end-to-end workflow** we use across **Raider Aerospace Society 25-26** repositories—covering firmware (.cpp), dashboards, **CAD/3D models**, **PCB schematics/layouts**, and documentation. The goal is to help every contributor (software or not) ship high-quality changes confidently and predictably.

---

## 0) Big Picture & Mental Model

**Git vs GitHub**

- **Git** lives on your computer and tracks changes as a history of **commits** (checkpoints of additions/deletions). It works offline.
- **GitHub** hosts repos online so we can collaborate (issues, pull requests, reviews) and automate (CI/CD).
  > Think: **Git = engine**, **GitHub = garage** where we park and maintain the vehicles.

**Organization → Repo → Project**

- **Organization**: the umbrella account that owns everything — `RaiderAerospaceSociety25-26`.
- **Repository (repo)**: a single codebase with its own issues, branches, and history (e.g., `srad-flight-computer`, `tracking-groundstation`).
- **Project**: a planning board that aggregates issues/PRs across one or more repos (e.g., `SRAD Flight Computer`, `Tracking Groundstation`).

**Commits are checkpoints, not autosaves**

- Git **does not** store every keystroke or live versions like Google Docs.
- You only get rollback points when you **commit**. If you commit once at the end, you can only roll back to the very start.
- Commit in **small, meaningful chunks** so you can undo just the broken piece without losing good work.

**One-line cycle (high-level)**

> **Pull → Branch → Commit (small chunks!) → Push → PR → Review → Merge → Update**

---

## 1) Start With an Issue

- All work begins as a **GitHub Issue** describing scope, acceptance criteria, and labels (e.g., subsystem, priority).
- Self-assign (or be assigned) when you agree to own it.
- Not sure if it fits? Open an issue first to see if its a good fit before you start working.

---

## 2) Branch & Sync

Start from a fresh `main`, then create a focused branch:

```bash
git switch main                         # Switch to the main branch
git pull origin main                    # Pull from the remote main
git switch -c feat/<short-description>  # Switch to branch <type>/<short-description>
git push -u origin HEAD                 # Initial push of empty branch to trigger a PR option in web
```

Examples: `feat/servo-boot-sequence`, `fix/gps-parsing-bug`, `docs/update-flight-readme`

---

## 3) Make Changes & Commit in Small Chunks

Commit frequently in logical steps:

```bash
git status      # Display changed files staged/unstaged
git add <files> # Stage changed <files> for the next commit `git add firmware/`
git commit -m "feat: add servo boot sequence" # Commit a set of staged changes
```

- Use **Conventional Commits** (`feat`, `fix`, `docs`, `chore`, etc.).
- Rule of thumb: each commit should leave the repo in a **working or reviewable** state.
- Keep in sync while you work:

```bash
git fetch origin                  # fetch the most recent updates
git rebase origin/main            # preferred for clean history
git push --force-with-lease       # push changes only to your feature branch (not to main)
```

**CAD/PCB/Binary assets**

- Large/binary files (STEP, STL, images, PDFs) don’t diff (show change line by line) like code—commit **sparingly** with clear messages.

---

## 4) Push & Open a Pull Request (PR)

Publish your branch so CI and teammates can see it:

```bash
git push
```

Create a PR with the GitHub CLI:

```bash
gh pr create --draft --fill    # start as draft; auto-fills from the PR template
# or
gh pr create --fill            # ready for review
```

- Link the issue: **“Closes #<id>”** so it closes on merge.
- Include motivation, what changed, how to test, and screenshots/renders/logs (for firmware, dashboards, CAD/PCB, etc.).
- Keep PRs focused and reasonably small—large PRs slow reviews.

---

## 5) Continuous Integration (CI)

Every PR runs Actions tailored per repo:

- **Avionics**: PlatformIO builds, unit tests, format checks.
- **Groundstation/dashboard**: Node builds, unit/e2e tests, linting.
- **Docs/CAD/PCB**: validation scripts where available; attach renders/artifacts for reviewers.

> PRs **cannot merge** until all required checks pass.

---

## 6) Reviews & Approvals

- All PRs require approval from a **Code Owner** (e.g team-leads); you cannot approve your own PR.
- **Firmware/docs**: at least **1** approval.
- **Hardware/safety-critical**: at least **2** approvals.
- New commits after approval **dismiss** approvals (re-review needed for changed code).

---

## 7) Merge Strategy

When CI is green and reviews are complete:

- Use **Squash merge** to keep `main` history clean.
- **Auto merge** should be enabled
- After merge:
  - The branch is deleted automatically.
  - Linked issues (via “Closes #…”) close automatically.

---

## 8) After Merge

Update your local environment, switch to `main`, and start your next task from `main`:

```bash
git switch main
git pull origin main
```

---

## 9) Quick Reference

```bash
git pull                             # get most recent updates
git switch -c feat/<name>            # new branch
git add <files> && git commit -m "type(scope): summary"
git push -u origin HEAD              # publish branch (first time)
git push                             # subsequent pushes
gh pr create --draft --fill          # draft PR with template
gh pr create --fill                  # ready PR with template
git fetch origin && git rebase origin/main   # stay current
```

---

### 🔄 One-Line Recap

**Pull → Branch → Commit (small chunks!) → Push → PR → Review → Merge → Update**

Always remember:

- Your computer = **local copy**
- GitHub = **shared truth** (remote)
- Commits = **checkpoints** (not autosaves)
- Smaller, meaningful commits make rollbacks and reviews easier—for **code, CAD, PCB, and docs** alike.
