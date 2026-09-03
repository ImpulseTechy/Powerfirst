# Power First

Practical power supply design for B.Tech students and makers.

Two static pages, no build step, no dependencies.

| Path | What it is |
|---|---|
| `index.html` | **Power Supply Picker** — works out the right topology and parts for a project, shows every calculation, and states what it assumed and did not check |
| `book/index.html` | **Power First** — the free online edition of the book |
| `og.png` | Social share card |

Built by [Yogesh Bawane](https://www.linkedin.com/in/yogesh-bawane/) ·
[YouTube](https://www.youtube.com/@ImpulseTech) ·
[Instagram](https://www.instagram.com/impulsetechy/)

---

## Before the first deploy

Both HTML files contain the placeholder `REPLACE-WITH-YOUR-DOMAIN`. Link
previews on WhatsApp, LinkedIn and Instagram need an absolute URL, so set this
once you know your Vercel address:

```bash
grep -rl 'REPLACE-WITH-YOUR-DOMAIN' . --include='*.html' \
  | xargs sed -i 's|https://REPLACE-WITH-YOUR-DOMAIN|https://your-domain.vercel.app|g'
```

macOS: use `sed -i ''` instead of `sed -i`.

## Deploying

Vercel picks this repo up with no configuration:

- **Framework preset:** Other
- **Build command:** leave empty
- **Output directory:** `.`

Every push to `main` redeploys.

## Swapping which page is the homepage

The picker is currently the site root. To make the book the homepage instead:

```bash
mkdir -p picker && git mv index.html picker/index.html && git mv book/index.html index.html
```

## Checks after deploying

- Open on a phone — text readable without pinching, no sideways scrolling
- Look for `₹`, `µ` and `°C`; if they show as `â‚¹` the charset meta is missing
- Paste the URL into WhatsApp — the share card should appear
- Switch the phone to dark mode; the pages follow it

## Editing

Plain HTML, CSS and JavaScript in one file each. No framework, no toolchain.
Open, edit, commit, push.
