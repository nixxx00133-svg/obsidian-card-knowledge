# Kimi 适配

## 两类入口

Kimi 网页/普通聊天适合粘贴指令并获取 Markdown；Kimi Agent 的技能面板支持发现、安装和调用 Skills，也支持通过 `/skill-creator` 对话创建自定义技能。Kimi Work 是桌面本地 Agent，可以在授权项目中读写文件。

## Kimi Agent：创建/调用 Skill

1. 在技能面板打开自定义技能创建流程；可尝试从 GitHub 获取本仓库技能文件，或将根目录 `SKILL.md` 内容作为技能说明/材料。具体导入按钮和支持的打包格式以当前客户端界面为准。
2. 若无法导入仓库目录，在对话框输入 `/skill-creator`，提供本仓库 `SKILL.md` 的完整规范并要求创建“Obsidian 卡片和知识库整理”技能。
3. 通过 `/` 选择技能，或在对话中明确说“生成卡片和知识库”。
4. 普通 Kimi 网页端如无本地文件连接器，需手动保存它输出的 Markdown。

## Kimi Work：写入本地 vault

1. 在 Kimi Work 创建/选择一个指向 Obsidian vault 的项目，并确认该目录已授权。
2. 将 `SKILL.md` 放入项目可读取的位置，或在任务中明确指定并要求先读取它。
3. 指定卡片和知识库子目录，要求写入完成后核对组件及双向链接。
4. 只在界面显示实际文件写入成功后，才把结果视为已保存。

## 参考

- [Kimi：什么是技能（Skills）](https://www.kimi.com/help/plugins-and-skills/what-are-skills)
- [Kimi：在 Agent 模式中使用技能](https://www.kimi.com/help/plugins-and-skills/use-skills-in-agent)
- [Kimi Work 官方概览](https://www.kimi.com/en/help/kimi-work/overview)
- [Kimi Work 入门指南](https://www.kimi.com/academy/kimi-work-getting-started)
