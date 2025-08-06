# Git API Documentation

<div align="center">
  <img src="https://img.shields.io/badge/Git-API-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git API">
  <h1>Git Commands & Utilities API</h1>
  <p>Complete reference for Git version control and GitHub workflows</p>
</div>

## Overview

The Git API provides a comprehensive collection of Git commands and workflows for version control, collaboration, and repository management. This documentation covers everything from basic Git operations to advanced repository management techniques.

**Sources:**
- [`utils/git/COMANDOSGIT.md`](../utils/git/COMANDOSGIT.md) - Portuguese Git commands reference
- [`utils/git/GITCOMMANDS.md`](../utils/git/GITCOMMANDS.md) - English Git commands reference  
- [`utils/git/ROADMAP_GITHUB.md`](../utils/git/ROADMAP_GITHUB.md) - GitHub learning roadmap
- [`utils/git/ComandosGitBasico.md`](../utils/git/ComandosGitBasico.md) - Basic Git commands
- [`utils/git/dicasgit.md`](../utils/git/dicasgit.md) - Git tips and tricks

**Compatibility:** Git 2.0+ and GitHub integration

## Quick Start

```bash
# Initialize a new repository
git init

# Clone existing repository
git clone https://github.com/user/repo.git

# Basic workflow
git add .
git commit -m "Initial commit"
git push origin main
```

## Command Categories

### 1. Configuration & Setup

#### Initial Git Configuration

```bash
# Set user information globally
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set user information for current repository only
git config --local user.name "Your Name"
git config --local user.email "your.email@example.com"

# Set user information system-wide
git config --system user.name "Your Name"
git config --system user.email "your.email@example.com"
```

#### Configuration Scopes

| Scope | Flag | Description | Priority |
|-------|------|-------------|----------|
| Local | `--local` | Repository-specific | Highest |
| Global | `--global` | User-specific | Medium |
| System | `--system` | System-wide | Lowest |

#### View Configuration

```bash
# View all configuration
git config --list

# View specific configuration
git config user.name
git config user.email

# View configuration with origin
git config --list --show-origin
```

#### Common Configuration Settings

```bash
# Set default editor
git config --global core.editor "code --wait"

# Set default branch name
git config --global init.defaultBranch main

# Enable color output
git config --global color.ui auto

# Set line ending handling (Windows)
git config --global core.autocrlf true

# Set line ending handling (Linux/Mac)
git config --global core.autocrlf input
```

### 2. Repository Operations

#### Creating & Cloning Repositories

```bash
# Initialize new repository
git init

# Initialize with specific branch name
git init --initial-branch=main

# Clone repository
git clone https://github.com/user/repo.git

# Clone specific branch
git clone --branch develop https://github.com/user/repo.git

# Clone to specific directory
git clone https://github.com/user/repo.git my-project

# Clone with depth (shallow clone)
git clone --depth 1 https://github.com/user/repo.git

# Clone submodules
git clone --recursive https://github.com/user/repo.git
```

#### Repository Status & Information

```bash
# Check repository status
git status

# Short status format
git status -s

# View repository information
git remote -v
git branch -a
git log --oneline -10
```

### 3. Remote Repository Management

#### Adding & Managing Remotes

```bash
# List remotes
git remote

# List remotes with URLs
git remote -v

# Add remote
git remote add origin https://github.com/user/repo.git

# Add upstream remote (for forks)
git remote add upstream https://github.com/original/repo.git

# Remove remote
git remote remove origin

# Rename remote
git remote rename origin backup

# Change remote URL
git remote set-url origin https://github.com/user/new-repo.git
```

#### Fetching & Pulling

```bash
# Fetch from all remotes
git fetch --all

# Fetch from specific remote
git fetch origin

# Fetch and prune deleted remote branches
git fetch --prune

# Pull changes (fetch + merge)
git pull origin main

# Pull with rebase
git pull --rebase origin main

# Pull specific branch
git pull origin feature-branch
```

#### Pushing Changes

```bash
# Push to remote branch
git push origin main

# Push and set upstream
git push -u origin feature-branch

# Push all branches
git push --all origin

# Push tags
git push --tags origin

# Force push (use with caution)
git push --force origin main

# Force push with lease (safer)
git push --force-with-lease origin main
```

### 4. Basic Git Workflow

#### Staging & Committing

```bash
# Add files to staging area
git add file.txt
git add *.js
git add .

# Add interactively
git add -i

# Add patch
git add -p

# Remove from staging
git reset HEAD file.txt

# Commit changes
git commit -m "Add new feature"

# Commit with detailed message
git commit -m "feat: add user authentication

- Add login component
- Implement JWT token validation
- Add user session management"

# Amend last commit
git commit --amend

# Amend without changing message
git commit --amend --no-edit
```

