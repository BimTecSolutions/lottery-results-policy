# Lottery Results — Privacy Policy Site

Static site hosted on GitHub Pages, used for the Play Store's required
"Privacy Policy" link (App content → Privacy policy, and the Data
safety section).

## Files
- `index.html` — About page (landing page, optional but nice to have)
- `privacy-policy.html` — **This is the URL you paste into the Play Console**

## 1. Before uploading — edit the placeholder email
Open `privacy-policy.html`, find:
```
support@yourdomain.com
```
(it appears twice — once as visible text, once inside `mailto:`) and
replace both with your real support email.

## 2. Create the GitHub repository
1. Go to https://github.com/new
2. Repository name: `lottery-results-policy` (or any name you like)
3. Set it to **Public** (GitHub Pages on the free tier requires a public repo)
4. Don't initialize with a README (you already have these files) — or
   if you do, you'll just merge them in step 3
5. Click **Create repository**

## 3. Upload the files
Easiest way, no git command line needed:
1. On your new repo's page, click **"uploading an existing file"**
2. Drag in `index.html` and `privacy-policy.html`
3. Commit directly to the `main` branch

Or with git, from this folder:
```bash
git init
git add index.html privacy-policy.html
git commit -m "Add privacy policy site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/lottery-results-policy.git
git push -u origin main
```

## 4. Enable GitHub Pages
1. In your repo, go to **Settings → Pages**
2. Under "Build and deployment" → **Source**, choose **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)** → Save
4. Wait ~1 minute, then refresh — GitHub shows your live URL at the top,
   something like:
   ```
   https://YOUR_USERNAME.github.io/lottery-results-policy/
   ```

## 5. Your Privacy Policy URL for the Play Console
```
https://YOUR_USERNAME.github.io/lottery-results-policy/privacy-policy.html
```
Paste this exact URL into:
- **Play Console → Policy → App content → Privacy policy**
- Also make sure the **Data safety** section's declared data types match
  what's listed in the policy (name, device identifiers, usage/analytics
  data, advertising ID)

## 6. Update the app to match
In your Flutter app's `modern_drawer.dart`, update the `policyUrl` passed
to `PrivacyPolicyScreen` to this same live URL, so the "View hosted
version" button opens the real page instead of the placeholder.

## Updating the policy later
Just edit `privacy-policy.html` (bump the "Last updated" date near the
top), commit, and push — GitHub Pages redeploys automatically within a
minute or two. No need to touch the Play Console URL again.
