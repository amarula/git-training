---
theme: ../template
transition: slide-left
mdc: true
layout: cover
hideInToc: true
---

# Git
## An introduction to git
### Michael Nazzareno Trimarchi

---
layout: default
---

# Part 1: Introduction to Version Control

<div class="center">

A Version Control System (VCS) is a software tool that meticulously tracks changes to files over time. It's like having a detailed history book for your project.  Think of it as a system that not only saves different versions of your files but also records who made each change and when. This allows you to revert to previous versions if needed, compare modifications side-by-side, and collaborate effectively with others on the same project without overwriting each other's work.

By maintaining a detailed history, a VCS significantly enhances teamwork, prevents accidental data loss by providing backups, and simplifies the management of evolving codebases or documents, especially in complex projects where multiple people are involved. It's an indispensable tool for any serious software development or collaborative writing effort.

</div>

---
layout: default
---

# What is Version Control?

<div class="center">

* Records changes to a file/set of files over time: Instead of just saving the latest version, a VCS keeps a record of every single modification. This includes additions, deletions, and changes to the content of your files. Each change is like a snapshot in time.
*  A "time machine" for your code: This is a great analogy. You can go back to any previous version of your code or documents. If you introduce a bug or decide you don't like a change, you can easily revert to a working state.
* Essential for modern software development: Modern software development is rarely a solo effort. Teams of developers work on the same codebase, and VCS is crucial for managing their contributions, preventing conflicts, and ensuring everyone is on the same page. It also automates many backup and merging tasks.

</div>

---
layout: default
---

# Why Use Version Control?

<div class="center">

* **Track Changes:** See who, what, and when for accountability and debugging.
* **Collaboration:**  Enables teamwork, avoiding overwrites; VCS merges changes.
* **Experimentation:** Safely explore new features; discard branches if needed.
* **Rollback:** Revert to stable versions after errors.
* **Branching/Merging:** Develop features in parallel; integrate changes cleanly.

</div>

---
layout: default
---

# Benefits: Track Changes

<div class="center">

* **Detailed history of every modification:** A complete log of changes.
* **Understand project evolution:** See how the project has grown.
* **Accountability and traceability:** Track who made each change.

</div>

---
layout: default
---

# Benefits: Collaboration

<div class="center">

* Multiple developers on the same project.
* Manage contributions efficiently.
* Resolve conflicts systematically.

</div>

---
layout: default
---

# Benefits: Experimentation

<div class="center">

* Isolate new features or bug fixes.
* Test without affecting the main codebase.
* Revert easily if things go wrong.

</div>


---
layout: default
---

# Benefits: Rollback

<div class="center">

* Quickly revert to a previous state.
* Undo mistakes or recover from errors.
* Maintain stability.

</div>

---
layout: default
---

# Benefits: Branching and Merging

<div class="center">

* Develop features in parallel.
* Isolate unstable code.
* Integrate changes cleanly.

</div>

---
layout: default
---

# Introduction to Git

<div class="center">

* Distributed Version Control System (DVCS).
* Created by Linus Torvalds (2005) for Linux kernel.
* Focus on speed, data integrity, and distributed workflow.

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e0/Git-logo.svg"
     style="background-color:white; padding:10px; border-radius:10px; width:200px"/>

</div>

---
layout: default
---

# Git vs. Other VCS

<div class="center">

| Feature        | Git (Distributed)                               | SVN (Centralized)                             |
| :------------- | :---------------------------------------------- | :-------------------------------------------- |
| Model          | Decentralized, local copies                     | Central server, single repository             |
| Speed          | Fast for most operations                        | Slower for many operations                    |
| Offline Work   | Full history available, work offline            | Requires network connection                   |
| Branching      | Lightweight, efficient                          | More complex, less efficient                  |

</div>


---
layout: default
---

# Part 2: Getting Started with Git

<div class="center">

VCS keeps a record of every modification, like snapshots in time.
It's a \"time machine\" for your code, allowing you to revert to any previous
version if needed. Version control is essential for modern software development,managing contributions, preventing conflicts, and automating tasks.

