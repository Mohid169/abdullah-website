# Abdullah Ahmad

A static personal website, using the supplied HTML and CSS. No build or dependencies are required.

## Preview

Open `index.html` in a browser, or run `python3 -m http.server 8080` and visit http://localhost:8080.

## Publish with GitHub Pages

1. Create a public GitHub repository named `abdullah-website`.
2. Upload `index.html` and `.nojekyll` to the repository's `main` branch.
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**, choose **main** and **/(root)**, and click **Save**.
5. GitHub will show the published URL in the Pages settings once deployment finishes: `https://YOUR-USERNAME.github.io/abdullah-website/`.

Official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

Alternatively, once `gh auth login --hostname github.com` succeeds, publish this folder using:

```sh
git init -b main
git add index.html .nojekyll .gitignore README.md
git commit -m "Add Abdullah Ahmad personal website"
gh repo create abdullah-website --public --source=. --remote=origin --push
gh api --method POST repos/{owner}/{repo}/pages -f 'source[branch]=main' -f 'source[path]=/'
gh api repos/{owner}/{repo}/pages --jq .html_url
```

## Edit

Update `index.html` and commit the changes to `main`; GitHub Pages publishes updates automatically.

To add a portrait, put `your-photo.jpg` beside `index.html` and replace `<div class="photo-box">Your photo here</div>` with `<img src="your-photo.jpg" alt="Abdullah Ahmad">`.
