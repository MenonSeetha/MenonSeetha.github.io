# Deploying your site to GitHub Pages

Your new site lives in this `Website` folder: four pages (`index.html`, `publications.html`,
`awards.html`, `media.html`), one stylesheet (`style.css`), and a `CNAME` file that tells
GitHub your custom domain.

Work top to bottom. Steps 1–2 you can do today; step 5 (DNS) is the only one that touches
your live domain, and it is fully reversible.

---

## Before you publish — three things to add to this folder

1. **Your photo.** Save a headshot as `assets/headshot.jpg` inside the Website folder.
   (Create an `assets` subfolder.) Until you do, the homepage simply shows no photo — it
   won't break. Roughly 600×800 px, portrait, is ideal.

2. **Your CV.** Save your CV as `assets/Seetha_Menon_CV.pdf`. The "Curriculum Vitae"
   button on the homepage links to it. You can reuse `Menon_CV.pdf` from the Job Search folder.

3. **Your ORCID link.** In all four HTML files the footer has `href="https://orcid.org/"`.
   Replace that with your real ORCID URL (e.g. `https://orcid.org/0000-0002-1234-5678`).
   Tell me your ORCID and I'll do this for you in one pass.

---

## Step 1 — Create a GitHub account
If you don't have one: go to github.com and sign up (free). Pick a username — `seethamenon`
or similar is fine; it won't be visible on your site.

## Step 2 — Create the repository
1. Click the **+** (top right) → **New repository**.
2. Repository name: **`seethamenon.github.io`** — use your own username in place of
   `seethamenon`. The name MUST end in `.github.io`.
3. Set it to **Public**. Don't add a README. Click **Create repository**.

## Step 3 — Upload the site files
1. On the new repo page, click **uploading an existing file**.
2. Drag in everything inside this `Website` folder: the four `.html` files, `style.css`,
   `CNAME`, and your `assets` folder (with the photo and CV). Drag the *contents*, not the
   `Website` folder itself — `index.html` must sit at the top level of the repo.
3. Click **Commit changes**.

Within a minute your site is live at `https://seethamenon.github.io`. Check it works before
touching your domain.

## Step 4 — Turn on Pages (usually automatic)
Repo → **Settings** → **Pages**. Under "Build and deployment", Source should be
**Deploy from a branch**, branch **main**, folder **/ (root)**. Save if it isn't already set.

## Step 5 — Point seetha-menon.com at GitHub
This is the only step that changes your live domain. Do it once the github.io site looks right.

**5a. Find where your domain is registered.** Your domain is currently managed through Wix.
Two options:
   - *Easiest:* keep the domain at Wix and just change its DNS records to point at GitHub.
   - *Cleaner long-term:* transfer the domain to a dedicated registrar (Namecheap, Cloudflare).
     Not necessary now.

**5b. In your domain's DNS settings, add these records** (at Wix: Domains → your domain →
Advanced / DNS records):

   - Four **A records** for the apex domain (host `@`) pointing to GitHub's IPs:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - One **CNAME record**: host `www` → value `seethamenon.github.io`
     (your username + `.github.io`).
   - Remove any old A/CNAME records Wix added that conflict (the ones currently pointing the
     domain at Wix's servers).

**5c. Back in GitHub:** Settings → Pages → Custom domain — enter `seetha-menon.com`, Save.
(The `CNAME` file already in your repo does this too, but confirm it shows here.) Tick
**Enforce HTTPS** once it becomes available — this can take up to 24 hours while a certificate
is issued.

DNS changes take anywhere from 15 minutes to a few hours to propagate. Until then, the old
Wix site may still show — that's normal.

## Step 6 — Keep Wix live until the switch resolves, then cancel
Once `https://seetha-menon.com` reliably shows the new site (test in a private browser window),
you can cancel the Wix subscription. Not before — that's your safety net.

---

## Editing the site later
Every page is plain text. To change anything — add a paper, update a grant — either edit the
file on your computer and re-upload, or edit directly on GitHub (click the file → pencil icon →
Commit). Or just ask me: the files are in your Job Search folder and I can edit them in seconds.

## If something goes wrong
The whole change is reversible: restore the original Wix DNS records and your old site returns.
Nothing here deletes your Wix site until you choose to cancel it in step 6.
