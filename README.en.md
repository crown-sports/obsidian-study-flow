# Obsidian Study Flow · by crown

**Read a PDF → capture a passage → write your understanding → make a card → review → return to the source.**

[中文](README.md) · [User guide](docs/native-guide.en.md) · [Download](https://github.com/crown-sports/obsidian-study-flow/releases/tag/v0.2.1) · [Value and evidence](docs/product.md)

For people who read textbooks, papers or work material in Obsidian and accumulate
highlights they rarely revisit. Capture while reading, reflect later, and publish
only the questions worth reviewing. Your excerpts and cards remain editable
Markdown with links to the original passage. The desktop workbench supports
English and Chinese.

## Choose your download

Get the chosen ZIP and `SHA256SUMS` from the [v0.2.1 release](https://github.com/crown-sports/obsidian-study-flow/releases/tag/v0.2.1).
The [guide](docs/native-guide.en.md) explains checksum verification.

| Your situation | Download |
| --- | --- |
| Try it without changing your own vault | **`obsidian-study-flow-example-v0.2.1.zip`**: separate practice vault, plugin and original PDF |
| Install in an existing vault | **`obsidian-study-flow-plugin-v0.2.1.zip`**: put its `study-flow` folder in your vault's `.obsidian/plugins/` |
| Keep the old QuickAdd workflow | `obsidian-study-flow-starter-v0.2.1.zip`: legacy example; new users should choose one of the above |

GitHub's automatic “Source code” archives are developer source, not installable
plugin packages. Study Flow is not listed in Community Plugins yet. Install
**PDF++** and **Spaced Repetition** separately from Community Plugins; their
binaries are not bundled. Native use needs no Node, QuickAdd, JSON editing or API key.

## Complete your first learning loop

1. Unzip the example and open `Study-Flow-Example` as a new Obsidian vault. Enable **Study Flow** in Community Plugins.
2. Install and enable **PDF++** and **Spaced Repetition**. Open the 🎓 workbench and save its defaults; dependency status and installation links are shown there.
3. Open `03_PDF/主动回忆示例.pdf`, select the first two lines on page 1, and run **Study Flow: Capture PDF selection**.
4. In **Inbox**, write your reflection, such as “Recognition is not recall.” Create a question: “Why is rereading different from remembering?” Answer in your own words, save a draft, preview and publish.
5. In **Review**, start native SR review. Recall first, reveal the answer and rate it. Follow the source link on the back to return to the PDF.

**Your first result:** an excerpt with the original passage and your reflection,
a published review card, and a working source link. Drafts stay out of review.
If a card is absent, check publication, SR enablement and the selected deck.
The example's `00_开始.md` repeats these steps inside Obsidian.

![Capture while reading](docs/images/v0.2/02-capture.png)

![Inbox and card preview](docs/images/v0.2/03-inbox-card.png)

## Keep reading and organizing separate

| Situation | Behavior |
| --- | --- |
| A passage matters now, but you need to keep reading | Save the selection immediately; a repeated identical capture returns the existing excerpt |
| A question is not ready | Save a draft without sending it into review |
| You edit a reviewed card | Keep its file, identity and existing SM-2 / FSRS scheduling comments |
| The source moved or is missing | Repair links or relink the PDF; the captured text remains available |
| You return to a document | Restore saved progress for PDFs you have started; mark completion yourself |

Study Flow connects capture, reflection, publishing and recovery. PDF++ provides
PDF selection/navigation; Spaced Repetition provides native review and scheduling.
The [implementation evidence](docs/product.md) covers text preservation, scheduling,
duplicate capture and migration conflicts. It supports those behaviors, not a
claim of improved learning outcomes or a new repetition algorithm.

## Continue with existing notes and cards

**0.2.0 → 0.2.1:** this updates onboarding and the example vault. The record format
is unchanged; do not rerun legacy-data migration just for this patch.

**Existing 0.2.0 or v0.2 preview plugin:** back up the vault, close Obsidian, replace the
plugin files with the new package and preserve `data.json`. Reopen and rebuild the
learning index. Do not use an older preview to edit records saved by the new version.

**Legacy QuickAdd data:** open the workbench's legacy-upgrade preview. Nothing is
written until you confirm backup and upgrade. Original content and review schedules
are retained; restoration stops if newer edits would be overwritten. Try your vault
copy first. [Upgrade and recovery steps](docs/native-guide.en.md).

QuickAdd remains optional for existing macros. The separate
[legacy guide](docs/install.md) documents that route; new users can follow the
native workflow above.

## Scope and evidence

Processing stays local. Scanned PDFs need a text layer. OCR, AI-generated cards
and image occlusion are not implemented. Mobile users can review synced Markdown
and attachments with SR; native mobile capture is not supported.

The [existing application validation](docs/validation-v0.2.md) covers macOS,
Obsidian 1.13.7, PDF++ 0.40.31 and SR 1.15.4. Windows/Linux build and file tests run
in CI; their application UI is unverified. This documentation update adds no new
in-app or user-study validation. [Supported formats and versions](docs/compatibility.md).

## Development

Node 20+: `npm ci`, `npm run check`, `npm test`, `npm run package`.
`dist/` contains the plugin, native example, separate legacy starter and checksums.

[Architecture](docs/architecture.md) · [Contributing](CONTRIBUTING.md) · [MIT](LICENSE) · [Upstream acknowledgements](NOTICE)

Examples and screenshots use original practice material, not personal vault contents or paid textbooks.
