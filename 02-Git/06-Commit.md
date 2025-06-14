# Overview

- [Overview](#overview)
- [Short status flags](#short-status-flags)
- [Commit](#commit)
  - [Note](#note)
- [Syntax](#syntax)
- [Commit Message Tips](#commit-message-tips)
- [Git Commit without Stage](#git-commit-without-stage)
- [Git Commit Log](#git-commit-log)
- [Common Git Commit Commands](#common-git-commit-commands)
- [Important Notes](#important-notes)
- [Atomic commit](#atomic-commit)
  - [Meaning of unit of work](#meaning-of-unit-of-work)
  - [It should:](#it-should)
  - [Why Use Atomic Commits?](#why-use-atomic-commits)
  - [Example of Atomic commits:](#example-of-atomic-commits)
- [Git snapshot](#git-snapshot)
- [Musketeers of Git](#musketeers-of-git)
  - [Commit Object](#commit-object)
  - [Tree Object](#tree-object)
  - [Blob object](#blob-object)

&nbsp;

&nbsp;

&nbsp;

# Short status flags

| flags | Descriptions         |
| ----- | -------------------- |
| ??    | Untracked files      |
| A     | Files added to stage |
| M     | Modified files       |
| D     | Deleted files        |

&nbsp;

&nbsp;

# Commit

A commit in Git is like a **snapshot** of your project at a particular moment in time.

&nbsp;

Since we have finished our work, we are ready move from `stage` to `commit` for our repo.

Adding commits keep track of our progress and changes as we work.

Git considers each commit **_change point or "save point"_**. It is
a point in the project you can go back to if you find a bug, or want to make a change.

By adding clear messages to each commit, it is easy for yourself (and others) to see what has changed and when.

&nbsp;

## Note

**When we commit, we should always include a message.**

&nbsp;

&nbsp;

# Syntax

```bash
git commit -m "COMMIT-MESSAGE"
```

&nbsp;

&nbsp;

# Commit Message Tips

- Always write clear, descriptive messages.
- **Use the present tense**: "Fix bug" instead of "Fixed bug"
- **Start with a verb**: "Add", "Fix", "Remove", "Update" etc.

&nbsp;

&nbsp;

# Git Commit without Stage

Sometimes, when you make small changes, using the staging environment seems like a waste of time. It is possible to commit changes directly, skipping the staging environment.

The `-a` option will automatically stage every changed, already tracked file.

```bash
git commit -a -m "COMMIT-MESSAGE"
```

&nbsp;

&nbsp;

# Git Commit Log

To view the history of commits for a repository, you can use the `log` command:

```bash
git log
```

&nbsp;

Summary

```bash
 git log --oneline
```

&nbsp;

&nbsp;

# Common Git Commit Commands

| Command                      | Purpose                                          |
| ---------------------------- | ------------------------------------------------ |
| `git commit -m "message"`    | Commit staged changes with message               |
| `git commit -a -m "message"` | Add **and** commit tracked files (skips staging) |
| `git commit --amend`         | Change the message of the **last commit**        |
| `git log`                    | View commit history                              |
| `git show <commit-id>`       | See details of a specific commit                 |

&nbsp;

&nbsp;

# Important Notes

If you try `git commit` without staging, Git will say:

```bash
"nothing to commit, working tree clean"
```

&nbsp;

You can undo the last commit (safely) using:

```bash
git reset --soft HEAD~1
```

&nbsp;

&nbsp;

# Atomic commit

An atomic commit is a commit that contains a single, complete, and coherent unit of work.

&nbsp;

In atomic commit, a commit should contain only one logical change.”

It should be able to stand on its own, without depending on or affecting other commits. It should also have a clear and descriptive message that summarizes the changes made.

### Meaning of unit of work

Here **unit of work** varies from person to person.

For example, if we are creating a webpage. To someone, unit of work may be creating only header. To someone unit of work may be creating some section. To someone, unit of work may be styling the font only and so on.

&nbsp;

&nbsp;

## It should:

- Do one thing only (fix one bug, add one feature, etc.)
- Be small and focused
- Be easily understandable

&nbsp;

&nbsp;

## Why Use Atomic Commits?

| Benefit                 | Explanation                                                       |
| ----------------------- | ----------------------------------------------------------------- |
| 🧠 **Clarity**          | Easy to understand what changed and why                           |
| 🔁 **Easier rollbacks** | You can revert a specific feature or fix without affecting others |
| 🔍 **Code review**      | Easier for reviewers to focus on a single concern                 |
| 📜 **Clean history**    | Makes your Git log readable and meaningful                        |
| ⚙️ **CI/CD Friendly**   | Pinpoint failures in automated pipelines faster                   |

&nbsp;

&nbsp;

## Example of Atomic commits:

```bash
git commit -m "Fix: correct typo in login error message"

git commit -m "Refactor: extract signup logic to new function"

git commit -m "Update: footer alignment in mobile view"
```

&nbsp;

&nbsp;

# Git snapshot

A git snapshot is a specific point in time in the history of code.

It represents a specific version of code, including all files and folders that were present at that time.

Each snapshot is identified by a unique hash code.

Everything is stored as an object and each object is identified by a unique hash code.

Every hash (commit) depends on it's previous commit

&nbsp;

&nbsp;

# Musketeers of Git

There are three musketeers of git

- Commit Object
- Tree Object
- Blob object

&nbsp;

&nbsp;

## Commit Object

Each commit in the project is stored in a `.git` folder.

It contains the following information

- Tree Object
- Parent commit object
- Author
- Committer
- Commit Message

&nbsp;

&nbsp;

## Tree Object

Tree object is a container for all the files and folders in the project.

It contains the following information

- File Mode
- File Name
- File Hash
- Parent Tree Object

Everything is stored as **_key-value pairs_** in the tree project. This key is the filename and this value is the file hash

&nbsp;

&nbsp;

## Blob object

Blob object is present in tree object and contains teh actual file content.

This is the place where the file content is stored.

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;
