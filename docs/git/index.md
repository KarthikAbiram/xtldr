---
hide:
  - navigation
---

# Git
Git is a distributed version control system that are used for tracking changes in files and sharing those with team members. 

It is like a time machine for your computer files. It keeps track of every change you make, allowing you to go back to any point in time. It's great for teamwork, ensuring everyone works on the same version without stepping on each other's toes.

## 🛠️ Setup
For installing and setup, please refer to [xTLDR Git Setup](\git\setup)

## 🖥️ Git Commands

| Command            | Description                                      |
| ------------------ | ------------------------------------------------ |
| git --version      | Get version of git installed in the system       |
| git help [command] | Get help for the git command. Eg: git help clone |

### ➡️ Repository Commands

| Command         | Description                                          |
| --------------- | ---------------------------------------------------- |
| git init        | Initialize an existing directory as a repository     |
| git clone [url] | Clone a remote repository to a local system          |
| git pull        | Fetches changes from remote and merges remote branch |
| git push        | Push local changes to remote                         |

### ➡️ Make Changes and Commit                                                                      
| Command                        | Description                                                                                   |
| ------------------------------ | --------------------------------------------------------------------------------------------- |
| git add [file]                 | Adds a file to staging from where you can commit                                              |
| git add .                      | Add all modified files to staging                                                             |
| git reset [file]               | Unstage a file from staging. Changes will be retained in working directory                    |
| git restore .                  | Discard changes in modified files (excludes those in staging)                                 |
| git clean -d --dry-run         | Dry run. Show list of files that would be removed with clean. -d recurses through directories |
| git clean -df                  | Force remove untracked files from repository, including subdirectories                        |
| git commit -m "commit message" | Makes a commit from the changes in staging                                                    |

### ➡️ Branching and Merging                                                                 
| Command                    | Description                                                        |
| -------------------------- | ------------------------------------------------------------------ |
| git branch                 | List all branches. * denotes the active branch                     |
| git branch [branch-name]   | Create a branch with the provided name                             |
| git checkout [branch-name] | Switch to a different branch. Use -b to create and checkout branch |
| git merge [branch-name]    | Merges the provided branch history into the active branch          |

### ➡️ Status
| Command                                         | Description                                          |
| ----------------------------------------------- | ---------------------------------------------------- |
| git status                                      | Displays the active branch and list of local changes |
| git log --oneline --graph --decorate [-n count] | Displays last n commits of the active branch         |

## 📑 Cheatsheets
- [Git Cheatsheet by Github](https://education.github.com/git-cheat-sheet-education.pdf)
- [Git Cheatsheet by Gitlab](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)
- [Git Cheatsheet by Freecodecamp](https://www.freecodecamp.org/news/git-cheat-sheet/)

## 🛤️Typical Flow
Typical steps to contribute to an open source repository:

1. Create a fork of the repo under your account
2. Clone the above fork in your PC
```
git clone [url]
```
3. Create and checkout a new branch
```
git branch [your-new-branch-name]
git checkout [your-new-branch-name]
```
4. Make changes and commit with your signature
```
git commit -s -m [your commit message]
```
5. Push branch to your online repo
```
git push -u origin [your-new-branch-name]
```
6. Create a pull request with your new branch in the open source repository.
 
## 🧙‍♂️ Advanced

### ➡️ Binary Merge Conflicts
If you don't have options to resolve merge conflicts for binary files, you would want to choose to go with the version in one of the branches.

To go with "your" version (the version in active branch):
```bash
git checkout --ours [file-name]
git add [file-name]
```

To go with "their" version (the branch which you are merging changes from, to the active branch):
```bash
git checkout --theirs [file-name]
git add [file-name]
```
For usage with all files, use `.` instead of file-name.

To better understand ours vs theirs, refer to [git ours vs theirs](https://nitaym.github.io/ourstheirs/)

### ➡️ Partial Merge
If you want to merge selective files from one branch into another, you can use the command, which will perform the merge, add items to staging but not make the commit. You can then reset the changes for files you don't want and then make the commit.

```bash
git merge [branch-name] --no-commit --no-ff
# Now all changes from the branch are in staging, but not committed yet
# Use git reset to discard files you don't want in the merge
git reset [file-name-1]
git reset [file-name-2]
# Once done, make the commit
git commit
```

