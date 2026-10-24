# Chrome Web Store — Listing Pack (CJ Product Hunter)

Copy-paste ready fields for the Chrome Web Store Developer Dashboard.
Package: `cj-product-hunter-extension.zip` (extension/ folder only, manifest at ZIP root, 9 entries).

---

## 1. Store listing

| Field | Value |
|---|---|
| **Title** (≤45) | `CJ Product Hunter` |
| **Summary** (≤132) | `Hunt CJ winning products: search, score, sales, reviews, supplier info and ship quotes — runs on your own local backend.` |
| **Category** | `Shopping` (alt: `Tools`) |
| **Language** | English |

**Detailed description:**

```
Hunt CJdropshipping winning products without leaving Chrome.

WHAT IT DOES
• Search CJ's product catalog (and 🔥 Trending / 🛒 Best-Selling lists)
• Winning-product score with evidence (price, stock, orders, listing age)
• Sales, reviews, supplier and warehouse info per product
• Ship-from / deliver-to country selectors with automatic shipping-cost
  and delivery-time quotes (CJ freight API)
• 🚀 Quick-delivery filter (stock in the destination warehouse)
• Variant Pricing dialog → list a product straight into your own CJ store
• Local profit calculator (cost, fees, margin)

HOW IT WORKS
The extension is a front-end for a local backend you run on your own
computer (Node.js, one command: npm start). It connects ONLY to
http://localhost:3000 — nothing else. Results come from the CJdropshipping
API through that backend.

REQUIREMENTS
• Chrome 116+
• The local backend running (npm start in the project folder)
• A free CJdropshipping API key, pasted in Settings (⚙) — stored only on
  your own machine, never inside the extension

PRIVACY
No developer server, no analytics, no tracking, no accounts. Your search
terms and (optional) API key go only to your local backend on this
computer. Full policy: https://gist.github.com/Lucky-Draw-777/dd9c5a4fe664bbc2bf09517e4af49ef6

UNOFFICIAL — not affiliated with, endorsed by, or sponsored by CJdropshipping.
```

---

## 2. Privacy practices tab

**Single purpose** (statement):

```
Provide product research for dropshippers: search, score and analyze
CJdropshipping products and list them to the user's own CJ store, using
the user's local backend, displayed in Chrome's side panel.
```

**Permission justifications:**

| Permission | Justification |
|---|---|
| `sidePanel` | Opens the hunting panel in Chrome's side panel when the toolbar icon is clicked. |
| `storage` | Saves your last search term locally (chrome.storage.local) so it is prefilled next visit. Stored only in this browser; not transmitted anywhere. |
| `host_permissions: http://localhost:3000/*` | Communicates exclusively with the user's own backend running on the same computer. No other hosts are declared or contacted; the extension has no content scripts. |

**Remote code:** `No` — "All code ships inside the package; no eval, no dynamically loaded remote scripts, no CDN."

**Data collection / usage disclosures:**

- Search queries → used **only** to run the search through your own local backend (which queries the CJ API). The last query is stored locally in `chrome.storage`. Not shared with the developer or any third party.
- API key (if entered in Settings) → stored only in a local file on your machine (`data/settings.json`); sent only to `http://localhost:3000` and CJ's own API through it.
- Declare: **"This extension does not collect or share user data with the developer."**
- **Privacy policy URL:** `https://gist.github.com/Lucky-Draw-777/dd9c5a4fe664bbc2bf09517e4af49ef6` (live, publicly accessible — verified)

---

## 3. Assets checklist

| Asset | File | Size |
|---|---|---|
| Package | `cj-product-hunter-extension.zip` | ≤2GB (ours ~40KB) |
| **Store icon (recommended, IP-safe)** | `store-assets/store-icon-128x128-alt.png` | exactly 128×128, full-bleed square, PNG ✓ |
| Store icon (alt art — has CJ-style logo) | `store-assets/store-icon-128x128.png` | exactly 128×128, PNG ✓ (⚠️ IP/impersonation flag risk) |
| Icon 128 (in package/manifest) | `extension/icons/icon128.png` | exactly 128×128 ✓ |
| Screenshot 1 | `store-assets/screenshots/01-search-results-1280x800.png` | 1280×800 ✓ |
| Screenshot 2 | `store-assets/screenshots/02-product-detail-1280x800.png` | 1280×800 ✓ |
| Screenshot 3 | `store-assets/screenshots/03-filters-1280x800.png` | 1280×800 ✓ |
| Screenshot 4 | `store-assets/screenshots/04-sidepanel-640x400.png` | 640×400 ✓ |
| Screenshot 5 | `store-assets/screenshots/05-settings-1280x800.png` | 1280×800 ✓ |
| **Small promo tile** (also usable for Promotional tile) | `store-assets/promo-tile-440x280.png` | exactly 440×280, PNG ✓ |
| **Marquee promo tile** | `store-assets/marquee-promo-tile-1400x560.png` | exactly 1400×560, **24-bit PNG (no alpha)** ✓ |
| Privacy policy | `store-assets/privacy-policy.md` | hosted publicly (§4) |

---

## 4. Privacy policy URL (live)

**https://gist.github.com/Lucky-Draw-777/dd9c5a4fe664bbc2bf09517e4af49ef6**

- Source file: `store-assets/privacy-policy.md`, published as a **public GitHub gist** under your `gh` account (Lucky-Draw-777) and rendered there as a readable policy page.
- Verified publicly accessible without login on 22 October 2026.
- Prefer your own hosting later? Publish the same text via GitHub Pages/Netlify and paste the new URL in the dashboard — the wording is identical, no need to reword the policy.

---

## 5. Submission steps

1. Pay the **one-time $5 registration fee** (Developer Dashboard → one-time fee) if this is your first extension.
2. Dashboard → **New item → Extension** → upload `cj-product-hunter-extension.zip`.
3. Fill **Store listing** (§1), upload screenshots (§3).
4. Fill **Privacy practices** (§2) — paste privacy policy URL.
5. **Distribution:** Public (or Unlisted while you test).
6. **Submit for review** — first review usually takes 1–3 working days.

### Review-risk notes (already handled / watch out)
- ✅ No remote code, no inline scripts/event handlers (MV3 CSP-safe).
- ✅ Minimal permissions: only `storage`, `sidePanel`, localhost host permission; no content scripts, no `<all_urls>`.
- ✅ Icon sizes exact; screenshots exact CWS sizes.
- ✅ API key never packaged in the extension; only a placeholder input.
- ⚠️ Name/branding: "CJ" could be flagged as implying affiliation with CJdropshipping — the listing already contains the "UNOFFICIAL" disclaimer. If Google still rejects it, rename to e.g. **"Winning Product Hunter (Local)"** in the dashboard (no rebuild needed — name lives in the manifest; if asked to rebuild, change `name` in `extension/manifest.json` and re-zip).
- ⚠️ If asked about localhost: explain it connects only to the user's own backend on their machine (justification in §2 covers it).
