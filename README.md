# Obsidian Study Flow · by crown

把 PDF 里的重点，变成会回来复习的卡片。

[English](README.en.md) · [下载 v0.2.1](https://github.com/crown-sports/obsidian-study-flow/releases/tag/v0.2.1) · [安装与使用](docs/native-guide.md)

读教材、论文时先保存原文，整理时写下自己的理解，再挑值得记住的问题制卡。
摘录和卡片留在本地 Markdown 中，复习时可以一键回到 PDF 原文。

![在真实 Obsidian 窗口阅读 PDF，选中文字后保存到摘录收件箱](docs/images/v0.2/02-capture.png)

*阅读时选中一段文字，点「保存 PDF 选区」。先收下，不必马上打断阅读写小结。*

## 整理时写理解，再出一道题

在「摘录收件箱」找到原文，点「写理解」，用自己的话解释。
一条摘录可以做成多张卡。问题还没想好就存草稿，预览满意后再发布到复习。

![收件箱中的理解与制卡窗口：问题、答案、卡组、预览、保存草稿和发布](docs/images/v0.2/03-inbox-card.png)

*示例用的是仓库原创练习资料。草稿不会进入复习。*

## 复习时先回忆，再看答案

「今日复习」打开 Spaced Repetition 的原生复习窗口。
回答、翻面、评分；想核对时，点答案中的「回到原文」或「摘录与理解」。
修改已经复习过的卡片，也会保留原来的复习调度。

![真实 SR 复习窗口：卡片答案、来源链接和四个评分按钮](docs/images/v0.2/04-sr-review.png)

*以上为已有 macOS 实测截图，界面沿用 v0.2；v0.2.1 更新上手文档与示例包。[截图来源](docs/images/README.md)。*

## 先用示例库试一轮

从 [v0.2.1 发布页](https://github.com/crown-sports/obsidian-study-flow/releases/tag/v0.2.1)下载对应 ZIP：

| 你想怎么用 | 下载哪个 |
| --- | --- |
| 先试用，不动自己的笔记库 | **`obsidian-study-flow-example-v0.2.1.zip`**，含插件和练习 PDF |
| 装进已有笔记库 | **`obsidian-study-flow-plugin-v0.2.1.zip`**，将 `study-flow` 放到库内 `.obsidian/plugins/` |
| 继续使用旧 QuickAdd 宏 | `obsidian-study-flow-starter-v0.2.1.zip`，旧流程示例 |

1. 解压示例包，将 `Study-Flow-Example` 作为 Obsidian 新库打开，启用 **Study Flow**。
2. 从社区市场安装并启用 **PDF++**、**Spaced Repetition**。点 🎓 打开工作台，保存默认配置。
3. 打开 `03_PDF/主动回忆示例.pdf`，选中第一页前两行，运行 **Study Flow: 保存 PDF 选区**。
4. 在收件箱写理解，例如「看着熟悉，不等于能独立回答」。建一张卡，问题写「为什么重读不等于记住？」，自己填写答案，预览后发布。
5. 去「今日复习」回答并评分，再点来源链接回到 PDF。库内的 `00_开始.md` 也有这套步骤。

复习里没看到卡片？先发布，再确认 SR 已启用、所选卡组包含这张卡。
GitHub 的 “Source code” 不是插件安装包。Study Flow 尚未上架社区市场，另外两个插件需单独安装；
普通使用不需要 Node、QuickAdd 或 API Key。[安装、校验下载与常见问题](docs/native-guide.md)。

## 已有笔记和卡片继续用

**0.2.0 升到 0.2.1：**备份库、关闭 Obsidian，替换插件文件并保留 `data.json`。
记录格式不变，不必重新执行旧数据升级；重新打开后重建学习索引。

**旧 QuickAdd 记录：**从工作台「升级旧数据」先预览，再确认「备份并升级」。原文和复习记录保留，
恢复前会检查后续编辑。建议先在库副本上操作。[升级与恢复步骤](docs/native-guide.md)。

## 使用范围

Study Flow 负责摘录、理解、制卡和本地文件；PDF++ 负责选区与定位，Spaced Repetition 负责复习调度。
扫描 PDF 需要先有文字层，当前不含 OCR、AI 制卡或图像遮挡。手机端可同步笔记后用 SR 复习。

桌面操作已在 macOS 的 Obsidian 1.13.7、PDF++ 0.40.31、SR 1.15.4 验证；
Windows/Linux 的应用操作尚待验证。[兼容范围](docs/compatibility.md)。

## 开发

Node 20+：`npm ci` → `npm run check` → `npm test` → `npm run package`。
`dist/` 生成三个安装 ZIP 与 `SHA256SUMS`。

[架构与 API](docs/architecture.md) · [实现说明](docs/product.md) · [贡献指南](CONTRIBUTING.md) · [旧 QuickAdd 教程](docs/guide.md) · [MIT](LICENSE) · [上游致谢](NOTICE)
