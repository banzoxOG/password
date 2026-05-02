# 🔐 Personal Password Generator

A simple, fully offline tool that generates every possible password combination based on your personal information — names, birthdays, nicknames, pets, and more.

> **100% private.** Everything runs in your browser. No data is sent to any server.

---

## ✨ Features

- **Personal info inputs** — you, your partner, child, and pet
- **Special words** — add custom words that matter to you
- **Birthday numbers** — automatically extracts day, month, year, short year, full date from every birthday you enter
- **Common numbers** — hundreds of 1–5 digit patterns (23, 99, 123, 1234, 12345, 54321…)
- **Special characters** — pick any combination of `! @ # $ % & * - _ . ?`
- **Leet speak variants** — auto-generates `a→4`, `e→3`, `i→1`, `o→0`, `s→5` variants
- **Word combinations** — pairs every word with every other word + numbers + symbols
- **Download as `.txt`** — plain list, one password per line, no labels
- **Search & filter** — search, sort A–Z, longest first, shortest first
- **Copy to clipboard** — one click per password
- **No dependencies** — pure HTML, CSS, and JavaScript. One file.

---

## 🚀 Usage

### Option 1 — Open directly
Just download `index.html` and open it in any browser. No install needed.

### Option 2 — Clone and run
```bash
git clone https://github.com/your-username/personal-password-generator.git
cd personal-password-generator
open index.html
```

### Option 3 — GitHub Pages
Push to GitHub and enable **Pages** (Settings → Pages → Branch: main → / root).  
Your tool will be live at `https://your-username.github.io/personal-password-generator/`

---

## 📖 How it works

1. Fill in whichever fields apply to you
2. Choose whether to include birthday numbers, common numbers, or both
3. Select which special characters to append
4. Click **Generate passwords**
5. Browse the preview list or hit **Download .txt** to get the full file

### What gets generated

For each word entered, the generator creates these variants:

| Input | Variants generated |
|-------|--------------------|
| `ilyass` | `ilyass`, `ILYASS`, `Ilyass`, `1ly455` (leet) |

Then it combines every variant with every number and every special character, in multiple positions:

```
ilyass
ilyass12
ilyass12!
12ilyass
ilyass!12
!ilyass12
ilyasssara
ilyasssara1990
...
```

Word pairs are also generated — every word combined with every other word, with and without numbers/symbols.

---

## 📁 Output format

The downloaded `.txt` file is plain text, one password per line:

```
ilyass
Ilyass
ILYASS
1ly455
ilyass1
ilyass12
ilyass123
ilyass1234
ilyass!
ilyass@
...
```

---

## 🛡️ Privacy

- No internet connection required after loading the page
- No analytics, no tracking, no cookies
- No data leaves your device — ever
- Safe to use on an air-gapped machine

---

## 📂 Project structure

```
personal-password-generator/
├── index.html   ← the entire app (single file)
└── README.md
```

---

## 🤝 Contributing

Pull requests welcome. Ideas for improvement:

- [ ] Add a second child slot
- [ ] Add anniversary / important date field
- [ ] Minimum / maximum password length filter
- [ ] Regex filter for advanced search
- [ ] Dark / light mode toggle

---

## 📄 License

MIT — do whatever you want with it.
