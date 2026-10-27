# How to publish this article on GitHub

This folder is ready to become a GitHub repository. Below is the exact structure, then two ways to publish it — one entirely in the browser, one with git.

## Repository structure

```
memory-forensics-article/
├── README.md          <- the article (renders on the repo page)
├── LICENSE            <- MIT licence
├── SETUP-GITHUB.md    <- this file (optional, delete after setup)
└── docs/
    ├── _config.yml    <- GitHub Pages settings (theme, title)
    └── index.md       <- the article as a website homepage
```

The `README.md` and `docs/index.md` hold the same article. The first is what visitors read on the repository page; the second is what GitHub Pages turns into a live web page.

---

## Option A — Browser only (no installation)

1. Sign in to GitHub and click the **+** icon at the top right, then **New repository**.
2. Fill in:
   - **Repository name:** `memory-forensics-article`
   - **Description:** `Self-learning article on memory forensics and fileless malware — Advanced Digital Forensics (MOOC)`
   - **Visibility:** Public (required if you want a free GitHub Pages site and a link you can share)
   - Leave *Add a README file*, *.gitignore* and *licence* unticked — you are uploading your own.
3. Click **Create repository**.
4. On the empty repository page, click **uploading an existing file** (or **Add file → Upload files**).
5. Drag in `README.md`, `LICENSE` and `SETUP-GITHUB.md`. In the commit box type `Add memory forensics article` and click **Commit changes**.
6. Create the `docs` folder: click **Add file → Create new file**, type `docs/index.md` in the filename box (the slash creates the folder), paste the contents of `index.md`, and commit.
7. Repeat for the settings file: **Add file → Create new file**, name it `docs/_config.yml`, paste the contents of `_config.yml`, and commit.
8. Turn on the website: go to **Settings → Pages**. Under *Build and deployment*, set **Source** to `Deploy from a branch`, **Branch** to `main`, **Folder** to `/docs`, then click **Save**.
9. Wait one to two minutes and refresh the Pages screen. Your link appears there, in the form:

   ```
   https://<your-username>.github.io/memory-forensics-article/
   ```

10. Optional polish: on the repository home page click the gear next to *About* and add the description plus topics such as `digital-forensics`, `memory-forensics`, `malware-analysis`, `incident-response`, `cybersecurity`.

## Option B — Command line (git)

```bash
# 1. Create an empty public repo named memory-forensics-article on github.com first,
#    then in the folder that holds these files:
git init
git add README.md LICENSE SETUP-GITHUB.md docs/index.md docs/_config.yml
git commit -m "Add memory forensics article"
git branch -M main
git remote add origin https://github.com/<your-username>/memory-forensics-article.git
git push -u origin main
```

Then enable Pages exactly as in steps 8–9 above.

If you prefer, GitHub CLI does the whole thing in one go:

```bash
gh repo create memory-forensics-article --public --source=. --remote=origin --push
```

## After publishing

- Add the live link to your resume, LinkedIn *Featured* section, or your portfolio page.
- Pin the repository on your GitHub profile: **Profile → Customize your pins**.
- If you edit the article later, edit `README.md` **and** `docs/index.md` so the repo page and the website stay in sync — or keep only one and delete the other.

## Notes

- `_config.yml` uses the `jekyll-theme-cayman` theme, which GitHub supports out of the box — no build step needed.
- If the Pages build fails, check **Settings → Pages** for the error and confirm the folder is `/docs` and the file is named `index.md` exactly.
- The MIT licence suits a code repository. For a written article, Creative Commons Attribution 4.0 (CC BY 4.0) is often a better fit — replace `LICENSE` with the CC BY 4.0 text if you prefer it.
