# Changelog

## 0.2.1 - 2026-10-23

- Clarify plugin/example/legacy downloads and the first PDF → reflection → card → review loop in English and Chinese.
- Include the first-result checklist and troubleshooting cues in the example vault’s `00_开始.md`.
- Document implementation evidence, product limits and existing-record upgrade steps. Core learning behavior, record formats and scheduling are unchanged; existing 0.2.0 users do not need to rerun legacy migration.

## 0.2.0 - 2026-10-22

- Preserve literal backslashes, escaped separators and literal `<br>` lines across repeated card/excerpt edits. New saves use schema 2 and an explicit text encoding; schema 1 notes retain the legacy decoder until saved. Older previews reject the new schema instead of silently rewriting it.
- Reject reserved control comments in encoded text before overwriting a learning record, and reject unknown text encodings.


- 原生桌面插件、crown 品牌、中英文工作台、设置与依赖安装入口。
- PDF 即时选区快照、独立摘录收件箱、理解、多卡片草稿与发布。
- 稳定 ID / 路径、Markdown 增量索引、手工编辑冲突比较与调度合并。
- SR 原生复习入口与可靠新卡 / 到期统计，保留 SM-2 / FSRS 注释。
- 文档身份校验、1.5 秒阅读进度保存、原文回跳、重命名与缺失 PDF 重新关联。
- 原生复制 / 截图预览、取消与附件失败清理、QuickAdd `api.v1` 转接。
- 旧数据升级预览、原文件备份、重复执行检查与恢复前完整校验。
- 原生插件 / 原生示例库 / 旧宏库三种安装包、SHA-256、三平台 CI。
- 中英文原生教程、正式架构、原创双语 PDF 与真实应用截图。

GitHub release with native plugin, example vault and legacy starter ZIPs. Community Plugin listing is not included; install the downloaded plugin manually.

## 0.1.0 - 2026-10-04

- 从实际学习流程中提取并移植 QuickAdd 脚本，发布独立示例库。
- 截图建卡、可编辑的剪贴板建卡、卡组管理。
- PDF 学习卡、原文与必填小结、勾选生成问答卡、原文回链、书架和续读。
- 去除个人目录与专用分类，配置与输出使用库内相对路径。
- 截图标题不泄露答案，进度保存直接读取当前 PDF。
- 支持带备份的既有库安装，提供图文指南、原创 PDF 和 MIT 许可证。
