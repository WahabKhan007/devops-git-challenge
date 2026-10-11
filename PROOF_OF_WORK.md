# PROOF OF WORK: DevOps Class Activity

**Practical Version Control Workflow Verification Challenge**

| Field | Details |
|---|---|
| Student Name | Abdul Wahab Khan |
| SAP ID | 55072 |
| Section | SE7-1 |
| Date | 10 / 11 / 2026 |
| Repository | `devops-git-challenge` |
| Repository URL | https://github.com/WahabKhan007/devops-git-challenge |

---

## 1. Git Log Output

Command executed on the `main` branch after merging the Pull Request and pulling the latest changes:

```bash
git log --oneline
```

Output:

```text
6b79dc9 (HEAD -> main, origin/main) Merge pull request #1 from WahabKhan007/development
13cd1b1 (origin/development, development) fix: resolved merge conflict
ee7111a (origin/staging, staging) fix: staging label
33b6dca feat: updated script with staging env
20dbf40 feat: initial commit with deploy script

```

> The history should show: the initial commit, the staging-environment update, the staging label fix, the conflict-resolution commit, and the merge commit created by the Pull Request.

---

## 2. Reflection Questions

### Q1: What is the difference between Git (local tracking) and GitHub (cloud platform)?

Git is a distributed version control system that is installed on a developer's own computer. It tracks every change made to files, stores the full history in a hidden `.git` folder, and lets a developer create branches, commit, merge, and stash entirely offline. GitHub, on the other hand, is a cloud-based hosting platform that stores Git repositories on remote servers so that they can be shared. It adds collaboration features on top of Git, such as Pull Requests, issue tracking, code review, access control, and CI/CD integration. In short, Git is the tool that does the version tracking, while GitHub is the online service that hosts the repositories and enables teamwork around them.

### Q2: Explain the three architecture stages: Working Directory, Staging Area, and Local Repository.

The Working Directory is the actual folder on the computer where files are created and edited, and any change made here is only "modified" and not yet tracked for saving. The Staging Area (also called the Index) is an intermediate zone where selected changes are placed using `git add`, which lets the developer choose exactly what will be included in the next commit. The Local Repository is the `.git` database where Git permanently stores committed snapshots after `git commit` is run, forming the project history. Changes therefore flow in one direction: Working Directory, then `git add` to the Staging Area, then `git commit` to the Local Repository, and finally `git push` sends them to the remote repository.

### Q3: What is the difference between `git stash pop` and `git stash apply`?

Both commands restore the most recently stashed changes back into the working directory so that work can continue. The key difference is what happens to the stash entry afterwards. `git stash pop` applies the changes and then removes that entry from the stash list, so it is gone once restored. `git stash apply` applies the same changes but keeps the entry in the stash list, which is useful when the same changes need to be applied to several branches or when the developer wants a backup in case of a conflict. If `pop` hits a conflict, Git also keeps the stash so nothing is lost.

### Q4: What is the difference between `git fetch` and `git pull`?

`git fetch` downloads new commits, branches, and tags from the remote repository and updates the remote-tracking branches such as `origin/main`, but it does not change the local working files or the current branch. This makes it a safe way to see what others have done before deciding to integrate it. `git pull` is a combination of two operations: it runs `git fetch` and then immediately merges (or rebases) the fetched changes into the current local branch. As a result, `git pull` updates the working directory directly and can create merge conflicts, while `git fetch` never does.

---

*End of PROOF_OF_WORK.md*
