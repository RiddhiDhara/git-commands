# Git Commands Reference Guide

A comprehensive guide to Git commands for version control.

## Table of Contents
- [Getting Started](#getting-started)
- [Basic Commands](#basic-commands)
- [Branching and Merging](#branching-and-merging)
- [Remote Repository Operations](#remote-repository-operations)
- [Inspection and Comparison](#inspection-and-comparison)
- [Configuration](#configuration)
- [Advanced Operations](#advanced-operations)
- [Git Workflows](#git-workflows)

## Getting Started

### Repository Initialization
```bash
# Create a new local repository
git init

# Clone an existing repository
git clone <repository-url>
git clone <repository-url> <directory-name>
```

## Basic Commands

### Adding Files
```bash
# Add a specific file
git add <filename>

# Add all files
git add .

# Add all files with a specific extension
git add *.<extension>

# Add files interactively
git add -p
```

### Committing Changes
```bash
# Commit with message
git commit -m "commit message"

# Add and commit tracked files
git commit -am "commit message"

# Amend last commit
git commit --amend
```

### Status and Information
```bash
# Show repository status
git status

# Show commit history
git log

# Show commit history with changes
git log -p

# Show compact history
git log --oneline

# Show branching history
git log --graph --oneline --decorate
```

## Branching and Merging

### Branch Management
```bash
# List branches
git branch

# Create new branch
git branch <branch-name>

# Switch to branch
git checkout <branch-name>

# Create and switch to new branch
git checkout -b <branch-name>

# Delete branch
git branch -d <branch-name>

# Force delete branch
git branch -D <branch-name>
```

### Merging
```bash
# Merge branch into current branch
git merge <branch-name>

# Abort merge
git merge --abort

# Continue merge after resolving conflicts
git merge --continue
```

## Remote Repository Operations

### Managing Remotes
```bash
# Show remote repositories
git remote -v

# Add remote repository
git remote add <name> <url>

# Remove remote
git remote remove <name>

# Rename remote
git remote rename <old-name> <new-name>
```

### Syncing with Remote
```bash
# Fetch changes from remote
git fetch <remote>

# Pull changes from remote
git pull <remote> <branch>

# Push changes to remote
git push <remote> <branch>

# Push new branch to remote
git push -u <remote> <branch>
```

## Inspection and Comparison

### Viewing Changes
```bash
# Show unstaged changes
git diff

# Show staged changes
git diff --staged

# Show changes between branches
git diff <branch1> <branch2>

# Show changes in specific file
git diff <filename>
```

### History and Blame
```bash
# Show file history
git log <filename>

# Show who changed what and when
git blame <filename>

# Show commit details
git show <commit-hash>
```

## Configuration

### User Configuration
```bash
# Set global user name
git config --global user.name "Your Name"

# Set global email
git config --global user.email "your.email@example.com"

# Set repository-specific user name
git config user.name "Your Name"

# Set repository-specific email
git config user.email "your.email@example.com"
```

### System Configuration
```bash
# Set default editor
git config --global core.editor "editor-name"

# Set default branch name
git config --global init.defaultBranch main

# List all configurations
git config --list
```

## Advanced Operations

### Stashing
```bash
# Stash changes
git stash

# List stashes
git stash list

# Apply stash
git stash apply

# Pop stash
git stash pop

# Drop stash
git stash drop
```

### Rebasing
```bash
# Rebase current branch
git rebase <branch>

# Interactive rebase
git rebase -i <commit-hash>

# Continue rebase after resolving conflicts
git rebase --continue

# Abort rebase
git rebase --abort
```

### Reset and Restore
```bash
# Soft reset (keep changes staged)
git reset --soft <commit>

# Mixed reset (keep changes unstaged)
git reset --mixed <commit>

# Hard reset (discard changes)
git reset --hard <commit>

# Restore file to last commit
git restore <filename>

# Restore staged file
git restore --staged <filename>
```

## Git Workflows

### Feature Branch Workflow
1. Create feature branch
```bash
git checkout -b feature/new-feature
```

2. Make changes and commit
```bash
git add .
git commit -m "Add new feature"
```

3. Push feature branch
```bash
git push -u origin feature/new-feature
```

4. Create pull request (through web interface)

5. After approval, merge and cleanup
```bash
git checkout main
git pull
git branch -d feature/new-feature
```

### Hotfix Workflow
1. Create hotfix branch
```bash
git checkout -b hotfix/bug-fix main
```

2. Fix bug and commit
```bash
git add .
git commit -m "Fix critical bug"
```

3. Merge to main and production
```bash
git checkout main
git merge hotfix/bug-fix
git push origin main

git checkout production
git merge hotfix/bug-fix
git push origin production
```

4. Cleanup
```bash
git branch -d hotfix/bug-fix
```

## Best Practices

1. Commit messages should be clear and descriptive
2. Pull before pushing to avoid conflicts
3. Use feature branches for new development
4. Review changes before committing
5. Keep commits atomic and focused
6. Regularly sync with remote repository
7. Document significant changes

## Need Help?

- Get command help: `git help <command>`
- Get quick command reference: `git <command> -h`
- View manual page: `man git-<command>`
