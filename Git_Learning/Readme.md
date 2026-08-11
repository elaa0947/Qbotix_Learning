# My Git & GitHub Notes

## What is Git?
Git is a tool that saves the history of my project. Every time I finish some work, I "commit" it, and Git remembers that version. If I mess up later, I can go back to an older version.

## Why we use Git (Use cases)
- To save different versions of my code without making copies like final1, final2, finalUSE THIS
- To undo mistakes and go back to old working code
- To work with friends on the same project without overwriting each other's work
- Used in almost every college project, hackathon, and job (companies use it daily)

## Git vs GitHub (the confusing part)
- Git = a tool on my own laptop that tracks changes. Works offline.
- GitHub = a website where I upload my Git project so I can store it online and share it. Needs internet.

Simple way to remember: Git saves history on my PC, GitHub stores that history online.

## Basic meanings
- Repository (repo) = the project folder Git is tracking
- Commit = a saved checkpoint with a message
- Branch = a separate copy to try new things without touching main code
- Push = send my saved work to GitHub
- Pull = get latest work from GitHub
- Clone = download someone's GitHub repo to my PC
- Fork = my own copy of someone else's repo, on GitHub itself
- .gitignore = file that tells Git which files to skip (like passwords, node_modules)

---

## Git Basics
1. git add . — stage all changed files
2. git status — see what changed
3. git commit -m "present tense, imperative" — save the checkpoint (e.g. "add login page", not "added login page")
4. git init — start tracking a folder (only once per project)
5. touch .gitignore — create ignore file (can use an online gitignore generator for different project types)

## Git Config (first time / setup)
1. git log --oneline — short history, one line per commit
2. git config --global user.name "user_name"
3. git config --global user.email "your_email@example.com"
4. git config --global core.editor "code --wait" — sets VS Code as Git's default editor

## Git Branch
1. git branch name — create a new branch
2. git branch — view current branch / list all branches
3. git checkout -b name (or git switch -c name) — create AND switch to new branch
4. git checkout master — go back to main branch
5. git merge branch_name — merge a branch into current branch (try to always be ON the branch you're merging INTO)
6. git branch -d branch_name — delete a branch

## Other Useful Commands
1. git diff — compare working directory with staging area
2. In diff output: `a` is file1 (old) and `b` is file2 (new) → shown as ---file1 / +++file2
3. git diff --staged — compare staged changes with last commit
4. git diff id..id2 — compare two commits (using commit hashes)
5. git diff branch1..branch2 — compare two branches
6. git stash — lets me switch branches without committing half-done work in the current branch
7. git stash pop — bring back the stashed changes (applies + removes from stash list)
8. Stash isn't limited to one branch — I can stash on one branch and pop it on another
9. git stash list — see all stashed changes
10. git stash apply — applies stash but KEEPS it in the list (unlike pop, which removes it)

## More Commands
1. git checkout <hash> — go to a specific old commit (use git reflog to find previous HEAD positions)
2. git switch main — simpler way to switch to main branch
3. git checkout HEAD~2 — go back 2 steps from current position (2 = number of steps)
4. git restore filename — undo changes in a file (bring back last saved version)

## Git Rebase (be cautious!)
1. Alternative to merging — used as a "clean up" tool for history
2. Important: only run rebase on your own branch, NEVER on main/master
3. git rebase master — rebase current branch on top of master
4. If conflict happens, fix it manually then run: git rebase --continue

---

## GitHub

### Renaming branch + connecting to GitHub
1. git branch -M main — rename current branch to "main"
2. Set up SSH key connection so I can push code without typing password every time

### Working with remotes
1. git remote -v — see connected remote repos
2. git remote add origin url — connect local repo to a GitHub repo
3. git remote rename oldname newname — rename a remote
4. git remote remove name — remove a remote connection

### Push
1. git push origin main — push branch to remote
2. git push -u origin main — the -u (upstream) sets default, so later I can just type `git push`

### Clone / Pull / Fetch
1. git clone url — download a GitHub repo to my PC
2. git fetch — only checks/downloads info about the remote repo, doesn't merge
3. git pull = git fetch + git merge (gets latest changes AND merges them in)

### Contributing to someone else's repo (Fork workflow)
1. Fork it — creates my own copy of their repo on GitHub
2. Clone my fork and open it in VS Code
3. Never work directly on someone's main branch — always create a new branch
4. Make my changes in that branch, then git add + git commit
5. git push origin mybranch_name
6. Go to GitHub → "Compare & Pull Request" → write a clear title & description (be careful/clear here, since maintainers read this)

---

## Mistakes I should avoid
- Don't forget git add before git commit
- Don't push passwords or .env files, use .gitignore
- Don't write useless commit messages like "abc"
- Pull before I push, so I don't miss teammates' changes
- Don't rebase on main/master
- Don't work directly on someone else's main branch when contributing

## One line summary
Git saves my project history on my laptop. GitHub stores it online so I can share and back it up. Push sends my work up, pull brings latest work down, fork + branch + PR is how I contribute to others' projects.