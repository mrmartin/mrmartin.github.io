# Adding content to mrmartin.net

This repository, [mrmartin/mrmartin.github.io](https://github.com/mrmartin/mrmartin.github.io), is the source of <https://mrmartin.net>, Martin Kolar's personal website. Martin's other projects link to this file so that Martin, or an AI agent working on one of those projects, can add the project to the site.

If you're adding something:

1. Use [Deciding what to add](#deciding-what-to-add) to choose what kind of content it is, or whether to publish it at all.
2. Follow the how-to section for that kind of content.
3. Submit it as described in [Submitting changes](#submitting-changes).

## Deciding what to add

Work through these questions in order. Stop at the first one that gives an answer.

### 1. Should it be on the web at all?

Everything here is public and free to read. The site is open, and the repository is public on GitHub, so any file in the repository can be downloaded even if no page links to it. Deleting a file later doesn't remove it from the git history.

**If the information shouldn't be freely available on the web, don't add it to this repository at all.** That includes:

- credentials, API keys, passwords, tokens, private URLs, IP addresses and stream links
- personal information about other people, such as contact details, addresses, or photos of people who haven't agreed to be published
- material that is paid for or commercially confidential, such as client work, business plans, unreleased product details, or code and data that Martin sells
- research that isn't ready to be public, such as results planned for a paper that hasn't been submitted, or anything under embargo

If you're not sure, leave it out and ask Martin.

### 2. Is it Martin's own work?

Martin's own work is anything Martin made, plus anything Martin instructed an AI to make.

- **No:** someone else's website, article, tool, dataset, music or video goes on the **[Links](#editing-the-pages)** page (`links.md`). Links is only for other people's work. Never list Martin's own work there.
- **Yes:** go to question 3.

### 3. Does the work have its own web address?

The work has its own web address if there is a URL where the work itself can be used, seen or downloaded. For example:

- its own website or web page
- a GitHub repository or GitHub Pages site
- an API endpoint
- an app or shop listing
- a video, an album page, or a paper on arXiv
- a standalone page hosted on this site, like the games

A post on this site that only *describes* the work doesn't count.

- **Yes:** add an entry to **[Projects](#editing-the-pages)** (`projects.md`). This is required. Go to question 4 to choose the section. You can also write a post if there is something worth saying or showing, such as an announcement, screenshots or the story behind it. A post is optional.
- **No:** write a **[post](#writing-a-post)** that contains the work itself: the photos, the write-up, the results, the files. Don't add it to Projects or Links.

  *Example:* Martin repairs an old analogue camera and takes photos with it. That becomes a post with the photos and the story of the repair.

### 4. Which section of Projects?

Choose by the reason the work exists:

| Section | Use it when | Examples already listed |
|---|---|---|
| **My Work** | It makes money, or could make money: companies, products, services, commercial apps, patents | sharedproperty.co.uk, Subtitlecat, lkrobots |
| **My Research** | It explores a topic and could be published on arXiv or in a peer-reviewed venue: papers, datasets, methods, theses | the PhD, FFHQ features, publication lists |
| **My Hobbies** | Martin does it for enjoyment: music, books, art, games, things built for fun | the electro CD, The Hard Way, the games |

If more than one fits, choose the one that is the main reason the work exists. If that's unclear, ask Martin.

Inside each section, active projects come first. When a project stops working or its site goes offline, move its line to the `### Defunct` list at the end of the same section. If possible, point the link at a `web.archive.org` copy. Don't delete it.

### Post dates

**Every post is dated the day it's created**, even if the work was done earlier. Never backdate a post. If the work happened in the past, say so in the text ("I repaired this camera in 2019…"). The home page and the RSS feed are sorted by date, so a backdated post would be buried in the list and missed by feed readers.

### Quick reference

| What you're adding | Where it goes |
|---|---|
| Something that shouldn't be freely available on the web | Nowhere. Don't add it to the repository |
| Someone else's site, article, tool or media | `links.md`, under a matching `*` heading (create one if none fits) |
| Martin's work with its own web address that makes money or could | `projects.md` → My Work, plus an optional post |
| Martin's work with its own web address that could be published as research | `projects.md` → My Research, plus an optional post |
| Martin's work with its own web address, done for fun | `projects.md` → My Hobbies, plus an optional post |
| Martin's work with no web address of its own | A new post containing the work, dated today. Not in Projects or Links |
| An essay, idea or update that isn't a single piece of work | A new post, dated today |
| A browser game or web app that needs a home | A standalone HTML file on this site ([Adding a game](#adding-a-game-or-any-standalone-html-page)), then a Projects entry for it |
| A change to Martin's bio or motto | Edit `about.md` or `motto.md` |

## Submitting changes

Changes reach <https://mrmartin.net> only through a pull request that Martin reviews and merges. **Don't push to `master`**, because anything pushed there goes live within a few minutes.

1. Clone `https://github.com/mrmartin/mrmartin.github.io` and create a new branch from `master`.
2. Make the change by following the how-to sections below. Before you add an entry, check that it isn't already on the site, and update the existing entry if it is.
3. Optionally, [preview the site locally](#previewing-locally) to check that it builds and looks right.
4. Open a pull request against `master`. Say what you added, where you put it, and which rule from [Deciding what to add](#deciding-what-to-add) decided that. If you skipped something under rule 1, say so in the description without including the details.

## How the site works

This site is a [Jekyll](https://jekyllrb.com/) blog using the **minima** theme. GitHub Pages builds it automatically whenever `master` changes, and it is served at <https://mrmartin.net> (set by `CNAME`). You don't need to build anything yourself.

### How the site is laid out

| Path | What it is | Public URL |
|---|---|---|
| `index.html` | Home page: lists every post, newest first | `/` |
| `_posts/` | Blog posts, one Markdown file each | `/<categories>/YYYY/MM/DD/<slug>.html` |
| `about.md` | "About Me" page | `/about/` |
| `projects.md` | "Projects": Martin's own work that has its own web address (work, research, hobbies), with defunct ones grouped at the end of each section | `/projects/` |
| `links.md` | "Links": a categorised list of other people's sites, reading and tools | `/links/` |
| `motto.md` | "Hi, I'm Martin": a personal statement | `/motto/` |
| `feed.xml` | RSS feed of the 10 latest posts | `/feed.xml` |
| `*.html` in root (`letter-hunt.html`, `petal-paths.html`, `trex-secret-friends.html`) | Standalone browser games, served as-is | `/letter-hunt.html` etc. |
| `images/` | Images used in posts and pages | `/images/<file>` |
| `files/`, root `*.pdf`, `*.zip` | Downloadable documents (theses, papers, datasheets) | `/files/<file>`, `/<file>` |
| `_includes/` | Reusable HTML snippets: `head.html` (overrides minima's `<head>` to add MathJax), `analytics.html`, `video.html` | not published |
| `css/main.scss` | Old theme variables. **Not loaded:** minima 2.5 uses `/assets/main.css` (see "Site settings and styling") | `/css/main.css` |
| `_config.yml` | Site title, description, URL, Markdown settings | not published |

The header menu is generated by minima. It lists every page that has a `title:` in its front matter, in alphabetical order of file name (about, links, motto, projects). Posts don't appear in the menu. They appear on the home page.

> **Everything in the repository is public.** GitHub Pages publishes every file that doesn't start with `_` or `.`, including archives such as `unpublished.7z`. The repository itself is public too, so a file is visible on GitHub even if Jekyll doesn't publish it.

## Writing a post

1. Create a file in `_posts/` named `YYYY-MM-DD-short-slug.markdown` (or `.md`), using **today's date** (see [Post dates](#post-dates)).
   - Use lowercase letters, digits and hyphens in the slug. Don't use spaces, `?`, `#` or `%`, because the slug becomes the URL.
   - The date in the file name should match the `date:` in the front matter.
2. Start the file with front matter:

   ```yaml
   ---
   layout: post
   title:  "Your Title Here"
   date:   2026-11-05 10:00:00 +0000
   categories: science space
   ---
   {% include analytics.html %}

   First paragraph of the post...
   ```

   - `categories` are **separated by spaces, not commas**. Each category becomes a folder in the URL, so `science space` gives `/science/space/2026/11/05/short-slug.html`. A comma becomes part of the URL (`/science,/space/...`). For a category of two or more words, use a hyphen: `data-science`.
   - Add `math: true` if the post contains maths (see [Maths](#maths)).
   - A future `date` hides the post until that time. GitHub Pages only rebuilds on push, so the post appears at the first push after that date.
   - The `analytics.html` include line is a habit kept from older posts. See the notes at the end.
3. Write the body in Markdown ([kramdown](https://kramdown.gettalong.org/quickref.html) flavour):
   - Headings `##`, lists, links `[text](url)`, footnotes `text[^1]` with `[^1]: note`.
   - Code blocks use fences (```` ```python ````) or Liquid: `{% highlight php %} … {% endhighlight %}`.
   - Add classes or attributes with `{: target="_blank" rel="noopener"}` after a link or paragraph.
4. Commit and push. The post appears on the home page and in the RSS feed.

**Changing a published post's date, categories or file name** changes its URL, and old links to it stop working. To keep them working, add the old URL to the front matter:

```yaml
redirect_from: /old/category/2018/12/08/Old-Name.html
```

Several posts already use this. It relies on the `jekyll-redirect-from` plugin, which is enabled in `_config.yml`.

**Drafts:** files in `_posts/` without a date prefix (like the two `.txt` files there now) are ignored. For drafts that are cleaner to manage, put them in a `_drafts/` folder (preview with `jekyll serve --drafts`). Remember that the repository is public, so drafts can still be read on GitHub.

### Links

These work the same way in posts and pages.

```markdown
[Subtitlecat](https://subtitlecat.com)                        external link
<https://mrmartin.net>                                        bare URL as a link
[About me]({{ "/about/" | relative_url }})                    another page on this site
[Petal Paths]({{ "/petal-paths.html" | relative_url }})       a game or other file in the root
[My Plan]({% post_url 2024-07-15-my-plan-for-contribution %}) another post (Jekyll checks it exists)
[Section below](#links)                                       heading on the same page
[Opens in new tab](https://example.com){: target="_blank" rel="noopener"}
```

- To link to a post, use `post_url` with the file name minus the extension. Don't copy the URL, because it depends on the categories and changes if they change. If the target post doesn't exist, the build fails, which catches broken links before they go live.
- Heading anchors are the heading text in lowercase with hyphens, so `## My Big Idea` becomes `#my-big-idea`.
- For a link that is used many times, use a reference link: write `[my GitHub][gh]` in the text and `[gh]: https://github.com/mrmartin` anywhere in the file.

### Images

1. Put the image in `images/`. Use a name without spaces, and resize large photos first (a width of about 1600 px is plenty, since the content column is 800 px).
2. Embed it with `relative_url`:

```markdown
![A bridge over the Vltava]({{ "/images/bridge.jpg" | relative_url }})
```

- The text in `[ ]` is the alt text, which screen readers announce and browsers show if the image fails to load. Describe the image there.
- Add a caption by putting an italic line directly below the image: `*Prague, 2016*`.
- To control the size, add an attribute: `{: width="400"}` on the line after the image.
- To make the image clickable and open full size, wrap it in a link: `[![alt]({{ "/images/x.jpg" | relative_url }})]({{ "/images/x.jpg" | relative_url }})`.
- For several images in a row, or for full control, use HTML: `<img src="{{ "/images/x.jpg" | relative_url }}" alt="…" width="300">`.
- An image hosted elsewhere works with a plain URL: `![alt](https://example.com/pic.png)`. It breaks if that site removes the image, so keeping a copy in `images/` is safer.

Older posts use `{{ site.url }}/images/...`. That also works, but it always points to the live site, even when you preview locally. Use `relative_url` in new posts.

### Downloadable files

Put PDFs and other documents in `files/` and link to them like any other link:

```markdown
[Download the paper (PDF)]({{ "/files/my-paper.pdf" | relative_url }})
```

### Video

Put the `.mp4` file in the repository (keep it small, because GitHub warns about files over 50 MB) and embed it with HTML:

```html
<video controls width="640"><source src="{{ "/movie.mp4" | relative_url }}" type="video/mp4"></video>
```

For anything large, upload it to YouTube and use a link.

### Maths

1. Add `math: true` to the post's front matter. This makes `_includes/head.html` load MathJax on that page only.
2. Write all maths between **double** dollar signs. kramdown ignores single `$` (so "150$" stays plain text), and the result depends on where `$$` sits:
   - Inside a sentence, it's inline: `the constant $$G$$ is tiny`.
   - On its own lines, separated by blank lines, it's a display equation:

     ```markdown
     $$
     E = mc^2
     $$
     ```

kramdown can read `|` inside maths as a table column separator, even in a normal paragraph, and the maths then doesn't render. Write `\vert` instead (for example `$$\vert x\vert$$`).

## Adding a game (or any standalone HTML page)

Hosting a page here gives a piece of work its own web address, so it goes in Projects. The three games follow this pattern:

1. Put a self-contained file such as `my-game.html` in the repository root. Use a single file with inline CSS and JS and no front matter. Jekyll copies it unchanged to `/my-game.html`.
2. Add it to `projects.md` in the right section (games usually go in My Hobbies):

   ```markdown
   - [My Game]({{ "/my-game.html" | relative_url }}), one-line description
   ```
3. Optionally, write a post dated today with `categories: games` that describes the game and links to it:

   ```markdown
   [Play My Game fullscreen]({{ "/my-game.html" | relative_url }}){: target="_blank" rel="noopener"}
   ```

If you start the HTML file with `---` front matter, Jekyll processes it as a template, and `{{ }}` or `{% %}` sequences in the JavaScript will break it. Leave the front matter off.

## Editing the pages

All four pages use `layout: page` and a `permalink:`. Edit the Markdown directly.

- **About (`about.md`)**: written like a paper (Abstract, Motivation, Hypothesis, Method, Results, Prior Work, Supplementary Material). Add to the matching section. "Results" and "Supplementary Material" still contain placeholder notes to replace with real content.
- **Projects (`projects.md`)**: Martin's own work that has its own web address (see [Deciding what to add](#deciding-what-to-add)), in three sections: `## My Work`, `## My Research` and `## My Hobbies`. Active projects come first. Projects that no longer run go under a `### Defunct` heading at the end of their section:

  ```markdown
  ## My Work

  - [New thing](https://example.com), one-line description
  - Unlinked project, one-line description

  ### Defunct

  - [Old thing](https://web.archive.org/web/2020/https://old.example.com), one-line description
  ```

  When a project shuts down, move its line into that section's `### Defunct` list (create the heading if the section doesn't have one yet). If possible, point the link at a `web.archive.org` copy.
- **Links (`links.md`)**: other people's sites, as a two-level bullet list. Add a line under the right heading:

  ```markdown
  * Section name
    - [Link text](https://example.com) short description
  ```

  Start a new section with a new top-level `* Heading`. Martin's own work never goes here. It goes on Projects or in a post.
- **Motto (`motto.md`)**: free prose.

### Adding a new page

Create `something.md` in the root:

```yaml
---
layout: page
title: Something
permalink: /something/
---
```

The page appears in the header menu automatically. To control which pages appear in the menu, and in what order, add this to `_config.yml`:

```yaml
header_pages:
  - about.md
  - projects.md
  - links.md
  - motto.md
```

## Site settings and styling

- `_config.yml`: `title`, `description` (shown in the footer and the feed), `email`, `url`. Restart `jekyll serve` after changing it.
- **Styling:** minima 2.5 only loads `/assets/main.css`, so `css/main.scss` currently has no effect. To customise the styling, create `assets/main.scss` with this content and add your own rules below it:

  ```scss
  ---
  ---
  $brand-color: #2a7ae2;   // set variables before the import
  @import "minima";
  ```
- To override any part of the theme's HTML (header, footer, `<head>`), copy the file from the [minima 2.5 repository](https://github.com/jekyll/minima/tree/v2.5.1/_includes) into `_includes/` or `_layouts/` and edit it.

## Previewing locally

```bash
bundle install
```

```bash
bundle exec jekyll serve
```

Then open <http://localhost:4000>. On Ruby 3+ you may also need `bundle add webrick`.

## Notes

- **Analytics:** `_includes/analytics.html` (and the copy pasted into `index.html`) uses Google Universal Analytics (`UA-…`), which Google shut down in July 2023. It no longer collects data. Either switch to a GA4 tag or another tool, or remove the includes.
- `_includes/video.html` is not used anywhere.
