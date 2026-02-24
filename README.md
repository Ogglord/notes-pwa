# TODO PWA

A lightweight Progressive Web App that reads your Logseq-style TODOs from a GitHub repo and displays them on your phone.

## Features

- **Parses Logseq markers**: `TODO`, `DOING`, `NOW`, `LATER`, `DONE`, `WAITING`
- **Priority support**: `[#A]`, `[#B]`, `[#C]`
- **Deadline/scheduled**: `DEADLINE: <date>`, `SCHEDULED: <date>`
- **Offline support**: Caches last-fetched data via service worker
- **Filter by status**: Quick filter tabs with counts
- **iPhone Add to Home Screen**: Full standalone PWA experience
- **Private repo support**: Optional GitHub token (stored in browser localStorage)

## Setup

### 1. Create this repo

Push this code to a new GitHub repo (e.g. `your-username/todo-pwa`).

### 2. Enable GitHub Pages

Go to **Settings → Pages → Source** and select **GitHub Actions**.

### 3. First visit

Open `https://your-username.github.io/todo-pwa/` and configure:

- **Owner**: Your GitHub username (or org) that owns the TODO repo
- **Repo**: The repo name containing your Logseq markdown files
- **Branch**: Usually `main`
- **Path**: Folder like `pages/` or `journals/`, or a specific file. Leave empty for repo root.
- **Token**: Only needed for private repos. Create a [fine-grained token](https://github.com/settings/tokens?type=beta) with `Contents: Read` permission on the target repo.

### 4. Add to iPhone Home Screen

In Safari, tap the share button → **Add to Home Screen**. The app will run in standalone mode with offline caching.

## Logseq syntax supported

```markdown
- TODO Buy groceries
- TODO [#A] Fix critical bug DEADLINE: <2025-03-01>
- DOING Write documentation
- NOW Deploy to production
- LATER Research new framework
- DONE Ship v1.0
- WAITING Review from @teammate
```

## Security note

If you use a GitHub token for private repos, it's stored in your browser's localStorage. This is fine for personal use on your own devices. Don't use this on shared/public computers.
