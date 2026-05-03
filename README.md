# VM CleanTrail Marketing Site

The static one-page marketing site for **VM CleanTrail™**, the customer service portal product from Vacu-Man Furnace and Duct Cleaning.

- **Live URL:** https://vmcleantrail.ca
- **Mirror:** https://vmcleantrail.com (301 redirects to .ca)
- **Hosting:** Hostinger (`public_html` folder)
- **Owner:** Vacu-Man Furnace and Duct Cleaning, Hamilton ON

---

## What this site does

VM CleanTrail is a QR-coded sticker product. Every Vacu-Man service ends with a sticker placed on the customer's furnace. Scanning the QR code opens that property's service record — before-and-after photos, technician info, dryer vent certificate of completion, and full service history.

This site is the public-facing marketing page that explains the product to prospective customers, property managers, and insurers. It is intentionally a single static HTML page with no backend, no build step, no JavaScript framework. Editing is direct: open `index.html` in any text editor, change what you need, save, deploy.

---

## File inventory

### Source

| File | Purpose |
|---|---|
| `index.html` | The entire site. HTML, CSS, and SEO metadata (canonical, OG tags, Twitter Card, Schema.org JSON-LD with FAQPage and LocalBusiness). |

### Logos

| File | Used for |
|---|---|
| `VM_logo_white_1150x350.png` | Vacu-Man wordmark in the header. Tight-cropped, white on transparent. |
| `VM_Clean_Trail_-_logo_-_cleaned_1530x350.png` | CleanTrail logo in the header. Tight-cropped. Sits on dark background; black is baked in (looks transparent visually because the header is also dark). |
| `VM_CleanTrail_white_transparent.png` | CleanTrail logo for the red CTA section. True PNG transparency so the white wordmark sits cleanly on red. |
| `Vacuman_Logo_Tagline_WHITE.png` | Footer logo (smaller). |
| `Vacuman_Logo_tagline_RGB.png` | Referenced only by URL inside the Schema.org JSON-LD `logo` field. Google fetches this when generating rich snippets. Do not delete. |
| `45_years_-_VM_-_RED.png` | The "45 Years" anniversary badge in the legacy section. |

### Hero and section imagery

| File | Used in section |
|---|---|
| `HERO_-_holding_phone_with_CleanTrail.png` | Hero (top of page), right side. |
| `HERO_-_3_fingers.png` | "How CleanTrail Works" section, left side. Chroma-keyed transparent. |
| `HERO_-_looking_up.jpg` | FAQ section, left side. Cream background baked in to match section colour. |
| `CleanTrail_-_the_new_before___after.png` | Proof section image. |
| `sticker_job_30269_01.jpeg` | Step 1 icon. |
| `scan_job_30269_02.jpeg` | Step 2 icon. |
| `portal_job_30269_03.jpeg` | Step 3 icon. |

### Discoverability and favicons

| File | Purpose |
|---|---|
| `og-image.png` | 1200x630 Open Graph image for social shares (Facebook, LinkedIn, Twitter, etc.). |
| `favicon.png` | Browser tab icon. |
| `apple-touch-icon.png` | iOS home-screen icon. |

---

## Deploying changes

### Manual (current method)

1. Edit files locally.
2. Log into Hostinger.
3. Open File Manager and navigate to `public_html`.
4. Drag the changed files in to overwrite.
5. Hard-refresh the live site to confirm.

### Automated (recommended for the future)

Once the repo lives on GitHub, you can automate deployment so commits to the `main` branch auto-publish to Hostinger. Two paths:

- **Git deployment:** Hostinger supports pulling from a GitHub repo directly on most plans. Configure once in the Hostinger control panel under "Git" — point it at this repo and the `main` branch.
- **GitHub Actions + FTP:** Add a workflow file that uploads changed files via FTP on every push. Eman has done this kind of plumbing for other Vacu-Man projects.

Either path eliminates the manual file-by-file drag and drop.

---

## Known gotchas

### Hostinger sometimes auto-converts PNG to JPEG on upload

Several PNG uploads in the past have come back as `.jpeg` files on the server, which strips transparency. The HTML in this repo references the actual extensions currently on the server. If you upload a PNG and find it has been renamed `.jpeg`, the broken transparency may show as a black or white rectangle around the asset. Two options:

1. Re-upload using a different method (FTP client like FileZilla often preserves PNG).
2. Pre-bake the matching background colour into the image so transparency is not required (this was done for `HERO_-_looking_up.jpg`, where cream is baked in to match the FAQ section).

### Some logo PNGs have black backgrounds baked in

`VM_Clean_Trail_-_logo_-_cleaned_1530x350.png` and `VM_logo_white_1150x350.png` have black backgrounds. They sit on the dark header where this is invisible. If you ever need either logo on a non-dark background, use `VM_CleanTrail_white_transparent.png` (already chroma-keyed), or chroma-key a fresh version.

### The CleanTrail PNG aspect ratio is wide

The header logos are 3.29:1 (Vacu-Man) and 4.39:1 (CleanTrail). At 90px and 180px tall on desktop, they render around 296px and 790px wide respectively. If you change the height, the width scales proportionally — be aware of available container space (max-width 1200px).

---

## Brand standards (apply to all edits)

- **Canadian English** spelling throughout (colour, organisation, optimise, etc.)
- **No em dashes** — never use `—` or `--`
- **Brand red** `#C8102E`, **brand navy** `#1F3864`, **CleanTrail teal** `#2D8A82` (defined as CSS variables at the top of `index.html`)
- **Helvetica Rounded** for headings (with Sora fallback), **Manrope** for body
- **Phone-first CTAs** — call buttons use `tel:+19053335454`
- **Maximum three emojis** per social post (not relevant to this static site, but worth noting)
- **Motto:** "Do It Right or Don't Do It At All"

---

## Contact

- **Owner:** Adam Oldfield, President, Vacu-Man Furnace & Duct Cleaning
- **Phone:** (905) 333-5454
- **Address:** 4 Lyndhurst Street, Hamilton, ON, L8L 7G7