</div>

---
layout: default
---

# Installing Git

<div class="center">

* **Windows:** [https://git-scm.com/download/win](https://git-scm.com/download/win)
* **macOS:** [https://git-scm.com/download/mac](https://git-scm.com/download/mac) (or `brew install git`)
* **Linux:** `sudo apt-get install git` (Debian/Ubuntu), `sudo yum install git` (Fedora/CentOS)

</div>

---
layout: default
---

# Checking Installation

<div class="center">

```
git --version

```

-   Verifies Git is installed correctly.
-   Displays the installed Git version.


</div>

---
layout: default
---

# Basic Git Configuration

<div class="center">

-   Set username:

    ```
    git config --global user.name "Your Name"

    ```

-   Set email:

    ```
    git config --global user.email "your.email@example.com"

    ```

-   `--global`: Applies to all repositories.

Those changes are applied to your .gitconfig file in home directory

</div>

---
layout: default
---

# Checking Configuration

<div class="center">

```
git config --list

```

-   Displays all Git configuration settings.

-   Use `git config --local <key>` for repository-specific settings.

</div>

---
layout: default
---

# Initializing a Repository

<div class="center">

git init creates a new, empty Git repository in the current directory.

-   Repository (.git): Hidden directory containing project history.

-   Command:

    ```
    git init

    ```

-   Example:

    ```
    mkdir my-project
    cd my-project
    git init

    ```

</div>

---
layout: default
---

# Working Directory, Staging Area, Repository

-   **Working Directory:** Your project's files.
-   **Staging Area (Index):** Where you prepare changes for commit.
-   **Repository (.git):** Stores the commit history.

<img src="https://git-scm.com/book/en/v2/images/areas.png"
     style="width:480px; margin:0 auto; background-color:white; padding:5px; border-radius:10px" />

---
layout: default
---

# Adding Files to Staging

<div class="center">

-   Add a single file:

    ```
    git add <filename>

    ```

    Example: `git add index.html`

-   Add multiple files:

    ```
    git add .

    ```

    (Adds all untracked files in the current directory and subdirectories)

</div>

---
layout: default
---

# Checking Status

<div class="center">

```
git status

```

-   Shows file status:
    -   Untracked files
    -   Changes not staged
    -   Changes staged
    -   Branch information


</div>

---
layout: default
---

# Committing Changes

<div class="center">

-   Commit: A snapshot of changes.

-   Command:

    ```
    git commit -m "Your commit message"

    ```

-   `-m`: Specifies the commit message.

</div>

---
layout: default
---

# Commit Message Guidelines

<div class="center">

-   Clear and concise.
-   Describe _why_ the change was made, not _what_ was changed.
-   Use imperative mood ("Fix bug..." not "Fixed bug...").
-   Example: `feat: Implement user authentication`


</div>

---
layout: default
---

# Viewing Commit History

<div class="center">

-   Basic log:

    ```
    git log

    ```

-   Shows: Commit hash, author, date, message.

</div>


---
layout: default
---

# Detailed Commit History

<div class="center">

-   One-line log:

    ```
    git log --oneline

    ```

-   Graphical log:

    ```
    git log --graph --oneline --decorate --all

    ```

</div>

---
layout: default
---

# Ignoring Files

<div class="center">

-   `.gitignore` file: Specifies intentionally untracked files to ignore.

-   Example:

    ```
    node_modules/
    .env
    *.log

    ```

</div>

---
layout: default
---

# Creating `.gitignore`

<div class="center">

- Create a file named `.gitignore` in the repository's root directory.
- Add patterns for files/directories to ignore.
- Commit the `.gitignore` file itself.

</div>

---
layout: default
---

# Part 3: Working with Branches

<div class="center">

Version control allows you to track changes, seeing who, what, and when for accountability and debugging. It enables collaboration, facilitating teamwork and avoiding overwrites, with VCS merging changes. You can safely explore new features, discarding branches if needed. Rollback to stable versions after errors, and develop features in parallel, integrating changes cleanly through branching and merging.

</div>

---
layout: default
---

# What are Branches?

-   Independent lines of development.
-   Isolate features, bug fixes, experiments.
-   Lightweight and fast to create.

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/advance-master.svg"
style="margin:0 auto; background-color:white; padding:5px; border-radius:10px; width:500px"/>

---
layout: default
---

# Why Use Branches?

<div class="center">

-   Isolate features and bug fixes.
-   Prevent unstable code from affecting the main branch.
-   Enable parallel development.

</div>

---
layout: default
---

# Listing Branches

<div class="center">

```
git branch

```

-   Shows local branches.
-   The current branch is marked with an asterisk (*).

</div>

---
layout: two-cols
---

# Creating a New Branch

```
git branch <branch_name>

```

-   Example:

    ```
    git branch testing

    ```

-   Creates a new branch named "testing".

::right::

<img src="/images/images_head-to-master-without-testing.svg"
     style="margin:0 auto; margin-top:50px; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:300px"/>

<Arrow x1="710" y1="240" x2="710" y2="330" width="3" color="gray"/>

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/head-to-master.svg"
     style="margin:0 auto; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:300px"/>

---
layout: two-cols
---

# Switching Branches

```
git checkout <branch_name>

```

-   Example:

    ```
    git checkout testing

    ```

-   Switches the working directory to the "testing" branch.

::right::

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/head-to-master.svg"
     style="margin:0 auto; margin-top:50px; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:300px"/>

<Arrow x1="710" y1="240" x2="710" y2="330" width="3" color="gray"/>

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/head-to-testing.svg"
     style="margin:0 auto; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:300px"/>

---
layout: two-cols
---

# Creating and Switching

```
git checkout -b <branch_name>

```

-   Shorthand for creating and switching.

-   Example:

    ```
    git checkout -b testing

    ```

::right::

<img src="/images/images_head-to-master-without-testing.svg"
     style="margin:0 auto; margin-top:50px; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:300px"/>

<Arrow x1="710" y1="240" x2="710" y2="330" width="3" color="gray"/>

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/head-to-testing.svg"
     style="margin:0 auto; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:300px"/>

---
layout: default
---

# Making Changes on a Branch

<div class="center">

1.  Switch to the branch (`git checkout feature-x`).
2.  Make changes to files.
3.  Stage changes (`git add .`).
4.  Commit changes (`git commit -m "Implement feature X"`).

</div>

---
layout: default
---

# Switching Back to Main

<div class="center">

```
git checkout main

```

-   Switches back to the main development branch (usually `main` or `master`).

</div>

---
layout: default
---

# Viewing Branch Changes

<div class="center">

-   Use `git log` while on different branches to see their respective commit histories.
-   `git log main..feature-x` to see commits unique to feature-x

</div>

---
layout: two-cols
---

# Merging Branches

- Integrate changes from one branch into another.
- Command (on the target branch):
  ```
  git merge <branch_to_merge>
  ```
- Example merge (no conflicts):
  ```
  git checkout master
  git merge hotfix
  ```

::right::

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/basic-branching-4.svg"
     style="margin:0 auto; margin-top:50px; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:350px"/>

<Arrow x1="710" y1="220" x2="710" y2="330" width="3" color="gray"/>

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/basic-branching-5.svg"
     style="margin:0 auto; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:350px"/>

---
layout: default
---

# Merge Conflicts

<div class="center">

-   Occur when changes in different branches conflict.
-   Git cannot automatically resolve them.
-   Require manual resolution.

</div>

---
layout: default
---

# Identifying Conflicts

<div class="center">

-   `git status` shows "both modified" files.
-   Conflicted files contain markers:
    -   `<<<<<<< HEAD`
    -   `=======`
    -   `>>>>>>> feature-x`

</div>

---
layout: default
---

# Resolving Conflicts (1)

<div class="center">

1.  Open the conflicted file in an editor.
2.  Manually choose which changes to keep.
3.  Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
4.  Save the file.

</div>

---
layout: default
---

# Resolving Conflicts (2)

<div class="center">

1.  Stage the resolved file:

    ```
    git add <conflicted_file>

    ```
2.  Commit the merge:

    ```
    git commit -m "Merge branch 'feature-x'"

    ```
    (Git usually pre-populates the message)

</div>

---
layout: two-cols
---

# Deleting Branches (Local)

- Delete a merged branch:
  ```
  git branch -d <branch_name>
  ```
- Force delete (even if not merged):
  ```
  git branch -D <branch_name>
  ```
- Example of merged branch deletion:
  ```
  git checkout master
  git branch -d hotfix
  ```

::right::

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/basic-branching-5.svg"
     style="margin:0 auto; margin-top:50px; background-color:white; padding:5px; border-width:3px; border-radius:10px; width:350px"/>

<Arrow x1="710" y1="270" x2="710" y2="360" width="3" color="gray"/>

<img src="/images/images_basic-branching-5-deleted-hotfix.svg"
     style="margin:0 auto; background-color:white; padding:5px; border-width:3px; border-radius:5px; width:350px"/>

---
layout: default
---

# Branching Strategies

<div class="center">

| GitHub Flow                                  | Git Flow                                      |
|----------------------------------------------|-----------------------------------------------|
| **Focus:** Continuous delivery, smaller teams. | **Focus:** Release cycles, larger teams.        |
| **Branches:** `main`, feature branches.       | **Branches:** `main`, `develop`, feature, etc. |
| **Workflow:** Feature PRs -> `main` -> deploy. | Feature -> `develop` -> release -> `main`.     |
| **Best for:** Frequent, agile deployments.   | **Best for:** Scheduled, structured releases. |

</div>

---
layout: default
---

# Keeping Main Updated

<div class="center">

- **Keep main synchronized:** Use git fetch origin main to download remote changes.
- **Merge or Pull:** Integrate changes with git merge origin main (creates a merge commit) or the combined git pull origin main.
- **Alternative: Rebase:** For a linear history, use git fetch origin main then git rebase origin main on your local main.

Better to have linear history to allow to keep track of changes in easy way

</div>

---
layout: default
---

# Part 4: Working with Remote Repositories

<div class="center">

A complete log of changes provides a detailed history of every modification. You can understand project evolution by seeing how the project has grown. Version control offers accountability and traceability, tracking who made each change.

</div>

---
layout: default
---

# What are Remote Repositories?

- Centralized repositories hosted on platforms like GitHub, GitLab, or Bitbucket.
- Enable collaboration and backups.

---
layout: two-cols
---

# Adding a Remote

```
git remote add <remote_name> <remote_url>

```

- `<remote_name>`: Name for the remote.
  - The most common name for the main remote is `origin`.
- `<remote_url>`: URL of the remote repository.
- Example of adding an extra remote:
  ```
  git remote add teamone git://git.team1.ourcompany.com
  ```

::right::

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/remote-branches-4.svg"
     style="margin:0 auto; margin-top:80px; background-color:white; padding:5px; border-radius:5px; width:430px"/>

---
layout: default
---

# Viewing Remotes

<div class="center">

```
git remote -v

```
-   Shows remote names and URLs (fetch and push).

```bash
panicking@panicking:~/work/bsh/symana/linux$ git remote -v
mainline	https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git (fetch)
mainline	https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git (push)
origin	https://scr.bsh-sdd.com/scm/symana/naos_kernel.git (fetch)
origin	https://scr.bsh-sdd.com/scm/symana/naos_kernel.git (push)
texas	git://git.ti.com/ti-linux-kernel/ti-linux-kernel.git (fetch)
texas	git://git.ti.com/ti-linux-kernel/ti-linux-kernel.git (push)
panicking@panicking:~/work/bsh/symana/linux$
```

</div>


---
layout: default
---


# Pushing to a Remote

<div class="center">

```
git push <remote_name> <branch_name>

```

-   Sends local commits to the remote.

-   Example: `git push origin main`

</div>

---
layout: default
---

# First Push and Tracking

<div class="center">

```
git push -u origin main

```

-   `-u`: Sets up tracking, so future `git push` commands can be simpler (`git push`).

</div>

---
layout: two-cols
---


# Fetching Changes

```
git fetch <remote_name>

```

-   Downloads commits and branches from the remote.
-   Does _not_ merge changes.
- Example:
  ```
  git fetch origin
  ```

::right::

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/remote-branches-3.svg"
     style="margin:0 auto; margin-top:80px; background-color:white; padding:5px; border-radius:5px; width:430px"/>

---
layout: default
---


# Pulling Changes

<div class="center">


```
git pull <remote_name> <branch_name>

```

-   Fetches and merges changes from the remote.

-   Shorthand (if tracking is set up): `git pull`

</div>


---
layout: two-cols
---


# Cloning a Repository

```
git clone <remote_url>

```

- Creates a local copy of a remote repository.
- Example:
  ```
  git clone https://github.com/user/repo.git
  ```

::right::

<img src="https://raw.githubusercontent.com/progit/progit2/55081eaf0bfb4b0f9bab287c0dd035bf604e43bc/images/remote-branches-1.svg"
     style="margin:0 auto; margin-top:80px; background-color:white; padding:5px; border-radius:5px; width:430px"/>

---
layout: default
---


# Basic Collaboration Workflow

<div class="center">

1.  `git clone` the repository.
2.  `git checkout -b <branch>` for your changes.
3.  Make and `git commit` changes.
4.  `git push origin <branch>`
5.  Create a Pull Request (on GitHub/GitLab/Bitbucket).

</div>


---
layout: default
---


# Pull Requests

<div class="center">

-   Mechanism for proposing changes.
-   Facilitates code review and discussion.
-   Essential for collaborative development.

</div>

---
layout: default
---


# Keeping Local Synced

<div class="center">

-   Use `git pull` regularly to get the latest changes from the remote.

</div>

---
layout: default
---

# Dealing with Pull Conflicts

<div class="center">

-   Similar to merge conflicts.
-   Resolve manually, `git add`, `git commit`.

</div>

---
layout: default
---


# Rebasing (Introduction)

<div class="center">

-   Alternative to merging.
-   Moves a branch's base to another branch.
-   Command: `git rebase <branch_to_rebase_onto>`
-   Caution: Avoid rebasing public history!

</div>

---
layout: default
---


# Comparing Branches

<div class="center">

-   `git log <remote>/<branch>..<local_branch>`

</div>

---
layout: default
---


# Deleting Remote Branches

<div class="center">

```
git push <remote_name> --delete <branch_name>

```

</div>


---
layout: default
---


# Troubleshooting Remote Issues

<div class="center">

-   Authentication errors (SSH keys, passwords).
-   "Already up to date" despite remote changes (check your local branch).

</div>


---
layout: default
---


# Part 5: Undoing Changes

<div class="center">

VCS allows multiple developers to work on the same project simultaneously. It manages contributions efficiently, ensuring smooth integration, and provides tools to resolve conflicts systematically.

</div>

---
layout: default
---


# Undoing Changes

<div class="center">

-   Git provides tools to undo mistakes at different stages.
-   Understand the commands and their consequences.

</div>


---
layout: default
---


# Unstaged Changes

<div class="center">

-   Discard changes in the working directory:

    ```
    git restore <filename>

    ```
-   Discard all unstaged changes

    ```
    git restore .

    ```

</div>


---
layout: default
---


# Unstaging Changes

<div class="center">

-   Remove a file from the staging area:

    ```
    git restore --staged <filename>

    ```

</div>

---
layout: default
---


# Undoing the Last Commit (Local)

<div class="center">

-   Keep changes in staging:

    ```
    git reset --soft HEAD^

    ```
-   Keep changes in working directory:

    ```
    git reset --mixed HEAD^

    ```
-   Discard changes:

    ```
    git reset --hard HEAD^

    ```
    (Use with CAUTION!)

</div>

---
layout: default
---


# Understanding HEAD

<div class="center">

-   `HEAD`: Pointer to the current commit.
-   `HEAD^`: Parent of the current commit.
-   `HEAD~n`: Nth ancestor commit.

</div>

---
layout: default
---


# Going Back to a Commit

<div class="center">

```
git reset --hard <commit_hash>

```
-   Moves the branch pointer to the specified commit and discards subsequent changes.
-   Use with EXTREME CAUTION! Data loss is possible.

</div>


---
layout: default
---


# Undoing a Pushed Commit

<div class="center">

```
git revert <commit_hash>

```

-   Creates a _new_ commit that undoes the changes of the specified commit.
-   Safer for shared repositories than `reset --hard`.

</div>


---
layout: default
---


# Cleaning Untracked Files

<div class="center">

- Dry run:

    ```
    git clean -n

    ```
- Force removal:

    ```
    git clean -f

    ```
- Remove directories:

    ```
    git clean -fd

    ```
- Remove even untracked files:
    ```
    git clean -fdx
    ```

</div>

---
layout: default
---


# Recovering Deleted Commits

<div class="center">

```
git reflog

```

-   Shows a history of where `HEAD` has been.
-   Use `git reset --hard <reflog_entry>` to recover a lost commit.

</div>

---
layout: default
---


# Best Practices for Undoing

<div class="center">

**git reset** can be used to restore the git to a different point.

-   git reset allow you to move to a specific \<sha256\> or tag
-   Be careful with `--hard`. Hard force the tree to go to that specific commit
-   Prefer `git revert` for public commits.

Public or official repositories should never receive a reset hard that destroy the history.

</div>

---
layout: default
---


# Part 6: Advanced Topics (Briefly)

<div class="center">

New features or bug fixes can be developed in separate branches, enabling safe experimentation without affecting the main codebase. If things go wrong, you can quickly undo changes and revert easily.

</div>

---
layout: default
---


# Stashing Changes

<div class="center">

- **Temporarily save uncommitted changes:** Stashing takes a snapshot of your modified and staged files, allowing you to switch branches or perform other Git operations without committing incomplete work. It cleans your working directory.

- **git stash:** Saves your current uncommitted changes to a stack for later use. Optionally add a message with git stash save "message".

- **stash list:** Displays a list of all your saved stashes, showing their index and any associated messages, helping you track your temporary saves.

- **git stash apply:** Reapplies a specific stash (defaulting to the latest) to your working directory and staging area. The stash remains in the list.

- **git stash drop:** Permanently removes a specific stash from the stash list. Use with caution as this action is generally irreversible.

</div>

---
layout: default
---


# Tagging Releases

<div class="center">

Mark specific points in history (e.g., v1.0.0): Tags create persistent snapshots, like version markers, making it easy to reference important releases or milestones in your project's history.

Commands:

- **git tag -a <tag_name> -m "Release notes":** Creates an annotated tag with a message, storing author and date. Essential for releases.
- **git tag <tag_name>:** Create a standard tag that does not include any new commit.
- **git tag:** Lists all existing tags in your repository.

</div>

---
layout: default
---


# Ignoring Changes in Tracked Files

<div class="center">

```
git update-index --assume-unchanged <filename>

```
-   Tells Git to ignore changes to a tracked file.
-   Use with caution.

</div>


---
layout: default
---


# Git Aliases

<div class="center">

-   Create shortcuts for commands.
-   Example:
    ```
    git config --global alias.co checkout

    ```
    Now you can use `git co <branch>`

</div>

---
layout: default
---


# Further Learning

<div class="center">

-   Git Documentation: [https://git-scm.com/doc](https://git-scm.com/doc "null")
-   Online tutorials and courses (e.g., Coursera, Udemy, freeCodeCamp).
-   Community forums (e.g., Stack Overflow).

</div>

# Part 7: Conclusion and Q&A

---
layout: default
---

# Summary

<div class="center">

-   Git is essential for version control.
-   Key commands: `init`, `add`, `commit`, `branch`, `checkout`, `merge`, `clone`, `push`, `pull`, `status`, `log`, `restore`, `reset`, `revert`.

</div>
