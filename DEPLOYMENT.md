# Deploying to GitHub Pages (Quander Team Repository)

Follow these steps to host your site on GitHub Pages using the Quander team/organization repository:

## Step 1: Create or Use Existing Team Repository

1. Go to [GitHub.com](https://github.com) and sign in
2. Navigate to the **Quander organization** (or have a team member create the repo)
3. Click the "+" icon in the top right → "New repository"
4. Name it (e.g., `quander-landing`, `quander-website`, or `landing-page`)
5. Choose **Public** (required for free GitHub Pages)
6. Select the **Quander organization** as the owner (not your personal account)
7. **Don't** initialize with README, .gitignore, or license
8. Click "Create repository"

## Step 2: Initialize Git and Push (if not already done)

If you haven't initialized git in this folder yet, run:

```bash
cd /Users/ananyachadha/code/quander-simple-landing
git init
git add .
git commit -m "Initial commit"
```

## Step 3: Connect to Team Repository and Push

```bash
# Add the Quander team repository as remote (replace ORG_NAME and REPO_NAME)
git remote add origin https://github.com/ORG_NAME/REPO_NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

**Note:** You'll need write access to the Quander organization repository. If you don't have access, ask a team admin to:
- Add you as a collaborator, or
- Give you write access to the repository

## Step 4: Enable GitHub Pages

1. Go to the repository on GitHub (must be in the Quander organization)
2. Click **Settings** (top menu)
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

## Step 5: Access Your Site

Your site will be available at:
```
https://ORG_NAME.github.io/REPO_NAME/
```

For example, if the org is `quander` and repo is `landing-page`:
```
https://quander.github.io/landing-page/
```

**Note:** It may take a few minutes for the site to be live after enabling Pages.

## Custom Domain (Optional)

If you want to use a custom domain like `quander.co` or `quander.ai`:

1. In the Pages settings, add your custom domain
2. Update your DNS records to point to GitHub Pages
3. GitHub will provide the exact DNS settings needed

## Alternative: Using GitHub CLI

If you have GitHub CLI installed and you're part of the Quander organization:

```bash
# Create repo in the Quander organization
gh repo create quander/landing-page --public --source=. --remote=origin --push

# Or if repo already exists, just push:
git remote add origin https://github.com/quander/landing-page.git
git push -u origin main

# Then go to Settings → Pages and enable it
gh repo view --web
```

## Updating Your Site

Whenever you make changes:

```bash
git add .
git commit -m "Update site"
git push
```

Changes will be live within 1-2 minutes.

