# Updating your website

Your site rebuilds and republishes itself every time you save a change on GitHub.
You do not need to install anything. Edit the files in your browser, and the site
is live about two minutes later.

**How to edit a file on GitHub:** open the file in your repository, click the
pencil icon (✏️) at the top right, make your change, then scroll down and click
**Commit changes**.

---

## Add a new paper

Open `data/papers.yaml`. There are three lists in this file: `working_papers`,
`articles` (peer-reviewed), and `book_reviews`. Copy an existing block, paste it
into the right list, and change the values. Keep the indentation exactly as it is.

```yaml
  - title: "Your Paper Title"
    authors: ["Tatiana Paula da Cruz"]
    status: "working paper"
    dissertation: false          # true adds the highlighted "dissertation chapter" card
    note: "Presented at MPSA, 2027."   # optional; delete the line if unused
    summary: >-
      A few sentences. Keep every line indented under `summary:`.
    pdf: "files/your-paper.pdf"  # optional; see below
    link: ""                     # optional external link (DOI, SSRN)
```

**Status options:** `work in progress`, `working paper`, `under review`,
`revise and resubmit`, `accepted`, `published`.

### Attach a PDF to a paper

1. Go to the `static/files/` folder in your repository.
2. Click **Add file → Upload files** and upload the PDF.
3. In `data/papers.yaml`, set `pdf: "files/your-file-name.pdf"`.

The paper title then becomes the download link.

## Mark a paper as published

In `data/papers.yaml`, move the entry from `working_papers` into `articles`, then
set `status: "published"` and fill in `venue`, `volume`, `year`, and `link`.

## Update your bio

The bio paragraphs are in `content/_index.md`, below the `---` lines. Write in
plain Markdown: blank line between paragraphs, `*text*` for italics,
`[words](https://url)` for a link.

Your name, title, tagline, email, office, and research-interest tags live in
`hugo.yaml` under `params:`.

## Add a teaching entry

Open `data/teaching.yaml` and add a block at the position you want it to appear:

```yaml
- course: "PS 999: Course Name"
  role: "Instructor"
  institution: "University of Wisconsin–Madison"
  term: "Fall 2027"
```

## Add an award, a talk, or a piece of writing

Same pattern, in these files:

| What | File | Appears on |
|---|---|---|
| Awards and grants | `data/awards.yaml` | CV |
| Conference presentations | `data/talks.yaml` | CV |
| Degrees | `data/education.yaml` | Bio sidebar and CV |
| Blog posts, interviews, op-eds | `data/writing.yaml` | (currently unused) |

Any section whose file is empty disappears from the page automatically.

## The pages and where things live

The site has five tabs. Each one is a file in `content/`, but the content itself
comes from `data/`:

| Tab | Shows |
|---|---|
| **Bio** (`/`) | Your bio, the sidebar (contact, education, interests), and the Cataguases gallery |
| **Research** (`/research/`) | Working papers and peer-reviewed articles |
| **Teaching** (`/teaching/`) | Courses |
| **CV** (`/cv/`) | Education, awards, talks, and the PDF download |
| **Contact** (`/contact/`) | Email, office, links |

To rename or reorder the tabs, edit the `menu:` block in `hugo.yaml` — `weight`
sets the order.

## Change the Cataguases gallery

Everything is in `data/gallery.yaml`: an `intro` paragraph and a `photos` list.
To add a photo, upload it to `static/images/cataguases/` and add a block:

```yaml
  - image: "images/cataguases/your-file.jpg"
    alt: "A plain description for screen readers and search engines."
    caption: "What this is."
    credit_text: "My photograph"   # or "Photographer, CC BY-SA 4.0"
    credit_url: ""                 # link to the source, if it isn't yours
```

Leave `credit_url` empty and the credit shows as plain text; leave `credit_text`
empty too and no credit line appears. Photos are shown about 380 pixels wide, so
save them around 760 pixels wide.

## Update your CV

Upload the new PDF to `static/files/` and name it exactly `cv.pdf`, replacing the
old one. The nav link and the CV button both point at that filename, so nothing
else needs changing.

## Change your photo

Replace `static/images/photo.jpg` with a new file using that same name. It sits in
the Bio sidebar as a full upright portrait — nothing is cropped — so a tall
(portrait-shaped) photo works best. Save it about 600 pixels wide so it stays sharp
on high-resolution screens.

If your new photo is a different shape, tell your assistant and they will adjust
the `width` and `height` on the image so the page doesn't jump while it loads.

> Four of the five gallery photos come from Wikimedia Commons under CC BY-SA
> licences, which require the photographer and licence stay credited. Keep their
> `credit_text` and `credit_url` intact, or replace the photo entirely.

## Preview changes before they go live

Optional. If you want to see a change before the world does, install Hugo
(`brew install hugo`), then from the repository folder run:

```bash
hugo server
```

Open <http://localhost:1313>. The preview reloads as you type.

## If the site doesn't update

Open the **Actions** tab in your repository. A red ✗ means the build failed —
click it to see why. The most common cause is a YAML indentation slip: every
entry in a `data/` file starts with `- ` and nested lines line up underneath.
