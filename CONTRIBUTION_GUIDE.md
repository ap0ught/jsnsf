# Contribution Guide

This document provides an overview of how to contribute to this fork of JsNsf and how to work with the upstream repository.

## Documentation Overview

This repository includes comprehensive documentation:

- **[README.md](README.md)**: Main project documentation with features, quick start guide, and project structure
- **[README.dev](README.dev)**: Detailed development guide covering architecture, build system, coding standards, and troubleshooting
- **[UPSTREAM_ISSUES.md](UPSTREAM_ISSUES.md)**: Tracking of open issues from the upstream repository (shicks/jsnsf)
- **[UPSTREAM_BRANCHES.md](UPSTREAM_BRANCHES.md)**: Information about upstream branches and how to sync with them

## Upstream Relationship

This is a fork of [shicks/jsnsf](https://github.com/shicks/jsnsf). We track upstream issues and maintain compatibility while adding our own improvements.

### Upstream Issues Being Tracked

1. **Issue #1**: Core CPU emulation accuracy affecting NSF playback
2. **Issue #2**: Runtime error when loading certain NSF files

See [UPSTREAM_ISSUES.md](UPSTREAM_ISSUES.md) for full details.

### Upstream Branches Being Tracked

- **master**: Main development branch
- **gh-pages**: GitHub Pages deployment with live demo

See [UPSTREAM_BRANCHES.md](UPSTREAM_BRANCHES.md) for sync instructions.

## CI/CD Workflows

This repository includes the following GitHub Actions workflows:

### Build Workflow (`.github/workflows/build.yml`)
- Runs on push and pull requests
- Sets up Java, Perl, and Google Closure Compiler
- Builds the project and uploads artifacts
- Validates that the build completes successfully

### GitHub Pages Deployment (`.github/workflows/pages.yml`)
- Automatically deploys to GitHub Pages on push to master
- Builds the project before deployment
- Makes the NSF player accessible via web

### CodeQL Analysis (`.github/workflows/codeql.yml`)
- Security scanning and code quality analysis
- Runs on schedule and pull requests
- Helps identify potential security issues

## How to Contribute

### For Issues Related to Upstream

If you're working on issues that exist in the upstream repository:

1. Check [UPSTREAM_ISSUES.md](UPSTREAM_ISSUES.md) to see if it's tracked
2. Work on a fix in this fork
3. Test thoroughly
4. Consider contributing the fix back to upstream via pull request
5. Document your changes and reference the upstream issue

### For Fork-Specific Improvements

1. Create a feature branch from master
2. Follow the coding standards in [README.dev](README.dev)
3. Test your changes thoroughly
4. Create a pull request with a clear description
5. Ensure CI/CD workflows pass

### Development Setup

See [README.dev](README.dev) for complete development setup instructions including:
- Prerequisites
- Build system
- Coding standards
- Testing procedures
- Debugging tips

## Quick Links

- **Upstream Repository**: https://github.com/shicks/jsnsf
- **Upstream Issue #1**: https://github.com/shicks/jsnsf/issues/1
- **Upstream Issue #2**: https://github.com/shicks/jsnsf/issues/2
- **Upstream Live Demo**: https://shicks.github.io/jsnsf/

## Keeping Documentation Updated

When making significant changes:

1. Update relevant documentation files
2. Keep [UPSTREAM_ISSUES.md](UPSTREAM_ISSUES.md) current if upstream issues change
3. Update [UPSTREAM_BRANCHES.md](UPSTREAM_BRANCHES.md) if new branches are added
4. Maintain the coding standards documented in [README.dev](README.dev)

## Questions?

For development questions, see [README.dev](README.dev).
For general project information, see [README.md](README.md).
For upstream sync questions, see [UPSTREAM_BRANCHES.md](UPSTREAM_BRANCHES.md).
