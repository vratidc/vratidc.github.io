# IMXD Lab website

Source for **https://imxd.in**, the website of the IMXD Lab, IDC School of Design, IIT Bombay.

It is a [Jekyll](https://jekyllrb.com/) site built on the Minimal Mistakes theme and
published with GitHub Pages. Every push to `master` rebuilds the live site.

---

## 1. Run it on your computer

You need Ruby and Bundler installed. Then, from this folder:

```sh
bundle install                      # first time only
bundle exec jekyll serve --livereload
```

Open http://localhost:4000. With `--livereload` the page refreshes by itself when you
save a file. (`npm run dev` / `npm run hotdev` do the same thing.)

If the server stops with an error like *"hash representation was changed during
iteration"*, just stop it (Ctrl+C) and start it again.

---

## 2. What is where

### Top level: folders

| Path | What it is |
|---|---|
| `_pages/` | All standalone pages, including the homepage (About, Contact, Openings, showcases, …). See below. |
| `openings/` | One file per internship opening. See `openings/_HOW-TO.md`. |
| `_projects/` | One file per project (`/projects/...`) |
| `_people/` | One file per person (`/people/...`), in `Faculty/`, `Team/`, `Students/`, `Previous Researchers/` |
| `_publications/` | One file per publication (`/publications/...`) |
| `_activities/` | Workshops, talks, visits, awards, defences (`/activities`) |
| `_posts/` | Older blog/update posts (`/updates/`) |
| `_notes/` | Notes collection (test content) |
| `_data/` | Lists used across the site: `navigation.yml` (top menu), `courses.yml`, `pastmembers.yml`, `pastinterns.yml`, `updates.yml`, `ui-text.yml` |
| `_layouts/` | Page templates (what a page looks like) |
| `_includes/` | Reusable pieces used inside templates (header, footer, cards, …) |
| `_sass/minimal-mistakes/` | Styles. Page-specific files such as `_openings.scss`, `_people.scss`, `_footer.scss` |
| `assets/` | Images (`assets/img/...`), documents, fonts, CSS and JS |
| `_internal-docs/` | Internal diagrams (IA, Jekyll flowchart). Kept in the repo, **not** published. |
| `.github/` | GitHub settings |

Folders starting with `_` are special to Jekyll: they are read while building, but not
copied to the site as-is.

### Top level: files (these must stay here)

These tools only look for their files in the root folder, so they can't be moved
into a subfolder.

| File | What it is | Edit it? |
|---|---|---|
| `_config.yml` | Site settings: title, menus, collections, defaults. Restart the server after editing. | Yes, carefully |
| `README.md` | This guide (not published on the site) | Yes |
| `CNAME` | Custom domain (imxd.in) for GitHub Pages | No |
| `Gemfile`, `Gemfile.lock` | Ruby packages Jekyll needs | Rarely |
| `minimal-mistakes-jekyll.gemspec` | Theme package description; the `Gemfile` reads it | No |
| `package.json`, `package-lock.json` | npm scripts (`npm run dev`, JS build) | Rarely |
| `banner.js` | Used by `npm run build:js` to stamp the theme's JS file | No |
| `Rakefile` | Theme's developer tasks | No |
| `staticman.yml` | Settings for Staticman comments (comments are currently off) | No |
| `LICENSE` | Theme licence | No |
| `shiva_gs_test.html` | Test page (`/shiva_gs_test.html`), kept on purpose | – |
| `.gitignore`, `.gitattributes`, `.editorconfig`, `.travis.yml` | Git and editor settings (hidden files) | No |

### Inside `_pages/`

Each page sets its own address with `permalink:` at the top, so **the folder a page is
in never changes its URL**.

| Folder | Pages | URLs |
|---|---|---|
| `_pages/main/` | index (homepage), about, activities, blog, contact, courses, openings, people, projects, publications, student-projects, 404 | `/`, `/about`, `/activities`, `/updates/`, `/contact`, `/courses`, `/openings`, `/people`, `/projects`, `/publications`, `/student-projects`, `/404.html` |
| `_pages/showcases/` | Course showcases `de677-showcase-2021` … `2026`, `de712-showcase-2024` … `2026` | Same as the file name, e.g. `/de677-showcase-2026` |
| `_pages/project-pages/` | manhole-project1, socialxrparty, unity-ar, artwo | `/manhole-project`, `/socialxrparty`, `/unity-ar`, `/artwo/` |
| `_pages/apps/` | archeck (AR Check app privacy policy) | `/apps/archeck/policy` |
| `_pages/internal/` | internalsites | `/sites` |
| `_pages/archive/` | indexold, scholar-remote (old versions, kept for reference) | `/indexold`, `/scholar-remote-old/` |
| `_pages/taxonomy/` | `categories/` and `tags/` archive pages | `/categories/<name>/`, `/tags/<name>/` |

---

## 3. Where things used to be (reorganised Nov 2026)

Every URL stayed the same; only the files moved.

| Before | Now |
|---|---|
| `index.md`, `about.md`, `activities.md`, `blog.md`, `contact.md`, `courses.md`, `openings.md`, `people.md`, `projects.md`, `publications.md`, `student-projects.md`, `404.md` (all at the top level) | `_pages/main/` |
| `de677-showcase-*.md`, `de712-showcase-*.md` | `_pages/showcases/` |
| `manhole-project1.md`, `socialxrparty.md`, `unity-ar.md`, `artwo.md` | `_pages/project-pages/` |
| `archeck.md` | `_pages/apps/` |
| `internalsites.md` | `_pages/internal/` |
| `indexold.md`, `scholar-remote.md` | `_pages/archive/` |
| `categories/*.md`, `tags/*.md` | `_pages/taxonomy/categories/`, `_pages/taxonomy/tags/` |
| `IMXD Docs/` | `_internal-docs/` (now private) |
| `index.html` (empty duplicate of the homepage) | Removed; the homepage is `_pages/main/index.md` |
| `aframe360.txt` (old code snippet) | Removed |
| `docs/` (the theme's own documentation) | Removed |

Old versions of anything removed are still in the git history.

---

## 4. Common tasks

**Add or close an internship opening:** edit a file in `openings/`. The Openings page
builds itself from those files, and openings close by themselves after their deadline.
Full guide: `openings/_HOW-TO.md`.

**Add an activity** (workshop, talk, visit, award, …): copy a recent file in
`_activities/` (e.g. `visit-kulfi-collective2026.md`), change the details, and put its
photos in `assets/img/activities/...`. The card thumbnail is a 200×200 image named
`icon-pub-<name>.jpg`.

**Add a project:** copy a file in `_projects/` and put its images in
`assets/img/projects/<ProjectName>/`. Course work goes in `_projects/course-outcomes/`;
retired projects are in `_projects/Inactive/`.

**Add a person:** copy a file in the right `_people/` subfolder and add their photo
under `assets/img/people/`.

**Add a publication:** copy a file in `_publications/`.

**Change the top menu:** edit `_data/navigation.yml`.

**Add a new standalone page:** create it in the matching `_pages/` subfolder and give it
a `permalink:` (e.g. `permalink: /my-page`). Without a permalink its URL would depend on
the folder.

---

## 5. Good to know

- Styles for one page go in that page's file in `_sass/minimal-mistakes/`. Avoid
  changing shared rules (like `#page-title`), which affect every page.
- Images: keep them reasonably small (about 1600px wide for photos) so pages load fast.
- After editing `_config.yml`, restart the local server; it doesn't reload that file.
- Check the page on a phone width too; most pages have mobile-specific styles.
