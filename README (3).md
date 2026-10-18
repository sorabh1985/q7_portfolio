# Sorabh's portfolio

A static site: plain HTML and one stylesheet, no build step.

```
index.html      Home: name, role, about, data sheet
projects.html   Projects
contact.html    Contact details
style.css       Colours, fonts and layout (edit the :root block to restyle)
```

## Before you publish

1. **Replace the email address.** It appears in all three pages as `your.email@example.com`:
   ```bash
   sed -i 's/your\.email@example\.com/YOUR-REAL-ADDRESS/g' *.html
   ```
2. **Check the details are ones you want public.** The home page lists your role, employer and skills. Edit or remove anything you would rather not publish.
3. **Edit the projects** in `projects.html`. Only list work you are free to share.
4. **Add your full name** if you want it shown. Search for `Sorabh` in the HTML files.

## Preview locally

```bash
python3 -m http.server 8000
```
Open http://localhost:8000

## Publish on GitHub Pages

1. Create an empty repo on GitHub. Name it `sorabh1985.github.io` to get the address `https://sorabh1985.github.io/`, or use any other name to get `https://sorabh1985.github.io/<repo-name>/`.
2. Push the files:
   ```bash
   git init
   git branch -M main
   git add .
   git commit -m "Add portfolio site"
   git remote add origin https://github.com/sorabh1985/<repo-name>.git
   git push -u origin main
   ```
3. On GitHub open **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, then choose branch `main` and folder `/ (root)`, and save.
4. Wait a minute or two. The site address appears at the top of the Pages settings.

Every `git push` to `main` updates the site.

## Add a page

1. Copy `contact.html` to a new file, for example `blog.html`.
2. Change the `<title>`, the description, the heading and the content.
3. In the `<nav>` of **every** page, add `<li><a href="blog.html">Blog</a></li>`.
4. In the new page, move `aria-current="page"` to its own nav link.

Keep links relative (`projects.html`, not `/projects.html`) so the site works from a repo sub-path.
