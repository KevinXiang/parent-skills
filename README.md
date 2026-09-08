# parent-skills —— 家长老师沟通 AI 助手

帮中国家长和老师沟通的一套 AI skills：**代笔**（把你的真实意图写成一条得体、敢发的消息）和**接招**（读懂老师的回复，建议下一步怎么回）。

包含两个 skills：

| skill | 作用 |
|---|---|
| `parent-setup` | 一轮中文采访，收集家里基本情况（家长/孩子/老师与沟通渠道） |
| `to-teacher` | 沟通助手：写消息、改草稿、分析老师回复并建议下一步 |

自动区分日常沟通（合作档：关系优先）与人身伤害/羞辱/歧视等红线情形（取证留痕、按 科任老师 → 班主任 → 年级组长 → 校长 → 教育局 的阶梯升级）。

## 安装（手动，两条命令）

前提：已安装 [ZCode](https://zcode.dev) 或其他兼容 agents skills 的 AI 工具。

```bash
git clone <本仓库地址> ~/parent-skills
ln -s ~/parent-skills/skills/parent-setup ~/.agents/skills/parent-setup
ln -s ~/parent-skills/skills/to-teacher ~/.agents/skills/to-teacher
```

装好后对 AI 说"帮我设置家长信息"或"帮我给老师写条消息"即可触发。

## 隐私

- 你的家庭信息默认**只保留在当前对话中**，不写任何文件。
- 只有你明确说"保存"时，才会写入 `~/.parent-skills/profile.md`（存在你自己的电脑上）。

## 目录结构

```
parent-skills/
  skills/
    parent-setup/SKILL.md
    to-teacher/SKILL.md
    to-teacher/references/   # 严重度分级、升级阶梯、话术原则
  docs/requirements.md       # 需求文档
  README.md                  # 本文件
```
