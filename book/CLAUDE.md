# Book Authoring Guide

This is a Quarto book template. It ships with two placeholder chapters written in
lorem ipsum so the structure, theme, and image-embedding pattern are all visible
and ready to be replaced with real content.

## Chapter Content Map

- `index.qmd` — Preface (unnumbered)
- `ch01-chapter-one.qmd` — Chapter One (placeholder)
- `ch02-chapter-two.qmd` — Chapter Two (placeholder)

## Current Status

- [x] Theme (light/dark, Aalto branding) set up
- [x] Two placeholder chapters demonstrating the full template pattern
- [ ] Real content — replace the placeholder chapters with your own material

## Chapter Template — Must Be Followed Consistently

Every chapter (except the preface) should follow this structure so the book
reads consistently:

1. **Front matter** — just a `title:` field.
2. **Draft-warning callout** — flags the chapter as not yet reviewed, remove once finalized:
   ```
   ::: {.callout-warning}
   ## Draft — Not Yet Reviewed
   ...
   :::
   ```
3. **Intro paragraph** — one or two sentences framing the chapter.
4. **Learning-outcomes callout**:
   ```
   ::: {.callout-note}
   ## Learning Outcomes
   - ...
   :::
   ```
5. **Body sections** — one or more `##` headings with prose, bullet lists, and
   images as needed. Embed images with Quarto's standard Markdown syntax and
   always include `fig-alt` for accessibility:
   ```
   ![Caption](images/chXX/your-image.png){fig-alt="Description for screen readers"}
   ```
   Use `width=` to constrain size when useful: `{fig-alt="..." width=120}`.
6. **Discussion-activity callout**:
   ```
   ::: {.callout-tip}
   ## Discussion Activity
   1. ...
   :::
   ```
7. **Practical Exercises** — a `## Practical Exercises` section with numbered
   sub-exercises, each naming a tool: replace `[Example Tool](https://example.com)`
   with tools relevant to your subject matter.
8. **References** — a plain numbered `## References` list (this template does
   not use Quarto's native citation/crossref system).

## How to Expand the Book

1. Add a new `.qmd` file following the template above.
2. Add its filename to the `chapters:` list in `_quarto.yml`, in the order it
   should appear.
3. If it has images, put them in `images/chXX/` and reference them with a
   relative path from `book/`.

## Theme / Layout (kept as-is from the source template)

- Light theme: `custom-light.scss` (layered over Bootstrap's `cosmo`)
- Dark theme: `custom-dark.scss` (layered over Bootstrap's `darkly`)
- Palette: Aalto blue `#46A5FF`, red, yellow, and grayscale accents
- Typography: Inter for body text, Fira Code/Consolas for monospace
- Sidebar logo: `aalto-logo-black.png` (light) — `aalto-logo-white.png` is
  also included for a future dark-mode logo swap, though it isn't wired up
  in `_quarto.yml` yet

## Build Commands

Run from the repository root (one level above `book/`):

```bash
quarto preview book/
quarto render book/     # output: book/_book/index.html
```

`book/_book/` and `book/.quarto/` are generated output/cache directories —
safe to delete, and should be excluded from version control if you initialize
a git repository.
