# Quick Reference: Resolving Permission Issues

This quick reference guide helps you quickly resolve common permission issues when working with GitHub repositories.

## Common Error Messages and Solutions

### "Permission denied (publickey)"

**Problem**: SSH authentication failed

**Solution**:
```bash
# Generate a new SSH key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Add the SSH key to your GitHub account
# Copy the public key: cat ~/.ssh/id_ed25519.pub
# Add it to GitHub Settings > SSH and GPG keys

# Test your connection
ssh -T git@github.com
```

### "remote: Permission to OWNER/REPO.git denied to USER"

**Problem**: You don't have write access to the repository

**Solutions**:

**Option 1: Fork the repository**
```bash
# 1. Fork on GitHub using the Fork button
# 2. Clone your fork
git clone https://github.com/YOUR_USERNAME/REPO.git

# 3. Add the original repository as upstream
cd REPO
git remote add upstream https://github.com/OWNER/REPO.git

# 4. Work on your fork and create PR from there
```

**Option 2: Request collaborator access**
- Contact the repository owner
- Ask to be added as a collaborator

### "refusing to allow a GitHub App to create or update workflow"

**Problem**: GitHub App lacks workflow permissions

**Solution**:
1. Repository Settings > Actions > General
2. Enable "Allow GitHub Actions to create and approve pull requests"
3. Or: Manually create/update workflows using a personal access token

### "Resource not accessible by integration"

**Problem**: GitHub Actions workflow lacks necessary permissions

**Solution**:
Add permissions to your workflow file:
```yaml
permissions:
  contents: write
  pull-requests: write
  issues: write
```

### "fatal: Authentication failed"

**Problem**: HTTPS authentication failed

**Solutions**:

**Option 1: Use GitHub CLI**
```bash
gh auth login
```

**Option 2: Use Personal Access Token**
```bash
# Create a PAT at: github.com/settings/tokens
# Use it as your password when prompted

# Or configure git credential helper
git config --global credential.helper cache
```

**Option 3: Switch to SSH**
```bash
# Change remote URL to use SSH
git remote set-url origin git@github.com:USERNAME/REPO.git
```

## Quick Commands

### Check Your Remotes
```bash
git remote -v
```

### Verify Repository Permissions
```bash
gh repo view OWNER/REPO --json permissions
```

### Check Who You're Authenticated As
```bash
gh auth status
```

### Fork a Repository via CLI
```bash
gh repo fork OWNER/REPO --clone
```

## Workflow Decision Tree

```
Do you have write access to the repository?
│
├─ YES: Clone directly and push to repository
│   └─ git clone https://github.com/OWNER/REPO.git
│
└─ NO: Fork the repository first
    ├─ Fork on GitHub (click Fork button)
    ├─ Clone your fork
    │   └─ git clone https://github.com/YOUR_USERNAME/REPO.git
    ├─ Create a branch and make changes
    ├─ Push to your fork
    └─ Create pull request from your fork to original repository
```

## Best Practices

### Before Starting Work

1. **Verify Access**
   ```bash
   gh repo view OWNER/REPO
   ```

2. **Fork if Needed**
   - No write access? Fork first!
   - Working on open source? Always fork!

3. **Set Up Remotes Correctly**
   ```bash
   # Your fork (or the repo if you have access)
   origin -> github.com/YOUR_USERNAME/REPO

   # Original repository (if you forked)
   upstream -> github.com/OWNER/REPO
   ```

### During Development

1. **Keep Your Fork Updated**
   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   git push origin main
   ```

2. **Work in Feature Branches**
   ```bash
   git checkout -b feature/my-feature
   ```

3. **Push to Your Fork**
   ```bash
   git push origin feature/my-feature
   ```

### Creating Pull Requests

1. **From Your Fork**
   - Go to original repository
   - Click "New Pull Request"
   - Click "compare across forks"
   - Select your fork and branch

2. **Include in PR Description**
   - What changes you made
   - Why you made them
   - How to test them
   - Reference any related issues

## When to Use Each Authentication Method

| Method | Use When | Pros | Cons |
|--------|----------|------|------|
| **SSH** | You frequently push to GitHub | Secure, no password prompts | Initial setup required |
| **HTTPS + Token** | You occasionally contribute | Easy to set up | Need to manage token |
| **GitHub CLI** | You use GitHub extensively | Handles auth automatically | Requires CLI installation |

## Emergency Fixes

### "I Can't Push My Changes!"

```bash
# 1. Check which remote you're pushing to
git remote -v

# 2. If it's the wrong remote, fix it
git remote set-url origin https://github.com/YOUR_USERNAME/REPO.git

# 3. Try pushing again
git push origin branch-name
```

### "I Accidentally Pushed to Wrong Repository"

```bash
# If you have access to the wrong repo:
# 1. Delete the branch from the wrong repo (if possible)
gh api repos/WRONG_OWNER/REPO/git/refs/heads/branch-name -X DELETE

# 2. Push to correct repository
git push correct-origin branch-name
```

### "My PR Says There Are Conflicts"

```bash
# 1. Update your local main branch
git checkout main
git pull upstream main

# 2. Rebase your feature branch
git checkout feature-branch
git rebase main

# 3. Resolve any conflicts in your editor

# 4. Continue rebase
git add .
git rebase --continue

# 5. Force push to your fork (since history changed)
git push --force-with-lease origin feature-branch
```

## Additional Resources

- [GitHub Docs: Authentication](https://docs.github.com/en/authentication)
- [GitHub Docs: Permission levels](https://docs.github.com/en/organizations/managing-access-to-your-organizations-repositories/repository-roles-for-an-organization)
- [GitHub CLI Documentation](https://cli.github.com/manual/)
- [Git Credential Storage](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage)

## Still Having Issues?

1. Check [MANUAL_PR_GUIDE.md](./MANUAL_PR_GUIDE.md) for detailed step-by-step instructions
2. Review [CONTRIBUTING.md](./CONTRIBUTING.md) for contribution guidelines
3. Search existing issues in the repository
4. Create a new issue with the "help wanted" label

---

*Part of the communicate-using-markdown repository*