#### Viewing Changes

```bash
# View working directory changes
git diff

# View staged changes
git diff --staged

# View changes in specific file
git diff file.txt

# View changes between commits
git diff commit1..commit2

# View changes between branches
git diff main..feature-branch
```

#### Commit History

```bash
# View commit history
git log

# Compact history
git log --oneline

# Graphical history
git log --graph --oneline --all

# History with file changes
git log --stat

# History for specific file
git log --follow file.txt

# History with search
git log --grep="bug fix"

# History by author
git log --author="John Doe"

# History in date range
git log --since="2023-01-01" --until="2023-12-31"
```

### 5. Branching & Merging

#### Branch Operations

```bash
# List branches
git branch

# List all branches (including remote)
git branch -a

# Create new branch
git branch feature-branch

# Create and switch to branch
git checkout -b feature-branch

# Switch to branch
git checkout main

# Switch to branch (Git 2.23+)
git switch main

# Create and switch (Git 2.23+)
git switch -c feature-branch

# Delete branch
git branch -d feature-branch

# Force delete branch
git branch -D feature-branch

# Delete remote branch
git push origin --delete feature-branch

# Rename branch
git branch -m old-name new-name
```

#### Merging

```bash
# Merge branch
git merge feature-branch

# Merge without fast-forward
git merge --no-ff feature-branch

# Merge with squash
git merge --squash feature-branch

# Abort merge
git merge --abort

# Continue merge after resolving conflicts
git merge --continue
```

#### Merge Conflict Resolution

```bash
# View conflicts
git status

# View conflicted files
git diff --name-only --diff-filter=U

# Resolve conflicts manually, then:
git add resolved-file.txt
git commit

# Use merge tool
git mergetool

# Accept version from current branch
git checkout --ours file.txt

# Accept version from incoming branch
git checkout --theirs file.txt
```

### 6. Stashing

#### Basic Stashing

```bash
# Stash current changes
git stash

# Stash with message
git stash push -m "Work in progress on feature X"

# Stash including untracked files
git stash -u

# Stash including ignored files
git stash -a

# List stashes
git stash list

# Apply latest stash
git stash apply

# Apply specific stash
git stash apply stash@{2}

# Pop latest stash (apply and remove)
git stash pop

# Drop stash
git stash drop stash@{1}

# Clear all stashes
git stash clear
```

#### Advanced Stashing

```bash
# Stash specific files
git stash push file1.txt file2.txt

# Create branch from stash
git stash branch feature-branch stash@{1}

# Show stash contents
git stash show -p stash@{0}
```

### 7. Rewriting History

#### Rebasing

```bash
# Rebase current branch onto main
git rebase main

# Interactive rebase
git rebase -i HEAD~3

# Continue rebase after resolving conflicts
git rebase --continue

# Skip current commit during rebase
git rebase --skip

# Abort rebase
git rebase --abort

# Rebase onto specific commit
git rebase --onto main feature~3 feature
```

#### Interactive Rebase Options

```bash
# In interactive rebase editor:
pick abc1234    # Keep commit as is
reword def5678  # Keep commit but edit message
edit ghi9012    # Keep commit but stop to amend
squash jkl3456  # Combine with previous commit
fixup mno7890   # Combine with previous, discard message
drop pqr2345    # Remove commit entirely
```

#### Resetting

```bash
# Soft reset (keep changes staged)
git reset --soft HEAD~1

# Mixed reset (unstage changes)
git reset HEAD~1

# Hard reset (discard changes)
git reset --hard HEAD~1

# Reset to specific commit
git reset --hard abc1234

# Reset specific file
git reset HEAD file.txt
```

### 8. Advanced Operations

#### Cherry-picking

```bash
# Cherry-pick single commit
git cherry-pick abc1234

# Cherry-pick multiple commits
git cherry-pick abc1234 def5678

# Cherry-pick range of commits
git cherry-pick abc1234..def5678

# Cherry-pick without committing
git cherry-pick --no-commit abc1234

# Abort cherry-pick
git cherry-pick --abort

# Continue cherry-pick after resolving conflicts
git cherry-pick --continue
```

#### Tagging

```bash
# List tags
git tag

# Create lightweight tag
git tag v1.0.0

# Create annotated tag
git tag -a v1.0.0 -m "Release version 1.0.0"

# Tag specific commit
git tag v1.0.0 abc1234

# Push tags
git push origin v1.0.0
git push origin --tags

# Delete tag
git tag -d v1.0.0

# Delete remote tag
git push origin --delete v1.0.0
```

