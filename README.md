# parent-skills —— 给中国家长的 AI Skills

一组面向真实家庭情境的中文 AI skills：既帮助家长与老师沟通、和孩子对话，也提供以尊重、边界和专业转介为前提的育儿与家庭知识框架。

项目服务的是家长，而不是让孩子直接与 AI 对话。目标不是输出漂亮的模板，而是在需要开口的时刻，给出家长能说得出口、孩子或老师能听得进去的支持。

## 包含什么

### 沟通工具

| Skill | 适用场景 | 能提供什么 |
| --- | --- | --- |
| [`parent-setup`](skills/parent-setup/SKILL.md) | 首次使用、设置或保存家庭信息 | 通过一轮中文采访收集家长、孩子、老师与家庭教育上下文，供后续沟通使用 |
| [`to-teacher`](skills/to-teacher/SKILL.md) | 给老师写消息、请假、询问成绩、修改草稿、回复老师 | 起草可直接发送的消息；识别日常合作与人身伤害、羞辱、歧视等红线情形，并给出下一步沟通建议 |
| [`to-child`](skills/to-child/SKILL.md) | 回答孩子的难题、处理磨蹭/撒谎/发脾气/冲突、建立规则与习惯 | 提供年龄适配的家长话术与长期策略；识别创伤、虐待或发育疑虑等需要专业支持的信号 |

`parent-setup` 不是必经步骤：若家长直接开始提问，`to-teacher` 和 `to-child` 会在缺少必要信息时简要追问。先完成设置则能让后续建议更贴合孩子年龄、家庭规则和沟通渠道。

### 育儿与家庭知识库

| Skill | 主题 | 使用重点 |
| --- | --- | --- |
| [`positive-discipline`](skills/positive-discipline/SKILL.md) | 《正面管教（修订版）》 | 归属感、鼓励、共同解决问题、家庭会议，以及“和善而坚定”的界限 |
| [`seeing-children`](skills/seeing-children/SKILL.md) | 《看见孩子》 | 情绪联结、羞耻修复、坚定边界；适用于发脾气、对抗、手足冲突、焦虑、自信、分离和睡眠等情境 |
| [`taking-charge-of-adhd`](skills/taking-charge-of-adhd/SKILL.md) | 《如何养育多动症孩子》 | 评估准备、家庭行为计划、学校协作、执行功能支持，以及与临床团队沟通的准备 |
| [`spark-the-brain`](skills/spark-the-brain/SKILL.md) | 《运动改造大脑》 | 谨慎地把运动与学习、压力、情绪、注意力、健康老化和习惯设计联系起来 |
| [`child-social-problem-solving`](skills/child-social-problem-solving/SKILL.md) | 《如何培养孩子的社会能力》 | 用“我能解决问题”（ICPS）培养孩子处理冲突、分享、轮流、公平、挫折与害羞等日常社会问题的思考能力 |
| [`self-driven-growth`](skills/self-driven-growth/SKILL.md) | 《自驱型成长》及《自驱型成长·实践篇》 | 以控制感、顾问型父母、非焦虑临在、共情沟通与励志访谈支持儿童和青少年的自主成长 |
| [`nonviolent-communication`](skills/nonviolent-communication/SKILL.md) | 《非暴力沟通（修订版）》 | 以观察、感受、需要、请求和同理心处理指责、拒绝、愤怒、边界与冲突 |
| [`happy-marriage`](skills/happy-marriage/SKILL.md) | 《幸福的婚姻（全新升级版）》 | 用戈特曼七大法则处理夫妻冲突、姻亲、金钱、家务、育儿分工与为人父母后的疏离；识别末日四骑士并优先转介家暴等专业风险 |

这些知识库用于帮助 AI 找到合适的框架和实践建议；它们不替代诊断、治疗、药物调整或紧急安全判断。

## 快速开始

### 1. 安装需要的 skills

