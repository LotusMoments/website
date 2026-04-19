# Claude Code Guidelines

## Git

- **Never commit without explicit permission.** Always show the work and wait for the user to say "commit" (or similar) before staging or committing anything.
- **Never push without explicit permission.** A commit instruction does not imply a push. Wait for a separate push instruction.
- **No co-author lines.** Do not add `Co-Authored-By` or any Claude/Anthropic attribution to commit messages.

---

## Project: Lotus Moments website

Jekyll marketing website for holistic massage practitioner **Emine Bayyurt** — hosted on GitHub Pages at **lotusmoments.nl**.

### Tech stack

- **Jekyll** (static site generator), Ruby, Bundler
- **Custom CSS** — no theme, single file: `assets/css/style.css`
- **Plugins:** `jekyll-seo-tag`, `jekyll-sitemap`
- **Analytics:** GoatCounter (`https://lotus-moments.goatcounter.com/count`)
- **Booking:** Calendly (`https://calendly.com/emine314/30min`)
- **Deployment:** GitHub Actions → GitHub Pages (push to `main` triggers deploy)
- **Custom domain:** `lotusmoments.nl` (CNAME file)
- **Local dev:** `bundle exec jekyll serve` → http://localhost:3000

### Design system

CSS variables defined in `:root` in `assets/css/style.css`:

| Variable | Value | Use |
|---|---|---|
| `--bg` | `#f5f0e8` | Warm beige background |
| `--text` | `#3f3226` | Dark brown body text |
| `--text-muted` | `#6b5a4b` | Muted brown |
| `--accent` | `#cfa16f` | Warm gold/tan (primary accent) |
| `--accent-dark` | `#b07d4a` | Darker gold (hover states) |
| `--accent-soft` | `#f3d6c6` | Soft peachy-tan |
| `--neutral` | `#fdf8f2` | Very light cream |
| `--neutral-strong` | `#e4d9c8` | Stronger neutral |
| `--dark` | `#2c1f14` | Very dark brown |

**Fonts (Google Fonts):**
- Playfair Display — headings (serif, warm brown `#7a5c44`)
- Raleway — navigation, labels (uppercase, 600 weight)
- Source Sans 3 — body copy

**Breakpoints:** 880px (tablet), 600px (mobile)

### Site structure

| File | URL | Layout | Notes |
|---|---|---|---|
| `index.md` | `/` | `home` | Homepage: hero, lotus meaning, treatments, reviews |
| `over-mij.md` | `/over-mij/` | `page` | About Emine |
| `hoe-ik-werk.md` | `/hoe-ik-werk/` | `page` | How sessions work |
| `instagram-tool.html` | `/instagram-tool/` | *(standalone)* | **Hidden tool** — Instagram post generator |
| `visitekaartje.html` | `/visitekaartje/` | *(standalone)* | **Hidden tool** — printable business card (85×55mm) |

Hidden tools have `sitemap: false` and `robots: noindex` in their front matter and do not appear in the navigation.

### Navigation

Defined in `_config.yml` under `nav_links`, rendered in `_includes/header.html`. To add a page to the nav, add an entry there:

```yaml
nav_links:
  - title: Paginanaam
    url: /pad/
```

External links (containing `http`) open in a new tab automatically.

### Layouts & includes

- `_layouts/default.html` — base layout (head, header, footer, GoatCounter, Schema.org JSON-LD)
- `_layouts/home.html` — homepage with hero, lotus section, treatments from `_data/behandelingen.yml`
- `_layouts/page.html` — simple content page with `.page-content` wrapper
- `_includes/header.html` — sticky header with logo + nav + mobile hamburger
- `_includes/footer.html` — dark footer with contact info

### Data

- `_data/behandelingen.yml` — treatment definitions (name, duration, price, phases)

### Contact info (source of truth)

| Channel | Value |
|---|---|
| Email | info@lotusmoments.nl |
| WhatsApp / Phone | 06 83 05 95 32 (`wa.me/31683059532`) |
| Instagram | @lotusmoments.nl (`instagram.com/lotusmoments.nl`) |
| Website | lotusmoments.nl |
| Location | Wijk De Vijfhoek, Deventer |
| Booking | https://calendly.com/emine314/30min |

### Assets

- `assets/images/emine1.jpg` — portrait for About page
- `assets/images/emine2.jpg` — portrait for business card back
- `assets/images/ruimte.jpg` — treatment room photo (Hoe ik werk page)
- `assets/lotus-bullet.svg` — custom bullet point used in page content
- `assets/qr-lotusmoments.svg` — QR code for business card