#### Submodules

```bash
# Add submodule
git submodule add https://github.com/user/lib.git libs/lib

# Initialize submodules
git submodule init

# Update submodules
git submodule update

# Update all submodules to latest
git submodule update --remote

# Clone with submodules
git clone --recursive https://github.com/user/repo.git

# Update submodules recursively
git submodule update --init --recursive
```

#### Worktrees

```bash
# List worktrees
git worktree list

# Add new worktree
git worktree add ../feature-branch feature-branch

# Add worktree with new branch
git worktree add -b new-feature ../new-feature

# Remove worktree
git worktree remove ../feature-branch

# Prune worktrees
git worktree prune
```

### 9. Repository Maintenance

#### Cleaning

```bash
# Clean untracked files (dry run)
git clean -n

# Clean untracked files
git clean -f

# Clean untracked files and directories
git clean -fd

# Clean ignored files
git clean -fX

# Clean everything
git clean -fx
```

#### Garbage Collection

```bash
# Run garbage collection
git gc

# Aggressive garbage collection
git gc --aggressive

# Prune unreachable objects
git prune

# Prune with expiry
git prune --expire="2 weeks ago"
```

#### Repository Optimization

```bash
# Repack repository
git repack -ad

# Verify repository integrity
git fsck

# Count objects
git count-objects -v

# Estimate repository size
du -sh .git
```

### 10. Debugging & Troubleshooting

#### Finding Issues

```bash
# Binary search for bugs
git bisect start
git bisect bad          # Current commit is bad
git bisect good v1.0    # v1.0 is known good
# Git will check out commits for testing
git bisect good         # If commit is good
git bisect bad          # If commit is bad
git bisect reset        # When done

# Find when line was changed
git blame file.txt

# Show what changed in commit
git show abc1234

# Find commits that changed specific string
git log -S "function_name" --source --all
```

#### Reflog

```bash
# View reference log
git reflog

# View reflog for specific branch
git reflog feature-branch

# Recover lost commits
git reflog
git checkout abc1234
git branch recovered-branch
```

## GitHub Integration

### 1. Authentication

#### SSH Key Setup

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your.email@example.com"

# Add to SSH agent
ssh-add ~/.ssh/id_ed25519

# Test connection
ssh -T git@github.com
```

#### Personal Access Tokens

```bash
# Use with HTTPS
git remote set-url origin https://token@github.com/user/repo.git

# Store credentials
git config --global credential.helper store
```

### 2. GitHub-Specific Workflows

#### Fork & Pull Request Workflow

```bash
# 1. Fork repository on GitHub
# 2. Clone your fork
git clone https://github.com/yourusername/repo.git

# 3. Add upstream remote
git remote add upstream https://github.com/original/repo.git

# 4. Create feature branch
git checkout -b feature-branch

# 5. Make changes and commit
git add .
git commit -m "Add new feature"

# 6. Push to your fork
git push origin feature-branch

# 7. Create pull request on GitHub
# 8. Keep fork updated
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

#### GitHub CLI Integration

```bash
# Install GitHub CLI: gh

# Authenticate
gh auth login

# Create repository
gh repo create my-project --public

# Clone repository
gh repo clone user/repo

# Create pull request
gh pr create --title "Add feature" --body "Description"

# List pull requests
gh pr list

# Check out pull request
gh pr checkout 123

# Merge pull request
gh pr merge 123 --squash
```

## Best Practices

### 1. Commit Message Conventions

#### Conventional Commits

```bash
# Format: type(scope): description
feat(auth): add user login functionality
fix(api): resolve null pointer exception
docs(readme): update installation instructions
style(css): fix indentation
refactor(utils): simplify validation function
test(auth): add login component tests
chore(deps): update dependencies
```

#### Commit Message Guidelines

- Use present tense ("add feature" not "added feature")
- Use imperative mood ("move cursor to..." not "moves cursor to...")
- Limit first line to 50 characters
- Reference issues and pull requests when applicable
- Explain what and why, not how

### 2. Branching Strategies

#### Git Flow

```bash
# Main branches
main        # Production-ready code
develop     # Integration branch

# Supporting branches
feature/*   # New features
release/*   # Prepare releases
hotfix/*    # Critical fixes

# Example workflow
git checkout develop
git checkout -b feature/user-auth
# ... make changes ...
git checkout develop
git merge feature/user-auth
```

#### GitHub Flow

