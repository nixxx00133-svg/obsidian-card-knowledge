# WorkBuddy 适配

## 适用入口

WorkBuddy 是腾讯的 AI Agent 桌面工作台，不是普通聊天网页。官方产品介绍列出本地文件实操、Skills 技能包扩展等能力；官方文档也说明可在用户授权的本地目录读写文件。具体菜单名称可能随版本变化。

## 使用方式

1. 在 WorkBuddy 中打开技能/Skills 管理入口，尝试导入本仓库或将 `SKILL.md` 文件夹作为技能包。若当前版本不支持从 GitHub 导入，按它支持的格式本地导入；不要只把仓库 URL 当成已经安装。
2. 在 WorkBuddy 授权访问 Obsidian vault，最好只授权需要写入的两个子目录。
3. 新任务中说明只整理自上次整理后的对话内容，并指定卡片和知识库目录。
4. 要求写入后检查每张卡片与长文的双向链接、组件、YAML 和文件名。核验 WorkBuddy 的完成报告与实际目录中的文件。

任务指令示例：

> 使用已安装的 Obsidian Card and Knowledge 技能，整理本次对话中自上次整理以来的内容。卡片写入「[卡片目录]」，知识库长文写入「[知识库目录]」。先查看现有笔记以避免重复命名；完成后检查 YAML、组件，以及卡片到知识库、知识库到卡片的双向链接，并列出实际写入的文件。

## 参考

- [WorkBuddy 官方产品介绍](https://www.workbuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Product-Guide)
- [WorkBuddy 官方站](https://www.workbuddy.ai/)
