# Documentation Index

This repository contains comprehensive documentation for working with GitHub, creating pull requests, and handling permission issues.

## Quick Start

New to the repository? Start here:
1. 📖 Read the [README](README.md) for an overview
2. ✅ Follow the exercise steps to learn Markdown
3. 🤝 Review [CONTRIBUTING.md](CONTRIBUTING.md) if you want to contribute

## Documentation Structure

```
communicate-using-markdown/
├── README.md                           # Main repository overview
├── CONTRIBUTING.md                     # How to contribute
├── MANUAL_PR_GUIDE.md                 # Step-by-step PR creation
├── PERMISSION_QUICK_REFERENCE.md      # Quick fixes for common errors
└── DOCUMENTATION_INDEX.md             # This file
```

## Document Purposes

### [README.md](README.md)
**Purpose**: Main entry point for the repository
**Audience**: Everyone
**Contents**:
- What this repository is about
- How to start the exercise
- Links to contribution guides

### [CONTRIBUTING.md](CONTRIBUTING.md)
**Purpose**: Guidelines for contributing to the repository
**Audience**: Contributors and collaborators
**Contents**:
- Code of conduct
- How to report issues
- Handling permission issues
- Pull request process
- Style guidelines
- Workflow modification guidelines

### [MANUAL_PR_GUIDE.md](MANUAL_PR_GUIDE.md)
**Purpose**: Detailed step-by-step guide for creating pull requests manually
**Audience**: Users without write access or experiencing automation issues
**Contents**:
- When to use this guide
- Prerequisites
- Step-by-step instructions for:
  - Forking repositories
  - Creating branches
  - Making changes
  - Committing and pushing
  - Creating pull requests on GitHub
- Best practices
- Troubleshooting common issues

### [PERMISSION_QUICK_REFERENCE.md](PERMISSION_QUICK_REFERENCE.md)
**Purpose**: Quick reference for resolving permission errors
**Audience**: Users experiencing access or authentication issues
**Contents**:
- Common error messages and solutions
- Quick commands
- Workflow decision tree
- Authentication method comparison
- Emergency fixes

## When to Use Each Document

### I want to...

#### Learn about this repository
→ Read [README.md](README.md)

#### Contribute to this project
→ Start with [CONTRIBUTING.md](CONTRIBUTING.md)

#### Create a pull request but don't have write access
→ Follow [MANUAL_PR_GUIDE.md](MANUAL_PR_GUIDE.md)

#### Fix a permission error quickly
→ Check [PERMISSION_QUICK_REFERENCE.md](PERMISSION_QUICK_REFERENCE.md)

#### Understand all available documentation
→ You're already here! (DOCUMENTATION_INDEX.md)

## Common Workflows

### Contributing Without Write Access

1. Read [CONTRIBUTING.md](CONTRIBUTING.md) - Permission Issues section
2. Follow [MANUAL_PR_GUIDE.md](MANUAL_PR_GUIDE.md) for detailed steps
3. Use [PERMISSION_QUICK_REFERENCE.md](PERMISSION_QUICK_REFERENCE.md) if you encounter errors

### Contributing With Write Access

1. Read [CONTRIBUTING.md](CONTRIBUTING.md) - Pull Request Process section
2. Create a branch, make changes, and push directly
3. Create PR following the guidelines

### Troubleshooting

1. Check [PERMISSION_QUICK_REFERENCE.md](PERMISSION_QUICK_REFERENCE.md) for quick fixes
2. Review relevant sections in [MANUAL_PR_GUIDE.md](MANUAL_PR_GUIDE.md)
3. Consult [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines
4. Create an issue if problem persists

## Documentation Flow

```
┌─────────────┐
│  README.md  │  ← Start here for overview
└─────┬───────┘
      │
      ├─→ Want to learn? → Follow the exercise
      │
      ├─→ Want to contribute? → ┌────────────────────┐
      │                          │ CONTRIBUTING.md    │
      │                          └────────┬───────────┘
      │                                   │
      │                          Have write access?
      │                                   │
      │                          ├─→ Yes → Standard workflow
      │                          │
      │                          └─→ No → ┌──────────────────────┐
      │                                    │ MANUAL_PR_GUIDE.md   │
      │                                    └──────────┬───────────┘
      │                                               │
      └─→ Having permission issues? ─────────────────┼────→ ┌────────────────────────────┐
                                                      │      │ PERMISSION_QUICK_REFERENCE │
                                                      └──────┤ .md                        │
                                                             └────────────────────────────┘
```

## Key Topics Cross-Reference

| Topic | README | CONTRIBUTING | MANUAL_PR_GUIDE | PERMISSION_QUICK_REF |
|-------|--------|--------------|-----------------|---------------------|
| Repository Overview | ✓ | | | |
| Exercise Instructions | ✓ | | | |
| Code of Conduct | ✓ | ✓ | | |
| Forking | | ✓ | ✓ | ✓ |
| Pull Request Creation | | ✓ | ✓ | |
| Permission Errors | ✓ | ✓ | ✓ | ✓ |
| Authentication | | | ✓ | ✓ |
| Git Commands | | ✓ | ✓ | ✓ |
| Troubleshooting | | ✓ | ✓ | ✓ |
| Best Practices | | ✓ | ✓ | ✓ |

## Contribution to Documentation

If you want to improve this documentation:

1. Review [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines
2. Ensure changes maintain consistency across all documents
3. Update this index if you add new documents
4. Keep cross-references up to date

## External Resources

All documents reference these external resources:
- [GitHub Documentation](https://docs.github.com)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Skills](https://skills.github.com)
- [Contributor Covenant](https://www.contributor-covenant.org)

## Questions?

If you can't find what you're looking for:
1. Search all documentation files
2. Check existing [Issues](../../issues)
3. Create a new issue with the "documentation" label

---

Last updated: 2026-02-12
