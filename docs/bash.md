---
hide:
  - navigation
---

# Bash
## General
Use ↑ and ↓ arrows to naviage to the past bash commands

## Navigating Directories
Creating, navigating and deleting directories.

| Command                        | Description                                                          |
| ------------------------------ | -------------------------------------------------------------------- |
| pwd                            | Print Working Directory (Current Directory)                          |
| ls                             | List all files and folders in current directory                      |
| cd MyFolder                    | Navigate to "MyFolder". Tip: Use tab to autocomplete the folder name |
| cd MyFolder1\SubFolder1        | Possible to navigate multiple levels                                 |
| cd D:                          | Navigate to D drive                                                  |
| cd ..                          | Move back one directory level                                        |
| cd ~                           | Go to Home directory                                                 |
| mkdir MyFolder                 | Makes/Creates a folder called "NewFolder"                            |
| mkdir -p MyFolder1/SubFolder1/ | Makes/creates the directories and subdirectories required            |
| rm -rf MyFolder                | Use -rf flag in rm command to delete folder recursively              |

## Create and Delete Files
Creating, viewing and deleting files.

| Command          | Description                                               |
| ---------------- | --------------------------------------------------------- |
| touch MyNote.txt | Creates a file called MyNote.txt in the current folder    |
| start MyNote.txt | "start" is for Windows. For other OS, try open MyNote.txt |
| rm MyNote.txt    | To delete/remove files                                    |
| rm *             | Removes all files in current folder                       |
| cat filename.txt | To view file contents directly in bash                    |

## Cheat Sheet
1. [Linux Cheat Sheet](https://github.com/sudheerj/Linux-cheat-sheet#file-and-directory-commands)
2. [Red Hat Linux Cheat Sheet](https://developers.redhat.com/cheat-sheets/linux-commands-cheat-sheet-old)
3. [Learn Enough Command Line to Be Dangerous](https://www.learnenough.com/command-line-tutorial)