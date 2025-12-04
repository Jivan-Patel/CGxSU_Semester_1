
# Detailed Git Notes with Examples

## Unit 1: Introduction to Version Control and Git

### Version Control Systems (VCS)

Version control tracks changes in code over time, enabling collaboration and rollback. Types include Centralized (SVN) and Distributed (Git). Git stores snapshots of entire projects, not just differences.

### Benefits of Git

- **Distributed**: Full repo copy on every machine, works offline.
- **Speed**: Lightning-fast operations even on large repos.
- **Branching**: Cheap branches for features/bugfixes.
- **Data integrity**: SHA-1 checksums prevent corruption.


### Installing Git

**Windows**: Download from git-scm.com, run installer.
**macOS**: `brew install git` or Xcode Command Line Tools.
**Linux (Ubuntu)**: `sudo apt update && sudo apt install git`.

### Configuring Git

```bash
git config --global user.name "John Doe"
git config --global user.email "john@example.com"
git config --global core.editor "nano"
git config --list  # Verify settings
```


### Basic Git Commands with Examples

```bash
# Initialize repo
mkdir myproject && cd myproject
git init

# Create files and check status
echo "Hello" > hello.txt
git status  # Shows untracked files

# Stage and commit
git add hello.txt
git commit -m "Add hello file"

# View history
git log --oneline  # Compact view
```


### Git Workflow Explained

1. **Working Directory**: Files you edit (`hello.txt`).
2. **Staging Area**: `git add` prepares changes.
3. **Repository**: `git commit` saves snapshots.
```
Working Dir → git add → Staging → git commit → Repo (.git/)
```


***

## Unit 2: Working with Repositories

### Creating vs Cloning

```bash
# Create new repo
git init my-repo
cd my-repo
echo "# My Project" > README.md
git add . && git commit -m "Initial commit"

# Clone existing
git clone https://github.com/user/repo.git
cd repo
```


### Commits and Messages

Good messages: "Fix login bug in auth module" (imperative mood, <50 chars).

```bash
git commit -m "Add user authentication

- Implement JWT tokens
- Add login endpoint
- Fix validation errors"
```


### Viewing History

```bash
git log --oneline --graph --all    # Visual branch graph
git log --stat                     # Files changed stats
git log --author="John"            # Filter by author
```


### Branching and Merging Example

```bash
# Create and switch to feature branch
git checkout -b feature-login
echo "login form" > login.html
git add . && git commit -m "Add login form"

# Switch back and merge
git checkout main
git merge feature-login
```

**Merge conflicts example**:

```
<<<<<<< HEAD
function greet() { return "Hello"; }
=======
function greet() { return "Hi there"; }
>>>>>>> feature-branch
```

Edit file, then `git add` and `git commit`.

### Branch Management

```bash
git branch -d feature-login     # Safe delete
git branch -D buggy-branch      # Force delete
git branch -m old-name new-name # Rename
```


***

## Unit 3: Advanced Git Operations

### Git Stash Workflow

```bash
# Emergency save unfinished work
git stash push -m "WIP: navbar design"

# List stashes
git stash list

# Apply latest
git stash pop

# Apply specific
git stash apply stash@{1}
```


### Git Rebase Example

```bash
# Rebase feature onto main (linear history)
git checkout feature
git rebase main

# Interactive rebase (edit last 3 commits)
git rebase -i HEAD~3
# Options: pick, reword, edit, squash, drop
```


### Cherry-pick Specific Commit

```bash
git cherry-pick a1b2c3d  # Apply commit from anywhere
git cherry-pick --no-commit a1b2c3d  # Stage only
```


### Tagging Releases

```bash
git tag v1.0.0 HEAD          # Lightweight tag
git tag -a v1.0.0 -m "Release 1.0"  # Annotated tag
git push origin v1.0.0        # Push tag
```


### Remote Repository Commands

```bash
# Add remote
git remote add origin https://github.com/user/repo.git

# Check remotes
git remote -v

# Sync workflow
git fetch origin          # Download changes
git pull origin main      # Fetch + merge
git push origin feature   # Upload branch
```


### Open Source Contribution

1. Fork repo on GitHub
2. `git clone your-fork`
3. `git checkout -b fix-issue-123`
4. Make changes, push, create PR

***

## Unit 4: Collaborating with GitHub

### GitHub Features

- **Repositories**: Private/public code storage
- **Issues**: Bug tracking, feature requests
- **Pull Requests**: Code review workflow
- **Actions**: CI/CD pipelines
- **Projects**: Kanban boards


### GitHub Workflow Example

```
1. Create Issue: "Add dark mode toggle"
2. Fork → Clone → Create branch: git checkout -b dark-mode
3. Implement feature → git push origin dark-mode
4. Create PR → Team reviews → Merge to main
```


### Pull Request Best Practices

- **Title**: "Add dark mode toggle (\#123)"
- **Description**: What, Why, How tested
- **Checkboxes**:
    - [ ] Tests pass
    - [ ] Docs updated


### Issues and Projects

```markdown
# Issue template
**What**: Navbar doesn't collapse on mobile
**Steps**: Open on phone, tap menu
**Expected**: Menu opens
```

**Projects**: Drag cards between "To Do" → "In Progress" → "Done"

### GitHub Pages and Wikis

- **Pages**: `git push` to `gh-pages` branch → auto-hosted site
- **Wikis**: Markdown docs linked to repo

These comprehensive notes with practical examples cover Git from basics to collaboration workflows for effective version control mastery.

