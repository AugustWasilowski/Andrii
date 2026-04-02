# 🛠️ Website — Setup Guide
---

## How This All Works (The Big Picture)

```
Your Computer                    GitHub                     Firebase
┌──────────┐    git push     ┌──────────┐   auto-deploy  ┌──────────┐
│  Edit     │ ──────────────►│  Stores   │ ─────────────► │  Live    │
│  files    │                │  the code │                │  website │
└──────────┘                 └──────────┘                 └──────────┘
```

1. **You edit** the website files on your computer.
2. **You push** those changes to GitHub (an online code vault).
3. **GitHub automatically deploys** the new version to Firebase (the web host).
4. **The live website updates** — no extra steps.

---

## Part 1 — Create Your Accounts

### 1A · GitHub Account

1. Go to **https://github.com/signup**
2. Use your Gmail address.
3. Pick a username (something professional — this is like a public portfolio).
4. Choose the **Free** plan.
5. Verify your email by clicking the link GitHub sends you.

### 1B · Tell August Your GitHub Username

Once your account exists, tell August (the repo owner) your username so he can **add you as a collaborator** on the project. You'll get an invite email from GitHub — **click "Accept"** in that email.

> **You cannot push changes until August adds you.** This is a one-time step.

---

## Part 2 — Install the Tools

Install these **in order**. Each one takes a few minutes.

### 2A · Git for Windows

Git is the tool that moves code between your computer and GitHub.

1. Go to **https://git-scm.com/download/win**
2. Download the **64-bit** installer.
3. Run it. **Use all the default settings** — just keep clicking "Next" then "Install."
4. When it finishes, open **PowerShell** (search for it in the Start menu) and type:
   ```
   git --version
   ```
   You should see something like `git version 2.47.1`. If you do, you're good.

### 2B · Node.js

Node.js runs JavaScript tools like the Firebase CLI.

1. Go to **https://nodejs.org**
2. Download the **LTS** version (the big green button).
3. Run the installer. **Use all the default settings.**
4. **Restart PowerShell** (close it and open it again) and type:
   ```
   node --version
   ```
   You should see something like `v22.x.x`. If you do, you're good.

### 2C · Python

Some developer tools need Python behind the scenes.

1. Go to **https://www.python.org/downloads/**
2. Click the big yellow "Download Python" button.
3. Run the installer. ⚠️ **CHECK THE BOX** that says **"Add python.exe to PATH"** before clicking "Install Now."
4. **Restart PowerShell** and type:
   ```
   python --version
   ```
   You should see something like `Python 3.12.x`.

### 2D · Firebase CLI

The Firebase CLI lets you preview the site locally.

1. Open PowerShell and run:
   ```
   npm install -g firebase-tools
   ```
2. After it finishes, run:
   ```
   firebase --version
   ```
   You should see a version number.

3. Log in to Firebase with your Gmail:
   ```
   firebase login
   ```
   A browser window will pop open. Sign in with your Gmail and click "Allow."

---

## Part 3 — Install The Code Editor (Antigravity / Jules IDE)

### 3A · Download & Install

1. Go to **https://gemini.google.com/app/download-antigravity** (or wherever August gives you the download link).
2. Download the Windows installer and run it.
3. Open Antigravity when it's done installing.

### 3B · Sign In

1. When Antigravity opens, sign in with your **Gmail address** (the same one you used for GitHub).

### 3C · Connect GitHub

1. Open the **Command Palette**: press `Ctrl + Shift + P`
2. Type **"GitHub: Sign In"** and select it.
3. A browser tab will open asking you to authorize. Click **"Authorize"**.
4. Go back to Antigravity — you're connected.

---

## Part 4 — Clone the Website to Your Computer

"Cloning" means downloading a copy of the project from GitHub to your computer.

1. In Antigravity, press `Ctrl + Shift + P` and type **"Git: Clone"**.
2. Paste this URL:
   ```
   https://github.com/AugustWasilowski/Andrii.git
   ```
3. Pick a folder on your computer where you want the project to live (e.g. `C:\Users\YourName\Projects`).
4. Click **"Open"** when it asks if you want to open the cloned repository.

You should now see the project files in the left sidebar:
- `index.html` — the Home page
- `our-story.html` — the Our Story page
- `services-gallery.html` — the Services & Gallery page
- `contact-quote.html` — the Contact & Quote page
- `firebase.json` — tells Firebase how to host the site

---

## Part 5 — Preview the Site on Your Computer

Before you make any changes, let's make sure you can see the site locally.

