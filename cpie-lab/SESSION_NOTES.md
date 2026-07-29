# CPiE Lab Website — Session Notes

> Last updated: **2026-05-07**
> Read this file when you come back to the project to remember where you left off.

---

## ✅ Project Status: LIVE

The CPiE lab website is **deployed and publicly accessible**:

- 🌐 **Live URL:** https://shereen777.github.io/cpie-lab/
- 📦 **GitHub repo:** https://github.com/Shereen777/cpie-lab
- 💻 **Local folder:** `/home/shereen/cpie-lab/`
- 🔧 **Local preview:** http://localhost:8765 (start with the dev-server command below)

The site auto-rebuilds whenever you push to `main`. No build step, no framework — pure HTML + CSS + JS.

---

## 📂 Files in this folder

| File | Purpose |
|---|---|
| `index.html` | All page content and structure (each section starts with a `<!-- SECTION -->` comment) |
| `styles.css` | All visual styling — theme colors are CSS variables in `:root` at the top |
| `script.js` | Custom cursor, particle background, scroll animations, stat counters, card tilt |
| `coderush.jpeg` | Photo for the CodeRush event card (Events section) |
| `actinspace.jpg` | Photo for the AIS 2025 / ActInSpace 2026 card (Events section) |
| `sarfraz.jpeg` | Mr. Sarfraz Raza's profile photo (Team section avatar) |
| `SESSION_NOTES.md` | This file. Untracked by git unless you `git add` it. |

---

## 🛠️ What was done in this session

1. **Built the website from scratch** based on Mr. Sarfraz's lab proposal memo.
2. **Sections created** (in display order): Hero · Vision · Research · Societies · CodeForge · Events · Team · Footer.
3. **Set up git** — initialized repo, made initial commit on branch `main`.
4. **Created GitHub repo** at `Shereen777/cpie-lab` (public).
5. **Pushed code** via VS Code's built-in GitHub OAuth (no PAT needed).
6. **Enabled GitHub Pages** via repo Settings → Pages → branch `main` / root.
7. **Added profile photo** for Mr. Sarfraz Raza in the Team section (with the rotating gradient ring around the circular avatar).
8. **Replaced 3 expiring LinkedIn images** with locally-hosted files (CodeRush, ActInSpace, Sarfraz photo) — LinkedIn URLs would have broken around June 2026.
9. **Resolved a git rebase conflict** (web-UI CNAME edits had created remote commits not in local repo).

---

## 🚧 Open / future work (non-urgent — pick up whenever)

- [ ] **Replace remaining Unsplash stock images** with real photos: research card images, society background images, NASA Space Apps event card. Method: drop photo into `/home/shereen/cpie-lab/`, change `<img src=...>` in `index.html`.
- [ ] **Add a favicon** — the browser tab is currently empty. Save a CPiE icon as `favicon.ico` in the folder and add `<link rel="icon" href="favicon.ico">` to `<head>` in `index.html`.
- [ ] **Add Open Graph / social preview** — when you share the URL on WhatsApp/LinkedIn, no preview card appears. Add `<meta property="og:title">`, `<meta property="og:description">`, `<meta property="og:image">` tags in `<head>`.
- [ ] **Custom domain** (e.g. `cpie.itu.edu.pk`) — possible if ITU IT gives DNS access. Set in repo Settings → Pages → Custom domain. (You experimented with CNAME during the session and reverted it.)
- [ ] **Update stat counters** if real numbers change — currently `15 / 6 / 4 / 3` (researchers / papers / societies / collabs) in `index.html` (`data-target` attributes).
- [ ] **Real email** in the footer — currently `mailto:sarfraz.raza@itu.edu.pk` (line ~441). Confirm or replace.
- [ ] **Real research-paper details** — replace any placeholder descriptions with the actual paper titles, authors, links, and PDFs once they're published.
- [ ] **Add a Contact form or "Apply to join" form** — currently just a `mailto:` button. Could use Formspree (free tier) for a working form without backend.

---

## ▶️ How to resume work

### To preview the site locally:
```bash
cd /home/shereen/cpie-lab
python3 -m http.server 8765
```
Then open http://localhost:8765 in your browser. Refresh after every save.

### To deploy any changes to the live site:
```bash
cd /home/shereen/cpie-lab
git pull          # always pull first to grab any web-UI commits
git add .
git commit -m "Describe what changed"
git push
```
Or use VS Code's Source Control sidebar (`Ctrl+Shift+G`) — stage, commit, sync changes.

### To re-engage Claude Code on this project:
Open Claude Code in this folder (or anywhere — I have memory of this project) and say something like:

> "Pick up CPiE work — I want to add a favicon."

…and I'll have the full context (project summary, URLs, your preferences) automatically loaded from memory.

---

## 📝 Notes & gotchas

- **Always `git pull` before `git push`.** During this session a push was rejected because GitHub web-UI CNAME edits had created commits not in the local repo. Fix: `git pull --rebase origin main` then push.
- **The custom cursor and particle background are CPU-light but disable-able** — see comments in `script.js` for how to remove them if needed for performance.
- **Theme colors are centralized.** Want to re-theme the whole site? Just change the variables in the `:root` block at the top of `styles.css` — every gradient, badge, button, and accent reads from those.
- **VS Code's GitHub OAuth handled credentials seamlessly** — you didn't need to enter a PAT. If it ever breaks, regenerate a token at github.com/settings/tokens (scope: `repo`).
