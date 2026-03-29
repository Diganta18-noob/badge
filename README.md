# 🏆 GitHub Badge Hunter

Auto-earn GitHub profile achievements using GitHub Actions.

> **Badges targeted:** `YOLO` · `Pull Shark` · `Quickdraw` · `Pair Extraordinaire`

---

## 📁 Repo Structure

```
badge-hunter/
├── README.md                          ← this file
├── logs/
│   └── .gitkeep                       ← keeps the folder tracked by git
└── .github/
    └── workflows/
        ├── pull-shark.yml             ← earns YOLO + Pull Shark (auto PR & merge)
        ├── quickdraw.yml              ← earns Quickdraw (open + close issue fast)
        └── pair-extraordinaire.yml    ← earns Pair Extraordinaire (co-authored PR)
```

---

## ⚙️ One-Time Setup (Do This First!)

### 1. Create the repo

- Go to [github.com/new](https://github.com/new)
- Name it `badge-hunter` (or anything you like)
- Set it to **Public**
- ✅ Check **"Add a README file"**
- Click **Create repository**

### 2. Enable Actions write permissions

This is critical — without it, workflows can't push code or merge PRs.

1. Go to your repo → **Settings** → **Actions** → **General**
2. Scroll to **Workflow permissions**
3. Select ✅ **"Read and write permissions"**
4. Also check ✅ **"Allow GitHub Actions to create and approve pull requests"**
5. Click **Save**

### 3. Push this project

```bash
git remote add origin https://github.com/YOUR_USERNAME/badge-hunter.git
git branch -M main
git push -u origin main
```

---

## 🗂️ Workflow Details

### 🦈 `pull-shark.yml` — Pull Shark + YOLO

| Detail | Value |
|---|---|
| **Badges earned** | Pull Shark, YOLO |
| **Trigger** | Every 6 hours (cron) + manual |
| **What it does** | Creates a branch → commits a timestamp → opens a PR → merges without review |

> 💡 Click **"Run workflow"** manually from the Actions tab to trigger it multiple times. You need **2 merges** for Bronze, **16** for Silver, **128** for Gold.

### ⚡ `quickdraw.yml` — Quickdraw

| Detail | Value |
|---|---|
| **Badge earned** | Quickdraw |
| **Trigger** | Manual only |
| **What it does** | Opens an issue and closes it within seconds |

> ✅ Run this **once** manually. After that you have the badge permanently.

### 🔗 `pair-extraordinaire.yml` — Pair Extraordinaire

| Detail | Value |
|---|---|
| **Badge earned** | Pair Extraordinaire |
| **Trigger** | Manual only |
| **What it does** | Creates a co-authored commit → opens + merges a PR |

> ⚠️ **Before running:** Edit the workflow file and replace `FRIEND_GITHUB_USERNAME` and `FRIEND_GITHUB_EMAIL` with real values. Use the format `username@users.noreply.github.com`.

---

## 🎯 Badge Progress Tracker

| Badge | How to Trigger | Times Needed |
|---|---|---|
| ⚡ **Quickdraw** | Run `quickdraw.yml` once manually | 1 |
| 🦈 **Pull Shark** Bronze | Run `pull-shark.yml` × 2 | 2 PRs merged |
| 🦈 **Pull Shark** Silver | Run `pull-shark.yml` × 16 | 16 PRs merged |
| 🦈 **Pull Shark** Gold | Run `pull-shark.yml` × 128 | 128 PRs merged |
| 🤙 **YOLO** | Automatic with every `pull-shark.yml` run | 1 |
| 🔗 **Pair Extraordinaire** Bronze | Run `pair-extraordinaire.yml` × 1 | 1 co-authored PR |
| 🔗 **Pair Extraordinaire** Silver | Run `pair-extraordinaire.yml` × 10 | 10 co-authored PRs |

---

## 🚀 Quick Start Checklist

- [ ] 1. Create public repo `badge-hunter`
- [ ] 2. Enable Actions → Read & write permissions + Allow PRs
- [ ] 3. Push this project to the repo
- [ ] 4. Go to Actions tab → Run **"Quickdraw"** manually (1 time)
- [ ] 5. Go to Actions tab → Run **"Pull Shark + YOLO"** manually (as many times as you want)
- [ ] 6. Edit `pair-extraordinaire.yml` with your co-author details → Run it
- [ ] 7. Check your GitHub profile page for new badges 🎉

---

## 💡 Pro Tips

- Badges can take **a few minutes to a few hours** to appear on your profile after the action completes.
- For **Pair Extraordinaire**, use `yourusername@users.noreply.github.com` as the email format.
- The `pull-shark.yml` schedule runs every 6 hours automatically — leave it and collect badges passively.
- Check your badges at: `https://github.com/YOUR_USERNAME`

---

*Made for badge hunting on GitHub · Good luck Diganta! 🏆*