1. In Antigravity, open the **Terminal**: press `` Ctrl + ` `` (that's the backtick key, above Tab).
2. Type:
   ```
   firebase serve
   ```
3. You'll see a message like:
   ```
   ✔ hosting: Local server: http://localhost:5000
   ```
4. Open your browser and go to **http://localhost:5000**
5. You should see the Bespoke Craftsman website! 🎉

> Press `Ctrl + C` in the terminal to stop the local server when you're done previewing.

---

## Part 6 — Make Your First Edit

Let's do a small change so you can see the whole flow working.

1. In the left sidebar, click on **`index.html`**.
2. Find this line (around line 312):
   ```html
   © 2024 The Bespoke Craftsman. Meticulously Crafted Bathrooms.
   ```
3. Change `2024` to `2025` (or whatever the current year is).
4. Save the file: `Ctrl + S`
5. If your local server is still running, refresh the browser to see the change.

---

## Part 7 — Push Your Changes to GitHub (and the live site)

This is the part that makes the live website update. There are three steps: **Stage → Commit → Push.**

### Using the Sidebar (Easiest)

1. Click the **Source Control** icon in the left sidebar (it looks like a branching line, or it might show a number badge).
2. You'll see your changed file listed under "Changes."
3. Hover over the file and click the **`+`** button to **Stage** it (this tells Git "I want to include this change").
4. In the text box at the top that says "Message", type a short description of what you changed, like:
   ```
   Update copyright year to 2025
   ```
5. Click the **✓ Commit** button (the checkmark).
6. Click the **"Sync Changes"** button (or the up-arrow ↑ button). This pushes your code to GitHub.

### What Happens Next (Automatic)

- GitHub receives your code.
- A **GitHub Action** (an automated script that's already set up) detects that `main` was updated.
- It automatically deploys your change to Firebase.
- **Within 1–2 minutes**, the live website is updated.

> **Live site URL:** https://andrii-491416.web.app (or the custom domain if one is configured).

---

## Part 8 — The Daily Routine (Cheat Sheet)

Every time you sit down to work on the website:

```
1. Open Antigravity
2. Open the project folder
3. Pull latest changes:    click "↓ Sync" or run: git pull
4. Start local server:     firebase serve
5. Make your edits
6. Preview at:             http://localhost:5000
7. Stage your changes:     click the + button
8. Write a commit message
9. Commit:                 click ✓
10. Push:                  click "Sync Changes"
11. Wait 1-2 min, check the live site
```

---

## Quick Reference — The Files

| File | What It Is |
|---|---|
| `index.html` | **Home page** — hero image, founder story, portfolio, CTA |
| `our-story.html` | **Our Story page** — about the founder |
| `services-gallery.html` | **Services & Gallery** — what we do + photos |
| `contact-quote.html` | **Contact & Quote** — contact form and info |
| `firebase.json` | Config file — tells Firebase what to host. **Don't edit this.** |
| `.firebaserc` | Config file — links to the Firebase project. **Don't edit this.** |
| `.github/workflows/` | Auto-deploy scripts. **Don't edit these.** |

---

## Common Edits You Might Make

### Change text on the page

1. Open the `.html` file.
2. Find the text you want to change (use `Ctrl + F` to search).
3. Edit the text between the `>` and `<` tags. For example:
   ```html
   <!-- Before -->
   <h2>A Journey from Kyiv to Your Home.</h2>

   <!-- After -->
   <h2>A Journey from Ukraine to Your Home.</h2>
   ```
4. Save, preview, commit, push.

### Change the phone number

Search for `(630) 870-5855` across all files (`Ctrl + Shift + F`) and replace it everywhere.

### Change the email

Search for `hello@bespokecraftsman.com` across all files and replace it.

### Change a color

The site uses a color system defined at the top of each HTML file in the `tailwind.config` section. The main colors are:
- `primary` — The main brand blue-grey (`#324a5b`)
- `secondary` — The warm brown accent (`#6c5b4e`)
- `tertiary` — Gold/amber accent (`#5c4328`)

To change the primary brand color, find this line in each `.html` file:
```js
"primary": "#324a5b",
```
And replace the hex code with a new color. Use **https://htmlcolorcodes.com** to pick one.

---

## Troubleshooting

### "I made changes but the live site didn't update"
- Go to **https://github.com/AugustWasilowski/Andrii/actions**
- Check if the latest workflow run is green ✅ or red ❌.
- If red, click on it to see what went wrong and tell August.

### "git push says 'permission denied'"
- August hasn't added you as a collaborator yet. Tell him your GitHub username.

### "firebase serve says 'command not found'"
- You need to install Firebase CLI. Re-do step **2D**.
- Or try restarting PowerShell.

### "I accidentally broke something"
Don't panic. Git saves everything.
1. To undo all your unsaved changes to a file:
   - Right-click the file in Source Control → **"Discard Changes"**
2. To undo your last commit (before pushing):
   ```
   git reset HEAD~1
   ```
3. If you already pushed and it broke the live site, tell August. He can revert it from GitHub.

### "I see 'merge conflict'"
This means someone else edited the same line you did at the same time. Tell August and he'll help you fix it.

---

## Glossary

| Word | What it means |
|---|---|
| **Git** | A tool that tracks changes to files and shares them between computers |
| **GitHub** | A website that stores Git projects online |
| **Clone** | Download a copy of a project from GitHub to your computer |
| **Commit** | Save a snapshot of your changes (like a save point in a game) |
| **Push** | Upload your commits to GitHub |
| **Pull** | Download the latest changes from GitHub to your computer |
| **Repository (repo)** | A project folder tracked by Git |
| **Branch** | A separate version of the code (we use `main`) |
| **Firebase** | Google's web hosting service — where the live site lives |
| **CLI** | Command Line Interface — a text-based tool you run in PowerShell |
| **HTML** | The language web pages are written in |
| **Deploy** | Put new code onto the live website |
| **GitHub Action** | An automated script that runs when you push code |

---

*Guide written April 2026. If something doesn't work, ask August!* 🚀
