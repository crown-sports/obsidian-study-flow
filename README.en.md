# Obsidian Study Flow · by crown

Turn passages from your PDFs into cards you come back to review.

[中文](README.md) · [Download v0.2.1](https://github.com/crown-sports/obsidian-study-flow/releases/tag/v0.2.1) · [User guide](docs/native-guide.en.md)

Capture a passage while reading. Explain it in your own words later, then make a
question worth revisiting. Excerpts and cards stay in local Markdown, with a link
back to the PDF when you need the context. The workbench supports English and Chinese.

![Real Obsidian window with a PDF selection and the capture button](docs/images/v0.2/02-capture.png)

*Select a passage and capture it. You can keep reading and leave the reflection for later.*

## Write your understanding, then a question

Find the passage in **Inbox** and add your reflection. One excerpt can lead to
several cards. Keep an unfinished question as a draft; preview it before publishing.

![Card editor over the excerpt inbox, with a question, answer, deck, preview and draft/publish buttons](docs/images/v0.2/03-inbox-card.png)

*The screenshots use the included original practice material. Drafts stay out of review.*

## Recall first, reveal and rate

**Review** opens Spaced Repetition's native reviewer. Answer, flip, and rate the
card. Its back links to both the PDF passage and your reflection. Editing a card
you have already reviewed preserves its existing schedule.

![Native Spaced Repetition review with answer, source links and rating buttons](docs/images/v0.2/04-sr-review.png)

*Existing macOS screenshots of the v0.2 interface, which v0.2.1 retains. That patch updates onboarding and the example vault. [Image sources](docs/images/README.md).*

## Try one loop in the example vault

Choose a ZIP from the [v0.2.1 release](https://github.com/crown-sports/obsidian-study-flow/releases/tag/v0.2.1):

| What you want | Download |
| --- | --- |
| Try it without changing your vault | **`obsidian-study-flow-example-v0.2.1.zip`**, with the plugin and practice PDF |
| Add it to an existing vault | **`obsidian-study-flow-plugin-v0.2.1.zip`**; put `study-flow` in your vault's `.obsidian/plugins/` |
| Keep using the old QuickAdd macros | `obsidian-study-flow-starter-v0.2.1.zip`, the [legacy example and English quickstart](docs/guide.en.md) |

1. Unzip the example. Open `Study-Flow-Example` as a new Obsidian vault and enable **Study Flow**.
2. Install and enable **PDF++** and **Spaced Repetition** from Community Plugins. Open the 🎓 workbench and save the defaults.
3. Open `03_PDF/主动回忆示例.pdf`, select the first two lines on page 1, and run **Study Flow: Capture PDF selection**.
4. In **Inbox**, write a reflection such as “Recognition is not recall.” Create a card asking “Why is rereading different from remembering?” Answer in your own words, preview and publish.
5. Open **Review**, answer and rate the card, then follow its source link back to the PDF. The vault's `00_开始.md` also walks through these steps.

Missing a card? Publish the draft, then check that SR is enabled and the selected
deck includes it. GitHub's “Source code” archives are not plugin installers.
Study Flow is not in Community Plugins yet; install PDF++ and SR separately.
Normal use needs no Node, QuickAdd or API key. [Installation, checksums and help](docs/native-guide.en.md).

## Keep your existing notes and cards

**0.2.0 → 0.2.1:** back up the vault, close Obsidian, replace the plugin files and
keep `data.json`. The record format is unchanged; no legacy-data migration is
needed for this patch. Reopen and rebuild the learning index.

**Legacy QuickAdd records:** preview the upgrade in the workbench before confirming
backup and upgrade. Original text and review schedules are retained; restoration
checks for newer edits. Try a vault copy first. [Upgrade and recovery](docs/native-guide.en.md).

## A few limits

Study Flow handles capture, reflection, cards and local files. PDF++ supplies
selection/navigation; Spaced Repetition supplies review scheduling. Scanned PDFs
need a text layer. OCR, generated cards and image occlusion are not included.
On mobile, sync your notes and attachments to review them with SR.

Desktop operation has been checked on macOS with Obsidian 1.13.7, PDF++ 0.40.31 and
SR 1.15.4. Windows/Linux application operation is still unverified.
[Compatibility](docs/compatibility.md).

## Development

Node 20+: `npm ci` → `npm run check` → `npm test` → `npm run package`.
`dist/` contains three installation ZIPs and `SHA256SUMS`.

[Architecture and API](docs/architecture.md) · [Implementation notes](docs/product.md) · [Contributing](CONTRIBUTING.md) · [Legacy QuickAdd guide](docs/guide.en.md) · [MIT](LICENSE) · [Acknowledgements](NOTICE)
