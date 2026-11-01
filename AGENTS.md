# Instructions for AI agents

This repo is a community list of Black Friday and Cyber Monday deals. The list lives in [README.md](README.md) as a single Markdown table. People add deals by opening a pull request against `dqhieu/black-friday-deals`.

If you are an AI agent (Claude, ChatGPT, Codex, Copilot, opencode, Cursor, Gemini, etc.) helping someone add a deal, follow these rules exactly.

## 1. Collect the details first

You need all of these before you edit anything. If any are missing, **ask the user**. Never invent or guess a discount, code, date or URL.

- **Product name**
- **URL**: the product's own website or App Store / Play Store page (`https://`). Referral or UTM parameters are fine. No URL shorteners.
- **Description**: one short sentence on what the product is and which platform it runs on.
- **Discount**: the headline percentage (or "up to X%").
- **Code**, if there is one.
- **Dates**, if the deal is time-limited.
- **Restrictions**, if any (new customers only, first 100, lifetime plan only, direct purchase only, ...).

## 2. Edit only the current year's list

- Edit **`README.md` only**. `README-2024.md` and `README-2025.md` are archives. Don't touch them.
- Don't change any other file. Don't add new files, sections, headings or images.
- Don't edit, reorder, reformat or remove other people's rows. Don't touch the header, the emoji legend or the "Special Request" footer.

## 3. Append your row at the end of the table

Add one new line directly after the **last row** of the `## Deals` table, before the blank line and the `---` separator. Never insert it in the middle or sort the table.

Row format (copy it exactly, including the leading and trailing `|`):

```
|EMOJI|[Product Name](https://example.com)| Short description | Deal details|
```

### Emoji

Pick it from the **highest discount** in the deal:

| Emoji | Discount |
|-------|----------|
| 💸 | less than 50% |
| 🤑 | 50% or more |

### Description

- One sentence, plain language, ideally under ~120 characters.
- Say what it does and the platform (macOS, iPhone, web, WordPress, ...).
- No ALL CAPS, emoji spam or marketing filler ("the best", "revolutionary", ...).

### Deal details

- Start with the discount in bold, e.g. `**40% OFF**` or `**50% OFF** lifetime`.
- Put the code in bold: `with code **BF2026**`. If no code is needed, say "no code needed".
- Add dates in parentheses at the end when they're known, e.g. `(Nov 24 – Dec 1)`.
- Add any restrictions briefly, e.g. `new customers only`, `first 100`.

### Markdown safety

- The whole row must stay on **one line**.
- Don't use a raw `|` inside any cell; it breaks the table. Use `·`, `,` or `/` instead.
- Check that the row has exactly 5 `|` characters, so it lines up with the 4 columns.

### Examples (real rows from the list)

```
|💸|[Compresto](https://compresto.app/?ref=black-friday-deals)| Video, Image & PDF Compression for macOS | 40% OFF with code **BFCM26**|
|🤑|[RewriteBar](https://rewritebar.com?ref=dqhieu)| AI writing toolkit for macOS. Fix grammar, adjust tone, translate, rewrite and summarize in any app, plus custom actions and templates. | **50% OFF** with code **BF2026** (Nov 2 – Dec 3)|
```

### Several deals: one pull request

If the user has more than one deal, put **all of them in a single pull request**. Don't open a separate PR for each deal.

- Add one row per deal, all at the end of the table, in the order the user gave.
- If the user already has an open PR in this repo, add the new rows to that PR's branch instead of opening another one.

## 4. Open the pull request

1. Fork `dqhieu/black-friday-deals` (contributors don't have push access) and create a branch, e.g. `add-<product-name>-bf2026`.
2. Right before committing, sync with the latest upstream `main`. Every PR appends to the same spot, so a stale branch will conflict. If someone else's row has appeared at the end, put yours after it.
3. Commit with the message `Add <Product Name>`. You can add the headline discount: `Add <Product Name> (Black Friday 2026: 50% off)`.
4. Open the PR against `dqhieu/black-friday-deals:main` with the same title. In the body, give the product link and a one-line summary of the deal.
5. The diff should be **only added line(s) in `README.md`**. If it shows anything else (whitespace changes, edits to other rows, other files), fix it before opening the PR.

## Checklist before you finish

- [ ] Only `README.md` changed, and only by adding line(s) at the end of the Deals table
- [ ] All of this user's deals are in this one PR (no separate PR per deal)
- [ ] Emoji matches the discount (💸 < 50%, 🤑 ≥ 50%)
- [ ] Link works and points to the product
- [ ] Discount, code and dates came from the user, not from guessing
- [ ] Row is on one line, has no stray `|` and has 5 `|` characters
- [ ] Branch is up to date with upstream `main`
