# ✦ Jasverine's Creative Hall

A personal idea notebook that lives on GitHub Pages. Add ideas directly from the website — no code editing needed.

---

## 🚀 Setup (5 minutes)

### 1. Create the GitHub repository

1. Go to [github.com/new](https://github.com/new)
2. Name it `creative-hall` (or anything you like)
3. Set it to **Public**
4. Click **Create repository**

### 2. Upload these files

Upload the entire folder contents to your repo:
```
index.html
ideas/
  manifest.json
  template.html
README.md
```

You can drag-and-drop them on the GitHub website, or use Git:
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/creative-hall.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose branch: `main`, folder: `/ (root)`
4. Click **Save**
5. Wait ~1 minute, then visit: `https://YOUR_USERNAME.github.io/creative-hall/`

### 4. Create a GitHub Token

1. Go to [github.com/settings/tokens/new](https://github.com/settings/tokens/new)
2. Give it a name like `creative-hall`
3. Select scope: ✅ **repo** (full control of private repositories)
4. Click **Generate token** and **copy it** (you won't see it again)

### 5. Configure the website

1. Open your Creative Hall website
2. Click the **⚙** button in the nav
3. Fill in:
   - GitHub Username: `your-username`
   - Repository Name: `creative-hall`
   - Branch: `main`
   - Token: paste your token
4. Click **Save Settings**

Done! Now click **+ Add Idea** to write your first idea. ✦

---

## 📁 Structure

```
creative-hall/
├── index.html              ← Main app
├── ideas/
│   ├── manifest.json       ← Index of all ideas (auto-updated)
│   ├── template.html       ← HTML template for each idea
│   └── your-idea-123.html  ← Each idea gets its own file
└── README.md
```

## 📝 How it works

- Each idea is saved as its own `.html` file in the `ideas/` folder
- `manifest.json` stores the index (title, category, date, tags, preview)
- When you add an idea via the website, it commits both files to GitHub via the API
- GitHub Pages automatically serves the updated site

## 🎨 Customizing

- Change the site title in `index.html` (search for "Jasverine")
- Add/remove categories: edit the `CATEGORIES` array in `index.html` and the `<select>` in the Add modal
- Change colors: edit the `:root` CSS variables at the top of `index.html`