```bash
# Simple workflow
main        # Always deployable

# Workflow
git checkout main
git pull origin main
git checkout -b feature-branch
# ... make changes ...
git push origin feature-branch
# Create pull request
# Merge to main after review
```

### 3. Collaboration Guidelines

#### Before Starting Work

```bash
# Always start with latest changes
git checkout main
git pull origin main
git checkout -b feature-branch
```

#### Regular Synchronization

```bash
# Keep feature branch updated
git checkout feature-branch
git rebase main

# Or merge approach
git checkout feature-branch
git merge main
```

#### Code Review Process

1. Create focused, single-purpose pull requests
2. Write descriptive pull request descriptions
3. Respond to feedback constructively
4. Update pull requests based on reviews
5. Squash commits if requested

### 4. Security Best Practices

#### Credential Management

```bash
# Never commit credentials
echo "*.env" >> .gitignore
echo "config/secrets.yml" >> .gitignore

# Use environment variables
export DATABASE_URL="postgres://user:pass@localhost/db"

# Use Git credential helpers
git config --global credential.helper cache
```

#### Signing Commits

```bash
# Generate GPG key
gpg --gen-key

# Configure Git to use GPG key
git config --global user.signingkey YOUR_KEY_ID
git config --global commit.gpgsign true

# Sign commits
git commit -S -m "Signed commit"
```

## Troubleshooting

### Common Issues

#### 1. Merge Conflicts

**Problem:** Conflicting changes in same file

**Solution:**
```bash
# View conflicted files
git status

# Edit files to resolve conflicts
# Look for conflict markers: <<<<<<<, =======, >>>>>>>

# After resolving
git add resolved-file.txt
git commit
```

#### 2. Accidental Commits

**Problem:** Committed wrong files or message

**Solution:**
```bash
# Undo last commit, keep changes
git reset --soft HEAD~1

# Undo last commit, discard changes
git reset --hard HEAD~1

# Amend commit message
git commit --amend -m "Corrected message"
```

#### 3. Lost Changes

**Problem:** Changes disappeared after reset

**Solution:**
```bash
# Check reflog
git reflog

# Recover from reflog
git checkout abc1234
git branch recovery-branch
```

#### 4. Large File Issues

**Problem:** Repository is too large

**Solution:**
```bash
# Remove large files from history
git filter-branch --tree-filter 'rm -f large-file.zip' HEAD

# Use Git LFS for large files
git lfs track "*.zip"
git add .gitattributes
```

### Debug Commands

```bash
# Verbose output
git -c core.verbose=true command

# Debug mode
GIT_CURL_VERBOSE=1 git clone https://github.com/user/repo.git

# Trace commands
GIT_TRACE=1 git status

# Check repository health
git fsck --full
```

## Advanced Workflows

### 1. Release Management

```bash
# Create release branch
git checkout -b release/v1.2.0 develop

# Bump version, update changelog
# ... make version changes ...

# Merge to main
git checkout main
git merge release/v1.2.0

# Tag release
git tag -a v1.2.0 -m "Release version 1.2.0"

# Merge back to develop
git checkout develop
git merge release/v1.2.0

# Clean up
git branch -d release/v1.2.0
```

### 2. Hotfix Workflow

```bash
# Create hotfix from main
git checkout -b hotfix/critical-bug main

# Fix the issue
# ... make changes ...

# Merge to main
git checkout main
git merge hotfix/critical-bug
git tag -a v1.2.1 -m "Hotfix version 1.2.1"

# Merge to develop
git checkout develop
git merge hotfix/critical-bug

# Clean up
git branch -d hotfix/critical-bug
```

### 3. Continuous Integration

```bash
# Pre-commit hooks
# .git/hooks/pre-commit
#!/bin/sh
npm test
if [ $? -ne 0 ]; then
    echo "Tests failed, commit aborted"
    exit 1
fi

# Pre-push hooks
# .git/hooks/pre-push
#!/bin/sh
npm run lint
npm test
```

## Related Resources

- [Pro Git Book](https://git-scm.com/book)
- [GitHub Docs](https://docs.github.com/)
- [Git Reference](https://git-scm.com/docs)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)
- [GitHub Learning Lab](https://lab.github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

## Contributing

Help improve the Git API documentation:

1. Test commands and workflows
2. Add new use cases and examples
3. Update with latest Git features
4. Improve troubleshooting guides
5. Share best practices and tips

---

<div align="center">
  <p>Maintained by the DIO Community</p>
  <p><a href="../API_DOCUMENTATION.md">← Back to API Documentation</a></p>
</div>