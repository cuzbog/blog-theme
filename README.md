# personal-page-system — Hugo theme

A Hugo port of the `personal-page-system` design bundle (bgdn.eu): a one-screen visit card whose paragraph *is* the navigation, plus quiet subpages for films, writing, software, research, CV, and about.

## Design rules (enforced by the theme)

- White background, generous margins, no shadows, no card chrome.
- Two typefaces: **Charter** (serif) for prose and titles, **DM Mono** for meta and labels.
- Color appears only as inline-link underlines, one per category:
  - film `#B83A3A`, writing `#C46B2A`, software `#3A4F5C`, research `#1A4F82`.
- Landing is vertically centered, no scroll. Subpages are top-aligned with a `← back` link.
- Max content width 640px; horizontal padding `clamp(32px, 8vw, 160px)`.

## Pages

| Section | Layout | Source |
|-|-|-|
| Home | `layouts/index.html` | `content/_index.md` |
| About | `_default/single.html` | `content/about.md` |
| Films | `films/list.html` | `content/films/_index.md` + per-item `.md` |
| Writing | `writing/list.html` | `content/writing/_index.md` + per-item `.md` |
| Software | `software/list.html` | `content/software/_index.md` + per-item `.md` |
| Research | `research/list.html` | `content/research/_index.md` (publications in front matter) |
| CV | `cv.html` | `content/cv.md` (sections in front matter) |

## Home prose & link shortcode

The intro paragraph lives in `content/_index.md` body. Use the `link` shortcode for category-coloured inline links:

```
{{</* link to="/films/" color="film" */>}}films{{</* /link */>}}
```

Valid `color` values: `film`, `writing`, `software`, `research`.

## Run

```bash
brew install hugo            # if needed
cd site
hugo server -D               # dev server
hugo                         # build to ./public
```
