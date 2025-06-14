# Overview

- [Overview](#overview)
- [Git Status](#git-status)
  - [full status](#full-status)
  - [Short status](#short-status)
- [States of files](#states-of-files)
- [Git Staging Environment](#git-staging-environment)
  - [To stage **any particular file**, we use the following command](#to-stage-any-particular-file-we-use-the-following-command)
  - [To stage **more than one file**, we use the following command](#to-stage-more-than-one-file-we-use-the-following-command)
  - [To stage **all changed files**, we use the following command](#to-stage-all-changed-files-we-use-the-following-command)

&nbsp;

&nbsp;

&nbsp;

# Git Status

We can check the **status** of any file using the following command

### full status

```bash
 git status
```

&nbsp;

### Short status

```bash
 git status -s
```

&nbsp;

&nbsp;

# States of files

Files in your Git repository folder can be in one of 2 states:

- **Untracked** - files that are in your working directory, but not added to the repository

- **Tracked** - files that Git knows about and are added to the repository

&nbsp;

&nbsp;

When you first add files to an empty repository, they are all untracked. To get Git to track them, you need to **stage** them, or **add** them to the staging environment.

&nbsp;

&nbsp;

# Git Staging Environment

As we are working, we may be adding, editing and removing files. But whenever we hit a milestone or finish a part of the work, we should add the files to a Staging Environment.

**_Staged files are files that are ready to be committed to the repository we are working on._**

&nbsp;

<img src="./assets/git workflow.png">

&nbsp;

### To stage **any particular file**, we use the following command

```bash
git add FILENAME
```

&nbsp;

### To stage **more than one file**, we use the following command

```bash
git add FILENAME1, FILENAME2, FILENAME3
```

&nbsp;

### To stage **all changed files**, we use the following command

```bash
git add .
```

or

```bash
git add --all
```

or

```bash
git add -a
```

&nbsp;
