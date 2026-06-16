# Resume Rewrite Skill — 简历逐条精准改写 + 个人简介

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](https://github.com/HanGu007/workbuddy-resume-rewrite/releases)
[![Platform](https://img.shields.io/badge/platform-Any%20AI%20Agent-orange.svg)](#支持的平台)

> **让 AI 像资深 HR 一样改写简历——每一条都经过专属性自检，每一句都只属于你。**

## 这是什么？

一个**平台无关的标准化 AI Agent Skill**。将资深职业顾问的简历改写方法论提炼为 AI 可执行的指令集——不是简单"润色语言"，而是一套包含四段式改写、五大改写规则、红线禁区、四句式个人简介的完整写作体系。

**核心差异**：建立了一套**可审计的改写体系**——每条改动都有原文对照、问题分析、改动说明，改完还要通过专属性检查确保这句话只属于你。

## 功能概览

### ✍️ 四段式改写（透明可追溯）

```
▸ 原文：    保留用户原话，一字不改
▸ 问题：    这句话具体哪里弱
▸ 优化：    改写后的版本
▸ 改动说明：改了什么、为什么这样改
```

### 🚫 五大改写规则

| 规则 | 说明 |
|------|------|
| **禁用词替换** | 7 大禁用词（负责/参与/协助/配合/完成/处理/从事）→ 精确替换 |
| **数据真实性** | 有数字→保留强化；无数字→规模/结果描述，绝不编造 |
| **专属性自检** | 每条改完自问"能套在别人身上吗？"，通过才放行 |
| **段位匹配** | 应届→管理层，语气精确匹配经验段位 |
| **JD 精准匹配** | 提供目标岗位时，自动关键词嵌入 + 职责对应 + 成果对齐 |

### 📝 四句式个人简介

```
身份定位：行业 + 年限 + 核心能力方向
    ↓
核心能力：擅长什么（具体，非"沟通能力强"）
    ↓
价值主张：能给公司带来什么（结果导向）
    ↓
差异化亮点：一句有个性的补充，像真人说话
```

### 🎯 一岗一版（JD 驱动）

提供目标岗位 JD 时自动执行：
- JD 关键词自然嵌入（不硬堆）
- 相关经历优先排序
- 成果对齐 JD 关注指标
- 个人简介定向回应 JD 需求
- **同一人、不同岗位 → 完全不同的改写**

### ❌ 红线禁区

| 必须做到 | 绝对禁止 |
|---------|---------|
| 行动动词开头 | 出现"我"字 |
| STAR 叙事自然流畅 | STAR 标签词 |
| 每条 1-2 行高密度 | "任务是…"句式 |
| 量化来自用户确认 | 纯职责罗列 |
| — | 虚构任何数据 |

## 快速开始

### Open Cloud / Cloud Code

```
创建 Agent → 系统提示词粘贴 SKILL.md → 发送简历 + JD
```

### CodeEx

```bash
git clone https://github.com/HanGu007/workbuddy-resume-rewrite.git
# CodeEx → 导入本地 Skill → 选择 SKILL.md
```

### Cursor / Copilot

```bash
# Cursor
cp SKILL.md .cursor/rules/resume-rewrite.md

# GitHub Copilot
cp SKILL.md .github/copilot-instructions.md
```

### LangChain / OpenAI SDK

```python
system_prompt = open('SKILL.md', encoding='utf-8').read()
messages = [
    {"role": "system", "content": system_prompt},
    {"role": "user", "content": f"请改写这份简历：\n{resume_text}\n\n目标岗位JD：{jd_text}"}
]
```

## 支持的平台

| 平台 | 加载方式 |
|------|---------|
| Open Cloud | 系统提示词 |
| Cloud Code | 系统提示词 |
| CodeEx | 自定义 Skill 导入 |
| Cursor | `.cursor/rules/` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| LangChain | system message 注入 |
| OpenAI SDK | system message 注入 |
| Dify | 知识库 + 提示词关联 |
| Coze | 知识库 + 提示词关联 |
| 任意 LLM API | 粘贴为 system prompt |

## 改写示例

### 工作经历改写

```
▸ 原文：
   负责公司客户对接及日常维护工作

▸ 问题：
   "负责"是被动模糊词，"客户对接"看不出规模和成果——HR扫过去等于没看到

▸ 优化：
   主导华南区 23 家经销商的全周期客户管理，推动季度业务回顾机制落地，
   关键客户续约率从 72% 提升至 91%

▸ 改动说明：
   ①"负责"→"主导"（主动动词）  ②补充区域和客户规模
   ③加入具体机制名称  ④补充从 X 到 Y 的结果数据（用户确认后填入）
```

### 个人简介

```
5年快消行业渠道管理经验，深耕华南区域经销商体系搭建与客户运营。
擅长从零构建培训赋能体系，累计为超百家经销商提供标准化运营方案。
2024年主导的渠道数字化项目实现经销商订货效率提升40%，
具备从策略到落地的全链路执行能力。坚信渠道的护城河不在政策而在人。
```

## 推荐工作流

```
  ┌─────────────────┐
  │ resume-diagnosis │  ← 先诊断
  │ 找出问题         │
  └────────┬────────┘
           │
           ▼
  ┌─────────────────┐
  │ resume-rewrite   │  ← 本仓库
  │ 逐条精准改写     │
  └────────┬────────┘
           │
           ▼
  HTML 生成 → PDF 导出 → 投递
```

搭配 [resume-diagnosis](https://github.com/HanGu007/workbuddy-resume-diagnosis) 使用效果最佳。

## 目录结构

```
.
├── SKILL.md          # Skill 定义文件（核心）
├── README.md         # 本文件
└── LICENSE           # MIT
```

## 设计哲学

| 原则 | 说明 |
|------|------|
| **平台无关** | 纯文本，不锁任何平台 |
| **自包含** | 零外部依赖，一个文件就是全部 |
| **可审计** | 每条改写都有原文对照 + 问题分析 + 改动说明 |
| **真实性底线** | 绝不编造数据——这是职业道德，不是技术限制 |
| **专属性** | 强制自检——"能套在别人身上就重写" |

## 常见问题

**Q: 和 resume-diagnosis 什么关系？**
A: 诊断在前、改写在后。诊断告诉你"哪里有问题"，改写帮你"具体怎么改"。建议搭配，也可独立使用。

**Q: 改写会不会很"模板化"？**
A: 不会。专属性自检机制强制每条改写必须包含「只属于你的细节」。段位匹配确保读起来像真人。

**Q: 可以批量改写吗？**
A: 可以。SKILL.md 是无状态的指令规范，每次调用独立执行，天然支持批量。

**Q: 个人简介四句式太死板？**
A: 四句式是**底层结构**，不是表面格式。AI 会自然地融合成一段流畅文字。

**Q: 如何自定义改写规则？**
A: 直接修改 SKILL.md 中的对应章节。纯 Markdown，任何编辑器都能改。

## 贡献

欢迎提 Issue 和 PR。特别欢迎：
- 更多行业的"优秀工作描述示例"
- 新发现的"禁用词"及替换方案
- 不同经验段位的改写话术优化
- 多语言版本

## 许可证

MIT License © 2026 [HanGu007](https://github.com/HanGu007)

---

<p align="center">
  <sub>标准化 AI Agent Skill · 一次编写 · 多平台部署 · 永久开源</sub>
</p>
