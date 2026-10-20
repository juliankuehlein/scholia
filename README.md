# Scholia

**Read, code and write about your papers — on your Mac.**

Scholia is a research workbench for people who work with many papers: read PDFs, mark and *code* passages and figures, collect what you still want to read, see how your papers relate to each other, and write your chapters in a notebook that cites them. AI helps where you ask it to, with your own Claude account. Everything else stays on your computer.

![Reading and coding a paper](docs/reader.png)

**[⬇ Download the latest version](../../releases/latest)** · [How to install](#get-started-in-4-steps)

## Get started in 4 steps

> **You need:** a Mac with **macOS 14 (Sonoma) or newer** — Apple Silicon or Intel both work. Reading, OCR, coding, the notebook and the charts work right away. The AI features need a Claude API key (step 4, optional).

### 1 · Download

Open the **[latest release](../../releases/latest)** and, under **Assets** at the bottom of that page, click **`Scholia-….zip`**.

### 2 · Install

Double-click the downloaded zip (Safari does this automatically), then drag **Scholia** into your **Applications** folder.

### 3 · Open it for the first time

Scholia is an independent app and is not notarized by Apple (that would cost the developer a yearly fee), so macOS asks you to confirm **once**:

1. Open **Scholia** from Applications. A message says it *cannot be opened* / *could not verify the developer*. Click **Done** (or **OK**).
2. Open **System Settings ▸ Privacy & Security** and scroll down to the **Security** section.
3. Next to *“Scholia” was blocked* click **Open Anyway**, enter your Mac password, then click **Open Anyway** once more.

From now on Scholia opens like any other app, and **new versions install themselves** from inside the app. If your Mac asks whether Scholia may use the **Keychain**, choose **Always Allow**.

<details><summary>It still won't open, or says the app is “damaged”?</summary>

Open the **Terminal** app, paste this line and press Return, then open Scholia again:

```bash
xattr -dr com.apple.quarantine /Applications/Scholia.app
```

</details>

### 4 · Add your Claude API key (only for AI features)

1. Create a key at [console.anthropic.com](https://console.anthropic.com) under **API keys** (billing must be set up there; you pay Anthropic directly, only for what you use).
2. In Scholia open **Scholia ▸ Settings** (⌘,), paste the key and click **Save to Keychain**.

That's it — create a project, drag your PDFs into the left bar and start reading.

---

## Your Anthropic API key

AI features (naming, summaries, code suggestions, auto-coding, topics, the paper network, search by question, chat) use **your own** Claude API key, so your usage is on your own Anthropic account.

The key is stored **only in your Mac's Keychain**. It is not in the app, not in your project files, and it is only ever sent to Anthropic. The left bar shows an estimate of the tokens and cost for the current session and in total (click it for details and a CSV export).

**What costs money:** only what you start. Chat and code suggestions use the model chosen in the chat panel. Summaries, naming and tagging, topics, auto-coding, AI search and the paper network use a background model (Sonnet 5.5 by default, changeable in Settings). When you add several papers, or use the AI buttons in the Library, you always see a cost estimate before anything is sent.

## What you can do

| | |
|---|---|
| **Read & code** | Big PDF reader with text selection, search and tabs. Select text or draw a box around a figure and apply codes; margin labels show every code next to its passage. Scans are OCR'd on your Mac. |
| **Codes** | Hierarchies, groups, colours, definitions. Double-click a margin label to change a code. Export as REFI-QDA (ATLAS.ti, MAXQDA, NVivo), CSV, JSON or Markdown. |
| **AI auto-coder** | Let Claude propose passages and codes for a paper, then step through them like tracked changes: ↩ accept, ⌫ decline, E edit, → skip. |
| **Notebook** | Pages and subpages with `@` paper tags, `/cite` citations that jump back to the exact sentence, quotes of a code, and a generated reference list. |
| **Library** | Topics, timeline, shared authors, word clouds, code and term co-occurrence, structured AI summaries and a **paper network** (who cites whom; supports, agrees, contradicts). |
| **Search** | Magnifier in the top bar: search all papers, a group or chosen papers with AND / OR / NOT, or ask a question and let AI find the passages. Results are a clickable list that stays in its own tab. |
| **Watchlist** | Mark a reference in a PDF to collect it: Scholia finds the full reference, shows it as a placeholder in the left bar and offers to remove it once the paper is in your library. |

![Library overview](docs/library.png)

![Paper network](docs/network.png)

<details><summary>More screenshots</summary>

![Reviewing AI coding suggestions](docs/review.png)

![AI paper summary](docs/summary.png)

![Notebook](docs/notebook.png)

</details>

### Handy shortcuts

The usual ones (all in the menus too): **⌘K** apply an existing code · **⌘J** new code · **⌘I** AI code suggestions · **⌘⌥C** auto-code or review · **⌘B** add selection to the watchlist · **⌘⇧N** notebook · **⌘⇧A** analysis · **⌘⇧F** focus mode · **⌘W** close tab.

## Privacy & security

- **No account, no tracking, no analytics.** The developer cannot see your papers, notes, codes or key.
- **Your data stays on your Mac** in `~/Library/Application Support/Scholia/Projects/`. Your original PDFs are copied in and never modified.
- **Network access is limited to three things:** Anthropic (only when you use an AI feature; the text you work with is sent for that request), [OpenAlex](https://openalex.org) (paper *titles* only, to confirm journal and authors — switch it off in Settings), and one small update-list file on GitHub.
- **Updates are verified.** Each update is signed with a key only the developer holds, checked before it is installed, and must carry the same code signature as the app you already have. Damaged or unsigned downloads are refused. Your project files are backed up before an update is installed.
- The app runs with the macOS *hardened runtime*.

## Updates

Scholia checks for a new version when you open it. If there is one, a window lists what changed since your version and offers **Update & restart**. Your projects and your API key are untouched. After the restart a short “What's new” window appears. You can also use **Scholia ▸ Check for Updates…**.

In **Settings ▸ Update channel** you can choose *Stable* (default) or *Beta* (every new version first).

## Where things are stored

| | |
|---|---|
| Projects (notes, codes, quotations, PDFs) | `~/Library/Application Support/Scholia/Projects/` |
| Automatic backups before updates | `~/Library/Application Support/Scholia/Backups/` (**Settings ▸ Show project backups in Finder**) |
| API key | macOS Keychain (item “com.scholia.app.anthropic”) |

To move your projects to another Mac, copy the `Scholia` folder in `Application Support` there.

## Troubleshooting

- **“Scholia can't be opened” / “cannot verify the developer”** → see step 3 above (**Open Anyway** in System Settings ▸ Privacy & Security).
- **macOS asks whether Scholia may use the Keychain** → choose **Always Allow**.
- **AI features say there is no key** → paste it in Settings, or allow the Keychain access above.
- **A scanned PDF can't be selected** → it is OCR'd automatically after import; run **OCR** in the toolbar if it was skipped.
- **An update fails** → the download is not installed and nothing changes; try again or download the latest `.zip` from the Releases page.

## Uninstall

Drag Scholia to the Trash. To remove your data as well, delete `~/Library/Application Support/Scholia` and the Keychain item “com.scholia.app.anthropic” in *Keychain Access*.

---

*Scholia is a personal project and is not affiliated with Anthropic. Cost figures in the app are estimates from list prices and may differ slightly from your invoice. Please share the link rather than the file.*

© 2026 Julian Kühlein. Free to use for personal, academic and commercial work. See [LICENSE](LICENSE) — please don't redistribute, sell or modify Scholia or its code without written permission.
