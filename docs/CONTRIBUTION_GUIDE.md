# Contributing Guide

Thanks for contributing! This guide explains the workflow we use in all repos under **Raider Aerospace Society 25-26**. Following these steps keeps our codebase consistent, stable, and easy to maintain.

---

## 1. Start With an Issue

- All work begins as a **GitHub Issue**.
- Issues describe the scope of work, acceptance criteria, and labels (e.g., subsystem, priority).
- Tasks are **assigned** to a contributor when they agree to own it.
- If you think something is missing, open a new issue first.

---

## 2. Create a Branch

1. Make sure your local `main` is up to date:
   ```bash
   git switch main
   git pull origin main
   ```
2. Create a branch for your task:
   ```bash
   git switch -c feat/<short-description>
   ```
3. Push the branch to GitHub
   ```bash
   git push -u origin HEAD
   ```

---

## 3. Do the Work

- Commit in small, logical chunks:
  ```bash
  git add <files>
  git commit -m "feat: add servo boot sequence"
  ```
- Keep your branch focused on the assigned issue.
- If `main` has moved ahead, sync:
  ```bash
  git fetch origin
  git rebase origin/main # or git merge origin/main
  git push --force-with-lease # only if you rebased
  ```

---

## 5. Continuous Integration (CI)

- Every PR runs GitHub Actions:
  - Firmware builds with PlatformIO
  - Additional checks (KiCad, formatting, tests) as they are added
- PRs cannot merge until all checks pass

---

## 6. Code Review

- All PRs require approval from a **Code Owner**
- You cannot approve your own PR
- **Firmware/docs:** at least 1 approval
- **Hardware/safety-critical**: at least 2 approvals
- If you push new commits after approval, previous approvals are dismissed and the PR must be re-approved

---

## 7. Merge

- When CI is green and approvals are complete:
  - Use **Squash merge** to keep history clean
  - Enables **Auto-merge** if you want GitHub to merge as soon as requirements are met
- After merge:
  - The branch is automatically deleted
  - The linked issue closes automatically

---

## 8. After Merge

- Update your local `main`:
  ```bash
  git switch main
  git pull origin main
  ```
- Start your next task by creating a new branch from `main`.

---

## Quick Reference

- `git switch -c feat/<name>` -> new branch
- `git push -u origin HEAD` -> publish branch
- `gh pr create --draft --fill` -> open draft PR (GitHub CLI)
- `git fetch origin && git rebase origin/main` -> keep branch in sync
