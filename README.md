# jbilla.com

Personal website for Jayadev Billa, PhD. Static HTML/CSS, no build step.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Entire site — edit this directly |
| `CNAME` | Tells GitHub Pages which domain to serve |
| `favicon.ico` | Placeholder — drop in your own 32×32 `.ico` |

---

## Deploying to GitHub Pages

### 1. Create the repo

Create a new public GitHub repository. The name doesn't matter (e.g. `website` or `jbilla.com`).

### 2. Push the files

```bash
cd /path/to/this/folder
git init
git add .
git commit -m "Initial site"
git remote add origin git@github.com:YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

### 3. Enable GitHub Pages

In the repo on GitHub:

1. Go to **Settings → Pages**.
2. Under **Source**, choose **Deploy from a branch**.
3. Select branch `main`, folder `/ (root)`.
4. Click **Save**.

GitHub will show a banner with the `*.github.io` URL once the deploy succeeds (usually under a minute).

### 4. Point your custom domain

In your DNS registrar (wherever you manage `jbilla.com`), add these records:

**Apex domain (`jbilla.com`) — four A records:**

```
A  @  185.199.108.153
A  @  185.199.109.153
A  @  185.199.110.153
A  @  185.199.111.153
```

**WWW subdomain — one CNAME record:**

```
CNAME  www  YOUR_USERNAME.github.io.
```

Then, back in **Settings → Pages**, enter `jbilla.com` in the **Custom domain** field and click **Save**. GitHub will provision an HTTPS certificate via Let's Encrypt automatically (can take up to 24 hours for DNS to propagate).

The `CNAME` file in this repo is what tells GitHub Pages to respond to `jbilla.com` — don't delete it.

### 5. Redirect jbilla.org / jbilla.net (optional)

Set up a DNS redirect at your registrar for `jbilla.org` and `jbilla.net` pointing to `jbilla.com`. Most registrars support "URL forwarding" or "domain redirect" in their DNS panel.

---

## Updating content

All content is in a single `index.html`. Common edits:

**Replace a code link placeholder:**
Find `href="#"` next to the relevant paper's `Code` link and replace `#` with the real URL.

**Promote a "Demo coming soon" to a live link:**
1. Replace `href="#"` with the real URL.
2. Remove the `class="demo-coming"` attribute from that `<a>` tag.

**Add a new paper:**
Copy an existing `<article class="paper">` block and edit in place.

**Add a favicon:**
Drop a `favicon.ico` (32×32 pixels) into the repo root. The `<link rel="icon">` tag already points to it.
