# franciscoperezarce.com — site source

Plain HTML/CSS recreation of the Wix site at
https://franciscoperezarce.wixsite.com/francisco-perez-arce

## Structure

    index.html          # Homepage (hero with brutalist background)
    research.html       # Working papers
    news.html           # Upcoming events
    publications.html   # Full publications list
    contact.html        # Address & email
    blog.html           # UAS materials / blog post stubs
    cv.html             # Big "CV" link → Dropbox PDF
    css/styles.css      # All styling

No build step. No JS framework. No dependencies.

## Local preview

    cd website
    python3 -m http.server 8000

Then visit http://localhost:8000

## Deploying to GitHub Pages

1. Create a repo on GitHub (e.g. `franciscoperezarce.github.io` for a user
   site, or any repo name for a project site).
2. Push these files to the `main` branch.
3. In the repo's **Settings → Pages**, set the source to `Deploy from a
   branch` → `main` / `(root)`.
4. Site goes live at `https://<username>.github.io/<repo>/` (or
   `https://<username>.github.io/` if the repo is named that way).

For a custom domain, add a `CNAME` file at the root with your domain
(e.g. `franciscoperezarce.com`) and configure DNS to point at GitHub.

## Images

The site currently hot-links the original images from the Wix CDN
(`static.wixstatic.com/...`). Those URLs are public and stable, so the
site renders correctly out of the box. If you want the site to be
fully self-hosted, download the three main images:

* Background (brutalist interior):
  `https://static.wixstatic.com/media/e48f7f_e3622eef1cb646fda3a1598dcc807bcc~mv2.jpg`
* Profile photo (logo, IMG_1596_edited.jpg):
  `https://static.wixstatic.com/media/e48f7f_be5bbe8f2321465eacd185bcb6180eed~mv2.jpg`
* Speaking-podium photo (homepage card):
  `https://static.wixstatic.com/media/e48f7f_a3aebc4762b049a8a655a68ad3b35c11~mv2.jpeg`

…save them into `assets/`, and replace the URLs in `index.html`,
`css/styles.css`, and the page headers with the local paths.

## Editing nav links

The nav is duplicated in each page (no JS includes). To rename or
reorder, search-and-replace across the seven HTML files.

## Notes

* Original Wix typo "Center for Economic *Rearch* (CESR)" was corrected
  to "Center for Economic *Research* (CESR)" on the homepage. Revert if
  you preferred it as written.
* The CV link points to your Dropbox PDF
  (`CV_202412.pdf`). Update the URL in `cv.html` (and the homepage card
  link in `index.html`, which currently routes to `cv.html`) when you
  rotate the file.
