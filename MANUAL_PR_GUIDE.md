# Manual Pull Request Creation Guide

## Overview

This guide helps you create pull requests manually when automated tools don't have sufficient write permissions to a repository.

## When to Use This Guide

You may need to create a pull request manually when:
- Automated tools or bots lack write permissions to the target repository
- You're working with a forked repository
- You need more control over the PR creation process
- GitHub Actions workflows don't have the necessary permissions

## Prerequisites

Before creating a manual pull request, ensure you have:
- A GitHub account with access to the repository
- Git installed on your local machine
- The changes you want to include are committed to a branch

## Step-by-Step Instructions

### 1. Fork the Repository (If You Don't Have Write Access)

If you don't have write access to the target repository:

1. Navigate to the repository on GitHub
2. Click the **Fork** button in the top-right corner
3. Select your account as the destination for the fork

### 2. Clone Your Fork (or the Repository)

```bash
# If you forked the repository
git clone https://github.com/YOUR_USERNAME/REPOSITORY_NAME.git

# Or if you have write access to the original repository
git clone https://github.com/OWNER/REPOSITORY_NAME.git

cd REPOSITORY_NAME
```

### 3. Create a New Branch

```bash
# Create and switch to a new branch
git checkout -b feature/your-branch-name

# Or use the newer git switch command
git switch -c feature/your-branch-name
```

### 4. Make Your Changes

Make the necessary changes to the files in your local repository using your preferred text editor or IDE.

### 5. Stage and Commit Your Changes

```bash
# Stage all changes
git add .

# Or stage specific files
git add path/to/file1 path/to/file2

# Commit your changes with a descriptive message
git commit -m "Brief description of your changes"
```

### 6. Push Your Branch to GitHub

```bash
# If you forked the repository, set the upstream remote first (one-time setup)
git remote add upstream https://github.com/ORIGINAL_OWNER/REPOSITORY_NAME.git

# Push your branch to your fork or repository
git push origin feature/your-branch-name

# If this is the first push for this branch
git push --set-upstream origin feature/your-branch-name
```

### 7. Create the Pull Request on GitHub

1. Navigate to your repository (or fork) on GitHub
2. You should see a banner suggesting to create a pull request for your recently pushed branch
3. Click the **Compare & pull request** button

Alternatively:
1. Go to the **Pull requests** tab
2. Click **New pull request**
3. Select the base repository and branch (usually `main` or `master`)
4. Select your fork and branch as the compare branch
5. Click **Create pull request**

### 8. Fill in Pull Request Details

Provide a clear and descriptive pull request with:
- **Title**: A concise summary of your changes
- **Description**: Detailed explanation of:
  - What changes you made
  - Why you made these changes
  - Any relevant context or background
  - Steps to test the changes (if applicable)
  - Screenshots or examples (if applicable)

### 9. Submit the Pull Request

Click the **Create pull request** button to submit your PR for review.

## Best Practices

### Commit Messages
- Use clear, descriptive commit messages
- Start with a verb in present tense (e.g., "Add feature", "Fix bug", "Update documentation")
- Keep the first line under 50 characters
- Add more details in subsequent lines if needed

### Pull Request Description
- Reference any related issues (e.g., "Fixes #123", "Closes #456")
- Include screenshots for UI changes
- List any breaking changes
- Mention if documentation needs updating

### Before Submitting
- [ ] Review your changes carefully
- [ ] Test your changes locally
- [ ] Ensure your code follows the project's style guidelines
- [ ] Update documentation if needed
- [ ] Add or update tests if applicable
- [ ] Rebase or merge with the latest main branch to avoid conflicts

## Handling Permission Issues

### If You Encounter "Insufficient Permissions" Errors

1. **Verify Repository Access**
   - Ensure you're working with your fork if you don't have write access
   - Check that you're pushing to the correct remote

2. **Update Remote URLs**
   ```bash
   # Check your current remotes
   git remote -v
   
   # Update origin to point to your fork
   git remote set-url origin https://github.com/YOUR_USERNAME/REPOSITORY_NAME.git
   ```

3. **Configure Git Authentication**
   ```bash
   # Using GitHub CLI
   gh auth login
   
   # Or use SSH keys
   # Add your SSH key to GitHub and use SSH URLs
   git remote set-url origin git@github.com:YOUR_USERNAME/REPOSITORY_NAME.git
   ```

## Troubleshooting

### "Permission denied" Error
- Verify your GitHub authentication (HTTPS token or SSH key)
- Ensure you're pushing to your fork, not the upstream repository
- Check if your access token has the required scopes

### "Branch already exists" Error
- Use a different branch name
- Or force push (use with caution): `git push -f origin branch-name`

### "Merge conflicts" Error
- Pull the latest changes from the base branch
- Resolve conflicts locally
- Commit the resolved changes
- Push again

## Additional Resources

- [GitHub Docs: Creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)
- [GitHub Docs: Creating a pull request from a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Skills - Introduction to GitHub](https://github.com/skills/introduction-to-github)

## Need Help?

If you're still experiencing issues:
1. Check the repository's CONTRIBUTING.md file for specific guidelines
2. Review existing pull requests to see examples
3. Ask for help in the repository's discussions or issues
4. Contact the repository maintainers

---

_This guide is part of the communicate-using-markdown repository and demonstrates best practices for collaborative development on GitHub._
