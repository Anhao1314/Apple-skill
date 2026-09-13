# Apple Product Design

用受 Apple 产品实践启发的方法，帮你定义产品、判断功能取舍和评审技术方案。输出可执行的替代方案，不只给“更简洁”的评价。

An independent Agent Skill for product definition, feature tradeoffs, and technical decision review, inspired by Apple's public product practices. Not affiliated with or endorsed by Apple Inc.

## 快速安装

在终端使用通用安装器，按提示选择你的 Agent 客户端和安装范围：

```bash
npx skills add Anhao1314/Apple-skill
```

命令需要 Node.js/npm 和网络；它调用外部安装器，本次未实际执行安装。客户端与安装器支持情况以各自当前文档为准。
安装后检查本地目录是否包含 `SKILL.md`、五个 `references/` 文件和 `assets/review-template.md`，再在客户端中确认 Skill 已被发现；必要时重新启动会话。

手动安装：

```bash
git clone https://github.com/Anhao1314/Apple-skill.git
```

将仓库内容复制到客户端文档指定的 Skill 目录中的 `apple-product-design/` 子目录，保留相对路径，排除 `.git/`。不要只复制或粘贴 `SKILL.md`：它依赖参考文件和输出模板。

## 复制这段开始使用

在已安装此 Skill 的 Agent 会话中输入：

```text
请用 apple-product-design 做一次轻量产品评审。
产品：为自由职业设计师收集客户反馈的网页工具。
核心任务：客户不用注册，就能在设计稿上标注意见；设计师集中处理反馈。
功能：匿名链接、图片标注、反馈状态、团队聊天、AI 写广告文案。
约束：独立开发，首版两周，只做网页，不接外部模型服务。
请给总判断、逐功能取舍及理由、下一步；缺失信息标为假设。
```

支持显式 Skill 调用的客户端可使用其命令选择 `apple-product-design`；其他客户端使用自然语言触发或自己的 Skill 选择界面。如果没有触发，先检查安装路径和客户端发现列表。

## 预期输出

以下是手写示范，不是模型运行记录或效果保证：

- 总判断：围绕“不注册就能反馈”建立主线，首版不同时承担聊天与文案生成。
- 保留匿名链接、图片标注和最小反馈状态；匿名指客户，不意味着设计师端无需权限。
- 暂缓团队聊天，删除首版 AI 文案：它们偏离反馈任务，外部模型也违反当前约束。
- 下一步：用一张设计稿验证客户能否不注册完成标注；链接有效期与撤回权限待确认。

完整可复制示例：[产品评审](examples/product-review.md) · [产品定义](examples/product-definition.md) · [技术方案评审](examples/technical-review.md)。示例全部使用虚构材料，输出是示范，不声称执行过测试。

## 四种使用模式

| 模式 | 给它什么 | 得到什么 |
| --- | --- | --- |
| 产品评审 | PRD、功能清单、产品方案 | 问题证据、功能取舍、替代方案、下一步 |
| 产品定义 | 用户痛点、模糊方向、资源约束 | 一句话定义、v1 边界、依赖、原型计划 |
| 方法论问答 | 明确的问题 | 相关原则、可核实案例、标注推断的回答 |
| 技术方案评审 | RFC、API/CLI、依赖清单 | 技术取舍、最小方案、兜底与验证动作 |

默认简单问题用轻量输出；完整 PRD 或“做完整评审”使用深入流程。已有材料但缺信息时先给有假设标记的初步判断，而不是要求填完长问卷。

## 运行前提与兼容性

- Agent 能加载 Skill 指令并读取同目录的参考文件与模板；本项目不限定模型品牌，也不需要 Apple 设备或 API 密钥。
- 浏览工具可选。无浏览能力时仍可分析所给材料；最新事实、历史引语、市场与竞品结论保留待核实标签。
- 不联网也不应虚构用户调查或引用。浏览工具不可用时继续可完成部分。
- 本次完成文件结构、引用路径、打包检查和场景静态审查；**尚未完成任何客户端的实际安装或独立 Agent 行为测试**。不宣称所有客户端兼容，静态检查也不等于效果验证。

## 限制

十条原则是可调整框架。80% 用户、约三个核心能力、三次重复才抽象均不是硬阈值或 Apple 官方规则。合规、安全、无障碍和专业用户需要可能要求保留低频能力。

本 Skill 不做 UI/HIG 合规，不模仿乔布斯，不负责具体编码调试。评审质量受输入材料和模型能力影响，不能代替用户研究、实际原型与领域专家判断。

## 目录

```text
apple-product-design/
├── SKILL.md
├── README.md
├── LICENSE
├── CHANGELOG.md
├── references/
│   ├── principles.md
│   ├── for-developers.md
│   ├── review-checklist.md
│   ├── cases.md
│   └── sources.md
├── assets/
│   └── review-template.md
└── examples/
    ├── product-review.md
    ├── product-definition.md
    └── technical-review.md
```

## 来源、许可与反馈

[来源与引用纪律](references/sources.md) · [版本变更](CHANGELOG.md) · [MIT 许可证](LICENSE) · [反馈问题](https://github.com/Anhao1314/Apple-skill/issues)

反馈请说明客户端与版本、Skill 版本、脱敏输入、预期与实际结果。不要附私有 PRD 或密钥。本项目为独立整理，与 Apple Inc. 无隶属、授权或背书关系；方法论推断不代表 Apple 的内部决策标准。
