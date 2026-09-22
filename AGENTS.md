# 仓库指南

## 项目结构与模块组织

本仓库发布面向中国家长的 AI skills。每个 skill 独立放在 `skills/<skill-name>/`，入口为 `SKILL.md`。将配套内容与使用它的 skill 放在一起：按需查阅的指南放入 `references/`，书籍提炼的原始内容放入 `chapters/`。`README.md` 是安装与目录页；`docs/requirements.md` 记录范围、验收案例和产品决策。

目录名使用小写 kebab-case，例如 `skills/to-teacher/`、`skills/child-social-problem-solving/`。移动或重命名 skill 时，同步更新 README 链接及所有跨 skill 引用。

## 编写风格与约定

所有面向用户的 skill 正文、示例和指引均使用中文。每个 `SKILL.md` 顶部保留 YAML front matter：`name` 必须与目录名一致，`description` 应清楚描述自然语言触发场景。使用简短的 Markdown 标题、编号流程和相对链接，例如 `references/red-lines.md`。

入口文件只写触发条件、工作流和边界。将详细清单、年龄适配和领域资料放在引用文件中，供 agent 按需加载。示例应是家长说得出口的具体表达，而非抽象建议。

## 内容安全与范围

这些 skills 服务家长，不直接服务儿童。不得提供诊断、处方、体罚、羞辱式建议或确定性断言。发现即时安全风险、疑似虐待、创伤信号、显著发育疑虑或自伤/他伤风险时，优先于日常教练建议，引导家长寻求适当的专业或紧急支持。遵守最小化隐私原则：除既定的明确保存流程外，家庭信息只保留在当前对话。

## 验证

仓库没有构建系统、格式化工具或自动化测试。提交前手动检查所有改动过的 Markdown 链接和 front matter，并从触发条件到引用文件走读完整流程。使用以下命令查找过时名称并检查 diff：

```bash
rg -n "旧-skill-名称|references/旧文件" .
git diff --check
```

变更行为时，按 `docs/requirements.md` 的相关验收案例推演，确认仍能产出可直接使用的中文话术。

## 提交与拉取请求

提交标题保持简短、祈使语气并使用句首大写；例如 `Add self-driven growth skill documentation` 或 `Refine communication guidelines for parent-teacher messages`。一个提交只聚焦一个 skill 或一项文档主题。

PR 应说明受影响的 skill、用户场景及安全或范围变化；有对应需求或 issue 时附上链接。修改 agent 行为时，提供前后输出示例并列出已做的手动验证；避免无关的格式调整。
