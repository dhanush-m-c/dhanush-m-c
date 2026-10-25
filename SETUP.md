# 🚀 Dhanush M C — GitHub Profile Deployment & Setup Guide

This guide provides step-by-step instructions for publishing and automating your animated GitHub profile repository.

---

## 📁 Repository Structure Overview

```
├── .github/
│   └── workflows/
│       └── snake.yml             # Automated Contribution Snake Generator (Platane/snk)
├── assets/
│   ├── banner.svg                # Custom wide animated hero banner (cyber grid + glowing neon)
│   ├── divider.svg               # Glowing neon laser gradient divider line
│   ├── developer-illustration.svg# Interactive terminal IDE + animated AI neural core
│   ├── footer-banner.svg         # Closing footer banner
│   ├── project-stockiq.svg       # StockIQ project banner card
│   ├── project-aegisops.svg      # AegisOps AI project banner card
│   ├── project-trimemory.svg     # TriMemory AI project banner card
│   ├── project-restaurant.svg    # Restaurant Website project banner card
│   └── github-contribution-grid-snake-dark.svg # High-fidelity local preview & fallback
├── README.md                     # Master profile README with 10 structured sections
└── SETUP.md                      # This step-by-step deployment and troubleshooting guide
```

---

## ⚡ Step 1: Create Your Special GitHub Profile Repository

GitHub provides a special feature: when you create a public repository with the exact same name as your GitHub username (`dhanush-m-c/dhanush-m-c`), the `README.md` file in that repository is displayed directly on your public GitHub profile (`https://github.com/dhanush-m-c`).

1. Log in to [GitHub](https://github.com).
2. Click the `+` icon in the top right corner and select **New repository**.
3. In the **Repository name** field, type: `dhanush-m-c`
4. Verify you see the special message:
   > *"You found a secret! `dhanush-m-c/dhanush-m-c` is a ✨special✨ repository that you can use to add a README.md to your GitHub profile. Make sure it's public and initialize it with a README to get started."*
5. Set visibility to **Public** (important: private repositories do not appear on your profile).
6. Leave "Add a README file" **unchecked** (we already have our comprehensive README).
7. Click **Create repository**.

---

## 📤 Step 2: Push Files from Your Workspace to GitHub

Open PowerShell or Command Prompt in your project directory (`Portfile files`), then run the following commands:

```powershell
# 1. Initialize git
git init -b main

# 2. Stage all assets, workflows, and README
git add .

# 3. Create your initial commit
git commit -m "feat: world-class animated profile with custom banners and snake workflow"

# 4. Link your remote GitHub repository
git remote add origin https://github.com/dhanush-m-c/dhanush-m-c.git

# 5. Push to GitHub
git push -u origin main
```

*(If you already have commits or an existing repository, you can use `git push -u origin main --force` or standard pull/rebase).*

---

## ⚙️ Step 3: Enable Workflow Permissions for the Snake Action

The Contribution Snake action automatically commits the animated SVG files to an `output` branch in your repository. To allow it to write to branches:

1. In your `dhanush-m-c/dhanush-m-c` repository on GitHub, navigate to:
   **Settings** (tab at the top right) → **Actions** (left sidebar) → **General**.
2. Scroll down to the section titled **Workflow permissions**.
3. Select **Read and write permissions**.
4. Check the box for **"Allow GitHub Actions to create and approve pull requests"** (optional, recommended).
5. Click **Save**.

---

## 🐍 Step 4: Run the Contribution Snake Workflow

Once permissions are set, trigger the action manually so your dynamic contribution animation is generated immediately:

1. Go to the **Actions** tab at the top of your repository.
2. In the left sidebar, click **"Generate Contribution Snake Animation"**.
3. On the right side, click the **Run workflow** dropdown button.
4. Select the `main` branch and click the green **Run workflow** button.
5. In approximately 30–60 seconds, the workflow will finish with a green checkmark (`✓`).
6. It automatically creates an `output` branch in your repository hosting:
   - `github-contribution-grid-snake.svg` (light mode)
   - `github-contribution-grid-snake-dark.svg` (dark mode with neon cyan accents)

> **Note**: Even before the action runs, the README is configured with a local SVG fallback (`./assets/github-contribution-grid-snake-dark.svg`), meaning your profile will **never** display a broken image icon.

---

## 🎨 Customizing Contact & Social Links

Review these lines in [README.md](file:///c:/Users/dhanu/OneDrive/Desktop/Portfile%20files/README.md) to adjust any personal handles:

- **LinkedIn URL**: Replace `https://linkedin.com/in/dhanush-m-c` with your custom LinkedIn vanity handle if different.
- **Email Address**: Currently set to `dhanushmc14@gmail.com` (update if you prefer an alternate contact email).

---

## 🔍 Troubleshooting & FAQ

### Q1: The contribution snake shows a 404 image on GitHub
- **Cause**: The GitHub Actions workflow hasn't executed yet, or workflow permissions were not set to "Read and write".
- **Fix**: Complete **Step 3** and **Step 4** above. Once the `output` branch exists on GitHub, the `<picture>` tag will automatically load the live animated SVG.

### Q2: Changes to SVG assets don't update immediately in the browser
- **Cause**: GitHub routes images through a caching proxy called `camo`.
- **Fix**: Hard refresh your browser using `Ctrl + F5` (Windows) or append a cache-busting query parameter (e.g. `./assets/banner.svg?v=2`).

### Q3: How often does the snake animation update?
- The workflow is configured in `.github/workflows/snake.yml` to run automatically **every 12 hours** (`cron: "0 0,12 * * *"`), as well as on every push to `main` and on manual trigger (`workflow_dispatch`).

---

✨ **Your GitHub Profile is now fully set up, automated, and ready to impress recruiters and fellow engineers!**
