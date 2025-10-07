# Upstream Branches Reference

This document provides information about branches in the upstream repository [shicks/jsnsf](https://github.com/shicks/jsnsf) and how to work with them.

## Upstream Branches

### master
- **SHA**: 168e0d8939b70ad0d8b6231bc72ea24193acc4a6
- **Description**: Main development branch
- **URL**: https://github.com/shicks/jsnsf/tree/master

### gh-pages
- **SHA**: c1a0d744b4641ed7ab91107f28971ec7dba4fa92
- **Description**: GitHub Pages deployment branch (live demo)
- **URL**: https://github.com/shicks/jsnsf/tree/gh-pages
- **Demo**: https://shicks.github.io/jsnsf/

## Syncing with Upstream

To track and merge changes from the upstream repository:

### Initial Setup

```bash
# Add upstream remote if not already added
git remote add upstream https://github.com/shicks/jsnsf.git

# Fetch all upstream branches
git fetch upstream
```

### Fetching Upstream Branches

```bash
# Fetch all branches from upstream
git fetch upstream

# List all remote branches
git branch -r

# View commits in upstream/master
git log upstream/master

# View commits in upstream/gh-pages
git log upstream/gh-pages
```

### Merging Upstream Changes

```bash
# Merge upstream master into your current branch
git merge upstream/master

# Or rebase your changes on top of upstream
git rebase upstream/master
```

### Checking Out Upstream Branches

```bash
# Create a local branch tracking upstream/master
git checkout -b upstream-master upstream/master

# Create a local branch tracking upstream/gh-pages
git checkout -b upstream-gh-pages upstream/gh-pages
```

### Comparing with Upstream

```bash
# See what commits are in upstream but not in your branch
git log HEAD..upstream/master

# See what commits are in your branch but not in upstream
git log upstream/master..HEAD

# See the diff between your branch and upstream
git diff upstream/master
```

## Working with Forks

If there are other notable forks with improvements:

1. Add them as remotes:
   ```bash
   git remote add fork-name https://github.com/username/jsnsf.git
   git fetch fork-name
   ```

2. View their branches:
   ```bash
   git branch -r | grep fork-name
   ```

3. Cherry-pick specific commits:
   ```bash
   git cherry-pick <commit-sha>
   ```

4. Merge entire branches:
   ```bash
   git merge fork-name/branch-name
   ```

## Keeping This Document Updated

When updating this document with new branch information:

1. Fetch latest from upstream:
   ```bash
   git fetch upstream
   ```

2. List branches with their SHAs:
   ```bash
   git ls-remote upstream
   ```

3. Update this document with new branch information

## Contributing Back to Upstream

If you make improvements that would benefit the upstream project:

1. Fork the upstream repository (shicks/jsnsf) if you haven't already
2. Create a feature branch
3. Push your changes to your fork
4. Open a pull request to the upstream repository

For more information about issues in the upstream repository, see [UPSTREAM_ISSUES.md](UPSTREAM_ISSUES.md).
