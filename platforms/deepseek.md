# DeepSeek 适配

## 适用入口

DeepSeek 普通网页/客户端对话适合按提示词整理内容；它与 DeepSeek Harness 桌面端是不同入口。DeepSeek 官方目前介绍 Harness 支持后台任务和本地文件读写，并可通过插件扩展能力。

## 普通 DeepSeek 对话

1. 将根目录 `SKILL.md` 粘贴或上传到当前对话，或将其压缩/摘录到可用的自定义指令中。
2. 说明卡片与知识库长文分别保存到哪个目录。
3. 说“生成卡片和知识库”。
4. 若当前对话没有本地文件写入工具，让它分文件输出 Markdown，并自行保存到 Obsidian。

## DeepSeek Harness

在 Harness 桌面端中，先把 vault 或目标笔记文件夹加入其可访问范围，再提供 `SKILL.md` 作为项目规则/任务上下文，明确要求按本仓库规范整理并写入对应目录。Harness 官方页面说明本地文件读写能力，但公开说明未确认其可直接安装 Agent Skills 目录或识别此仓库的 `SKILL.md` 为可调用技能。因此本适配采用“项目说明 + 明确任务”的方式；只有在你的 Harness 版本提供插件/技能导入入口时，才按其界面安装，不要假设直接复制即可。

建议任务开头：

> 先读取我提供的 SKILL.md，并将其作为本次任务的整理规范。只处理自上次整理以来的对话内容。把卡片写入「[卡片目录]」，知识库长文写入「[知识库目录]」，完成后检查 YAML、组件、文件名和双向链接目标，并报告实际创建或修改的文件。

## 参考

- [DeepSeek Harness 官方介绍](https://www.deepseek.com/zh/harness/)
- [DeepSeek 下载页：Harness 桌面端](https://www.deepseek.com/download/)
