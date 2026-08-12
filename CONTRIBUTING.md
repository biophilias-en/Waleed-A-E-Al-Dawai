# Contributing to Communicate Using Markdown

Thank you for your interest in contributing to this GitHub Skills exercise! This document provides guidelines for contributing to this repository.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Permission Issues](#permission-issues)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

This project adheres to the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md). By participating, you are expected to uphold this code.

## Getting Started

This repository is a GitHub Skills exercise designed to teach Markdown formatting. Before contributing, please:

1. Complete the exercise yourself to understand the learning objectives
2. Review existing issues and pull requests
3. Check if your contribution aligns with the exercise goals

## How to Contribute

### Reporting Issues

If you find a bug or have a suggestion:

1. Check if the issue already exists in the [Issues](../../issues) tab
2. If not, create a new issue with:
   - A clear, descriptive title
   - Detailed description of the problem or suggestion
   - Steps to reproduce (for bugs)
   - Expected vs. actual behavior
   - Screenshots if applicable

### Suggesting Improvements

We welcome suggestions for:
- Clarifying instructions
- Fixing typos or grammar
- Improving examples
- Adding helpful resources
- Enhancing workflow efficiency

## Permission Issues

> **Quick Reference**: For common permission errors and quick solutions, see [PERMISSION_QUICK_REFERENCE.md](./PERMISSION_QUICK_REFERENCE.md)

### I Don't Have Write Access to This Repository

If you encounter permission issues when trying to contribute:

1. **Fork the Repository**: Create your own copy of the repository
   - Click the "Fork" button at the top-right of the repository page
   - This creates a copy under your GitHub account

2. **Make Changes in Your Fork**: Work on your changes in your forked repository
   - Clone your fork to your local machine
   - Create a new branch for your changes
   - Make and commit your changes

3. **Create a Pull Request from Your Fork**: Submit your changes for review
   - Push your branch to your fork
   - Navigate to the original repository
   - Click "New pull request"
   - Click "compare across forks"
   - Select your fork and branch as the compare branch
   - Fill in the pull request details and submit

### Automated Tools and Bot Access

If you're working with automated tools or bots that lack write permissions:

- **Use the Manual Process**: Follow the [Manual Pull Request Guide](./MANUAL_PR_GUIDE.md)
- **Quick Fixes**: Check [Permission Quick Reference](./PERMISSION_QUICK_REFERENCE.md) for common issues
- **Request Access**: Contact the repository maintainers if you need direct access
- **GitHub Apps**: Ensure GitHub Apps have proper permissions configured in repository settings

## Pull Request Process

### Before Submitting a Pull Request

1. **Create a Feature Branch**
   ```bash
   git checkout -b descriptive-branch-name
   ```

2. **Make Your Changes**
   - Keep changes focused and minimal
   - Follow existing code style and conventions
   - Update documentation if needed

3. **Test Your Changes**
   - Verify that workflows still work
   - Check that Markdown renders correctly
   - Ensure no broken links

4. **Commit Your Changes**
   ```bash
   git add .
   git commit -m "Brief description of changes"
   ```

### Submitting a Pull Request

1. Push your branch to GitHub (your fork if you don't have write access)
2. Navigate to the repository and click "New pull request"
3. Provide a clear title and description:
   - Explain what changes you made
   - Why you made these changes
   - Reference any related issues (e.g., "Fixes #123")
4. Submit the pull request

### After Submitting

- Respond to feedback and review comments promptly
- Make requested changes in your branch and push updates
- Be patient - reviews may take time
- Keep the PR focused - avoid adding unrelated changes

## Style Guidelines

### Markdown Style

- Use consistent heading levels
- Include blank lines between sections
- Use code blocks with language identifiers
- Keep line lengths reasonable (80-100 characters when possible)
- Use relative links for internal references

### Commit Messages

- Use present tense ("Add feature" not "Added feature")
- Use imperative mood ("Move cursor to..." not "Moves cursor to...")
- Start with a capital letter
- Keep the first line under 50 characters
- Add detailed description after a blank line if needed

Example:
```
Add manual PR creation guide

- Created comprehensive guide for manual PR creation
- Addressed common permission issues
- Included troubleshooting section
```

### Documentation

- Write clear, concise instructions
- Use examples to illustrate points
- Include screenshots for visual steps
- Test all instructions before submitting
- Keep language accessible to beginners

## Workflow Files

When modifying GitHub Actions workflows:

1. **Test Thoroughly**: Workflow changes can break the exercise
2. **Maintain Backward Compatibility**: Ensure existing users aren't affected
3. **Document Changes**: Update relevant documentation
4. **Follow Security Best Practices**: 
   - Use minimal required permissions
   - Pin action versions
   - Avoid exposing secrets

### Required Permissions

Most workflows in this repository require:
```yaml
permissions:
  contents: write
  actions: write
  issues: write
```

If you're adding new workflows, ensure they have appropriate permissions.

## Questions?

If you have questions about contributing:

1. Check existing [Discussions](../../discussions) if enabled
2. Review closed [Issues](../../issues?q=is%3Aissue+is%3Aclosed) for similar questions
3. Create a new issue with the "question" label
4. Reach out to maintainers if needed

## License

By contributing, you agree that your contributions will be licensed under the same [MIT License](./LICENSE) that covers this project.

## Acknowledgments

Thank you for taking the time to contribute! Your efforts help make this learning resource better for everyone.

---

For detailed instructions on creating pull requests manually, see [MANUAL_PR_GUIDE.md](./MANUAL_PR_GUIDE.md).