前提：已安装支持 agents skills 的 AI 工具，例如 [ZCode](https://zcode.dev)。以下示例使用该约定的 `~/.agents/skills` 目录；若你的工具使用其他 skills 目录，请按它的文档替换目标路径。

```bash
git clone <本仓库地址> ~/parent-skills
mkdir -p ~/.agents/skills

# 沟通工具：通常建议一起安装
ln -s ~/parent-skills/skills/parent-setup ~/.agents/skills/parent-setup
ln -s ~/parent-skills/skills/to-teacher ~/.agents/skills/to-teacher
ln -s ~/parent-skills/skills/to-child ~/.agents/skills/to-child

# 按需安装知识库
ln -s ~/parent-skills/skills/positive-discipline ~/.agents/skills/positive-discipline
ln -s ~/parent-skills/skills/seeing-children ~/.agents/skills/seeing-children
ln -s ~/parent-skills/skills/taking-charge-of-adhd ~/.agents/skills/taking-charge-of-adhd
ln -s ~/parent-skills/skills/spark-the-brain ~/.agents/skills/spark-the-brain
ln -s ~/parent-skills/skills/child-social-problem-solving ~/.agents/skills/child-social-problem-solving
ln -s ~/parent-skills/skills/self-driven-growth ~/.agents/skills/self-driven-growth
ln -s ~/parent-skills/skills/nonviolent-communication ~/.agents/skills/nonviolent-communication
ln -s ~/parent-skills/skills/happy-marriage ~/.agents/skills/happy-marriage
```

若目录中已有同名链接或文件，请先确认其指向和用途，再决定是否替换；不要盲目覆盖已有配置。

### 2. 用自然语言开始

安装后直接向 AI 描述你的情境即可。例如：

- “帮我设置家长信息。”
- “帮我给班主任写条请假消息。”
- “老师这样回复是什么意思？我该怎么回？”
- “孩子问人死后去了哪里，我不知道怎么答。”
- “孩子每天写作业磨蹭，怎么和他定规则？”
- “想了解怎样用正面管教处理权力之争。”
- “孩子疑似 ADHD，去评估前要准备什么？”
- “运动怎样帮助孩子在学习前进入状态？”
- “孩子总抢同伴玩具，怎样引导他自己想办法解决？”
- “孩子不愿意练琴，我怎样从控制转为支持他的自主性？”
- “有了孩子后总为家务和管教方式吵架，怎么谈？”

## 设计原则与边界

- **隐私默认最小化。** 家庭信息默认只留在当前对话；仅当家长明确说“保存”时，`parent-setup` 才会写入本机的 `~/.parent-skills/profile.md`。
- **对老师：关系优先，也不回避红线。** 日常情境优先合作、核实和可持续沟通；涉及人身伤害、羞辱或歧视时，转为取证、书面留痕和阶梯式升级的建议。
- **对孩子：先联结，再纠正；和善且坚定。** 默认不提供体罚、羞辱或把孩子标签化的做法。规则可以清晰，执行也可以坚定。
- **对伴侣：技巧让位于安全。** 婚姻改善建议只适用于基本安全的关系；存在暴力、胁迫或控制时，优先安全与专业支持，不输出婚姻结局的预测或诊断。
- **遇到安全或专业风险，先转介。** 疑似虐待、持续创伤反应、显著发育差异、自伤/他伤风险、严重精神或身体症状等，需要优先保障安全并联系合适的专业服务。
- **建议为家长而写。** `to-child` 输出的是家长可转述和执行的话术，不面向孩子直接对话。

## 项目结构

```text
parent-skills/
├── skills/
│   ├── parent-setup/            # 家庭上下文采访与可选本地保存
│   ├── to-teacher/              # 家校沟通；含严重度与话术参考
│   ├── to-child/                # 亲子沟通；含年龄、红线与话术参考
│   ├── positive-discipline/     # 《正面管教》知识库与章节
│   ├── seeing-children/         # 《看见孩子》知识库与章节
│   ├── taking-charge-of-adhd/   # ADHD 家庭支持知识库与章节
│   ├── spark-the-brain/         # 运动与大脑知识库与章节
│   ├── child-social-problem-solving/ # 儿童社会问题解决（ICPS）知识库与章节
│   ├── self-driven-growth/      # 自主成长与顾问型父母知识库与章节
│   ├── nonviolent-communication/ # 非暴力沟通知识库与章节
│   └── happy-marriage/           # 幸福的婚姻知识库与章节
├── docs/
│   └── requirements.md          # 沟通工具的需求与范围记录
└── README.md
```

## 当前范围

沟通工具的详细需求、验收案例与后续方向见 [`docs/requirements.md`](docs/requirements.md)。其中复盘案例库、沟通演练、一键安装、动态观察存储、孩子直接使用 AI，以及更完整的其他年龄段内容，仍属于后续方向，并非当前功能。

## 贡献与使用提醒

本项目的核心是让 AI 在真实家庭情境下给出可靠、可执行且不越界的支持。新增或修改内容时，请保持中文、避免把教育或健康信息写成诊断与处方，并将安全风险和专业转介置于技巧建议之前。
