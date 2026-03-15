# Agent Guide

## Accepting GitHub Repository Invitations and First Commit

1. **Accept invitation**:
   ```bash
   gh api user/repository_invitations --jq '.[0].id'  # Get invitation ID
   gh api user/repository_invitations/{id} -X PATCH   # Accept
   ```

2. **Clone repository** (use SSH or HTTPS depending on auth):
   ```bash
   git clone git@github.com:owner/repo.git
   ```

3. **If SSH fails with host key**, use:
   ```bash
   GIT_SSH_COMMAND="ssh -o StrictHostKeyChecking=accept-new" git clone git@github.com:owner/repo.git
   ```

4. **Create content and push**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

**Important**: Never commit and push automatically. Only commit when explicitly requested by the user.
