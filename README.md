<div align="center">

```
██████╗  █████╗ ███████╗███████╗███████╗ ██████╗ ██████╗  ██████╗ ███████╗
██╔══██╗██╔══██╗██╔════╝██╔════╝██╔════╝██╔═══██╗██╔══██╗██╔════╝ ██╔════╝
██████╔╝███████║███████╗███████╗█████╗  ██║   ██║██████╔╝██║  ███╗█████╗  
██╔═══╝ ██╔══██║╚════██║╚════██║██╔══╝  ██║   ██║██╔══██╗██║   ██║██╔══╝  
██║     ██║  ██║███████║███████║██║     ╚██████╔╝██║  ██║╚██████╔╝███████╗
╚═╝     ╚═╝  ╚═╝╚══════╝╚══════╝╚═╝      ╚═════╝ ╚═╝  ╚═╝ ╚═════╝ ╚══════╝
```

**Personal password wordlist generator — fully client-side, zero-trust, zero-server.**

### 🔗 [https://banzoxog.github.io/password/](https://banzoxog.github.io/password/)

[![Live Demo](https://img.shields.io/badge/Live_Demo-banzoxog.github.io-00e5ff?style=flat-square&logo=github)](https://banzoxog.github.io/password/)
[![Single File](https://img.shields.io/badge/Architecture-Single_HTML_File-7c3aed?style=flat-square)](#)
[![No Server](https://img.shields.io/badge/Backend-None-00ffa3?style=flat-square)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-white?style=flat-square)](#license)

</div>

---

## What is this?

PassForge takes the personal info people commonly turn into passwords — names, birthdays, nicknames, pets, partners, kids — and **exhaustively generates every realistic combination** an attacker (or you) might try.

Use it to:
- **Test your own passwords** — see if yours appear in the list
- **Recover a forgotten password** you know was based on personal info
- **Security awareness** — show people why `Alex1998!` is not a strong password

Everything runs in your browser. Nothing is ever transmitted anywhere.

---

## Demo

<div align="center">

> **[→ Open PassForge](https://banzoxog.github.io/password/)**

</div>

---

## Features

| | Feature | Detail |
|---|---|---|
| 🧠 | **Smart word expansion** | Every input word becomes lowercase, UPPERCASE, and Capitalized variants automatically |
| 📅 | **Full date extraction** | Birthdays are split into `dd`, `mm`, `yyyy`, `yy`, `ddmm`, `mmdd`, `ddmmyyyy`, `ddmmyy` and more |
| 🔢 | **Number patterns** | Optionally append birthday numbers or 60+ common numeric suffixes (`123`, `2580`, `99999`, …) |
| 🔣 | **Special characters** | Toggle any of `! @ # $ % & * - _ . ?` — mixed into prefixes and suffixes |
| 👫 | **Multi-person support** | You, partner, child, and pet fields — cross-person combos included |
| ✍️ | **Custom words** | Three free-text word slots for anything not covered (city, team, favourite thing) |
| ⚡ | **Instant results** | Generates tens of thousands of combos in milliseconds |
| 📋 | **Click-to-copy** | Click any password in the list to copy it instantly |
| ↓ | **Bulk export** | Download the full deduplicated list as a `.txt` file |
| 🔒 | **Zero-trust** | Single HTML file, no fetch calls, no analytics, no cookies |

---

## How It Works

```
Input fields
     │
     ▼
┌─────────────────────────────────────┐
│  Word Collector                     │
│  first · last · nick · pet · words  │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  Case Expander                      │
│  "alex" → alex / ALEX / Alex        │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  Date Parser                        │
│  1998-03-15 → 15 / 03 / 1998 /      │
│  98 / 1503 / 0315 / 15031998 / …    │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  Combination Engine                 │
│  [prefix?] + word + [suffix?]       │
│  word + word pairs                  │
│  num × char cross-product suffixes  │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  Deduplicator  (Set-based, O(n))    │
│  Filters: length < 4 removed        │
└──────────────┬──────────────────────┘
               │
               ▼
          Password list
```

---

## Quickstart

```bash
# Option A — just open it
open index.html

# Option B — serve locally (any static server works)
npx serve .
python3 -m http.server 8080
```

No `npm install`. No build step. No dependencies. It's one file.

---

## Example Output

Given inputs `alex`, `mia`, birthday `15/03/1998`, special char `!`:

```
alex
Alex
ALEX
mia
Mia
MIA
alexmia
Alexmia
alex1998
Alex1998
Alex1998!
!Alex1998
mia1503
Mia15031998
Alex!
!mia
... (thousands more)
```

---

## Project Structure

```
password/
├── index.html      ← entire app (HTML + CSS + JS, ~600 lines)
└── README.md       ← you are here
```

---

## Privacy

PassForge was designed from the ground up to never touch a server.

- ✅ No form submissions
- ✅ No `fetch()` or `XMLHttpRequest` to any backend
- ✅ No localStorage or sessionStorage
- ✅ No analytics (no GA, no Plausible, nothing)
- ✅ No cookies
- ✅ Fonts loaded from Google Fonts CDN *(remove the `<link>` tag for full offline use)*

To verify: open DevTools → Network tab → generate passwords → watch zero requests fire.

---

## Tech Stack

```
HTML5          Semantic markup, single-file architecture
CSS3           Custom properties · Grid · Flexbox · keyframe animations
JavaScript     Vanilla ES2020 · Set-based dedup · No frameworks
Fonts          Syne (display) + Space Mono (data) via Google Fonts
Hosting        GitHub Pages
```

---

## Roadmap

- [ ] Leet-speak substitutions (`a→@`, `e→3`, `o→0`, `s→$`)
- [ ] Minimum / maximum length filter
- [ ] Regex search & filter on results
- [ ] PWA support for full offline use
- [ ] Dark / light theme toggle

PRs welcome.

---

## License

MIT — use it, fork it, embed it, do whatever.

---

<div align="center">

Made with 🖤 by [@banzoxog](https://github.com/banzoxog)

*If this helped you, drop a ⭐ — it means a lot.*

</div>
