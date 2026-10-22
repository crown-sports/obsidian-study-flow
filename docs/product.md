# Why Study Flow / 为什么用 Study Flow

[中文首页](../README.md) · [English README](../README.en.md)

## 用户完成的是一轮学习

适合已经在 Obsidian 阅读 PDF、希望把读过的内容变成可复习问题的人：阅读时先留原文，整理时补理解，确认问答后才发布。最后得到可编辑的摘录与卡片，并能从卡片返回来源。它不替你理解，不自动生成答案，也不承诺提高考试成绩。

For people who read PDFs in Obsidian, the job is to turn a passage into a question
worth reviewing without losing its source. Capture can happen during reading;
reflection and card publication can happen later. The output stays in Markdown.

## 现有优势与实现证据 / Current advantages and evidence

| 对用户的价值 / Value | 可核对的实现与测试 / Evidence |
| --- | --- |
| 原文、自己的理解、草稿与已发布卡片分开；未完成的草稿不进入复习 / Keep unfinished drafts outside review | [service](../src/core/service.ts), [Markdown codec](../src/core/markdown.ts), [core tests](../tests/plugin/core.test.ts) use the pinned SR parser to check one published card and no draft cards |
| 修改学过的卡片保留复习记录，修改理解保留自由笔记 / Keep schedules and freeform notes during edits | [core tests](../tests/plugin/core.test.ts) cover SM-2/FSRS comments, escaped text round-trips and concurrent edits; [review adapter tests](../tests/plugin/review.test.ts) |
| 原始 PDF 不在时仍保留摘录快照，重新关联后修复链接 / Keep source snapshots and repair links | [service](../src/core/service.ts), [identity/index](../src/core/index.ts), rename/relink tests in [core tests](../tests/plugin/core.test.ts) |
| 旧记录先预览、备份再升级；恢复时不覆盖后续编辑 / Preview upgrades and stop restoration on newer edits | [migration](../src/core/migration.ts), partial failure and restore preflight tests in [core tests](../tests/plugin/core.test.ts) |

这些优势来自学习流程连接、兼容适配和数据保留的工程细节。PDF 选区能力来自 PDF++，复习调度来自 Spaced Repetition；Study Flow 没有发明新的间隔算法。

The value is the connected workflow and preservation behavior. PDF++ supplies
PDF selection/navigation; Spaced Repetition supplies review and scheduling. Study
Flow does not claim a new memory algorithm.

## 证据范围 / Evidence limits

[已有验收记录](validation-v0.2.md)记载 macOS / Obsidian 1.13.7 / PDF++ 0.40.31 / SR 1.15.4 的应用操作。本次产品文档整理只核对源代码、已有测试和安装包内容，没有新增真人访谈或 Obsidian UI 验收。Windows/Linux 有构建和文件测试，不等于应用操作验收。

The [existing validation record](validation-v0.2.md) covers the listed macOS
application versions. This documentation pass checks source, existing tests and
package contents; it adds no new in-app or user-study evidence. See
[compatibility](compatibility.md) for supported card syntax and platform limits.

扫描 PDF 需要文字层；手机端面向同步后使用 SR 复习，没有移动采集界面。OCR、AI 制卡、图像遮挡均未实现。

Scanned PDFs need a text layer. Mobile use is synced-card review through SR, not
native mobile capture. OCR, AI card generation and image occlusion are absent.

## 可积累的长期优势 / What could become a durable advantage

可持续积累的是跨 PDF++ / SR 版本的兼容案例、匿名且经用户同意的问题复现、升级与恢复测试，以及从摘录到复习的真实使用反馈。当前没有证据证明“不可替代”或学习收益；未来应验证首次完成流程的成功率、数据保留与兼容稳定性，而不是以功能数量代替用户效果。

Maintained compatibility cases, consented reproducible bug reports, migration
coverage and observed completion of the capture-to-review workflow could build
lasting value. Current evidence supports the implemented behavior, not unique
market defensibility or measured learning gains.
