# Git Crew Sync Workflow Report

## Project Overview
* **Repository**: https://github.com/joshwawi/git-crew-sync-salvador-joshua.git
* **Author**: Salvador, Joshua
* **Workflow**: Two-clone synchronization (Clone A & Clone B)

## Tasks Executed

### Task 1: Feature Implementation (Clone A)
* Created and checked out `feature/overtime-pay`.
* Implemented overtime calculation (1.5x pay rate for hours exceeding 8 hours).
* Pushed changes to origin remote.

### Task 2: Hotfix Branch (Clone B)
* Synced `main` branch with remote.
* Created and checked out `hotfix/rate-cap`.
* Implemented rate cap validation ($100/hr limit).
* Pushed branch to origin remote.

### Task 3: Feature Merge (Clone A)
* Checked out `main` and pulled remote updates.
* Merged `feature/overtime-pay` into `main`.
* Pushed merged `main` to origin remote.

### Task 4: Conflict Trigger (Clone B)
* Pulled updated `main` into Clone B.
* Merged `hotfix/rate-cap` into `main`, triggering a merge conflict on `calculatePay`.

### Task 5: Conflict Resolution & Rebase (Clone B)
* Resolved merge conflict manually by combining overtime pay logic and rate cap validation.
* Committed resolved changes and rebased `hotfix/rate-cap` onto `main`.
* Pushed final state to remote repository.

### Task 6: Documentation & Final Push
* Created `WORKFLOW.md` detailing the entire multi-branch Git workflow.
* Pushed final documentation update to `main`.

# WORKFLOW.md

## Lab Reflection Questions

### 1. What did the rejected push error message tell you, and why did it happen?
* **Error Message**: `[rejected - non-fast-forward]` / `Updates were rejected because the remote contains work that you do not have locally.`
* **Reason**: The remote branch had commits pushed from another clone that were missing in the local repository. Git prevents overwriting remote history unless the local branch includes all upstream changes.

### 2. What's the actual difference between how you resolved Task 3 (merge) vs Task 4 (rebase)?
* **Task 3 (Merge)**: Combined local and remote histories by creating a new merge commit with two parent commits, preserving the true chronological branching history.
* **Task 4 (Rebase)**: Rewrote history by lifting local commits, applying remote commits first, and replaying local commits on top, creating a linear project history without extra merge commits.

### 3. What one habit would have avoided both rejected pushes in this lab?
* **Habit**: Running `git pull` (or `git fetch`) before starting work or attempting to push.

### 4. Which approach - merge or rebase - would you default to on a shared team branch, and why?
* **Default**: **Merge**. 
* **Reason**: Merging preserves historical accuracy and avoids rewriting public branch history, which can disrupt other team members' local copies. Rebase is better suited for local feature branches before merging into main.

# WORKFLOW.md

## Lab Reflection Questions

### 1. What did the rejected push error message tell you, and why did it happen?
* **Error Message**: `[rejected - non-fast-forward]` / `Updates were rejected because the remote contains work that you do not have locally.`
* **Reason**: The remote branch had commits pushed from another clone that were missing in the local repository. Git prevents overwriting remote history unless the local branch includes all upstream changes.

### 2. What's the actual difference between how you resolved Task 3 (merge) vs Task 4 (rebase)?
* **Task 3 (Merge)**: Combined local and remote histories by creating a new merge commit with two parent commits, preserving the true chronological branching history.
* **Task 4 (Rebase)**: Rewrote history by lifting local commits, applying remote commits first, and replaying local commits on top, creating a linear project history without extra merge commits.

### 3. What one habit would have avoided both rejected pushes in this lab?
* **Habit**: Running `git pull` (or `git fetch`) before starting work or attempting to push.

### 4. Which approach - merge or rebase - would you default to on a shared team branch, and why?
* **Default**: **Merge**. 
* **Reason**: Merging preserves historical accuracy and avoids rewriting public branch history, which can disrupt other team members' local copies. Rebase is better suited for local feature branches before merging into main.

---

## Screenshot Evidence

### Task 1 Evidence
![Task 1 Evidence](screenshots/task1.png)

### Task 2 Evidence
![Task 2 Evidence](screenshots/task2.png)

### Task 3 Evidence
![Task 3 Evidence](screenshots/task3.png)

### Task 4 Evidence
![Task 4 Evidence](screenshots/task4.png)

### Task 5 Evidence
![Task 5 Evidence](screenshots/task5.png)

### Task 6 Evidence
![Task 6 Evidence](screenshots/task6.png)