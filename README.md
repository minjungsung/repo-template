# repo-template

Template repository with pre-configured security and CI/CD settings.

## What's included

- **Dependabot** — weekly dependency + GitHub Actions version updates
- **Dependabot auto-merge** — auto-approve + squash merge for patch/minor updates
- **Release workflow** — tag-based releases with auto-generated changelog

## Usage

1. Click **"Use this template"** → **"Create a new repository"**
2. Edit `.github/dependabot.yml` — change `package-ecosystem` to match your project (`npm`, `pip`, `gradle`, `nuget`, `cargo`, etc.)
3. After creation, enable in repo Settings → Security:
   - Dependabot alerts ✅
   - Dependabot security updates ✅
   - Secret scanning ✅ (public repos)
   - Push protection ✅ (public repos)

## After creating from template

Enable auto-merge on the repo:
```bash
gh repo edit OWNER/REPO --enable-auto-merge
```

Enable GitHub Actions PR approval:
```bash
gh api repos/OWNER/REPO/actions/permissions/workflow -X PUT \
  -f default_workflow_permissions=write \
  -F can_approve_pull_request_reviews=true
```
