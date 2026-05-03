# ARB — 发布商变现准备度平台

[![策略优先](https://img.shields.io/badge/%E7%AD%96%E7%95%A5%E4%BC%98%E5%85%88-Policy%20First-1f6feb)](#为什么使用-arb)
[![文档优先](https://img.shields.io/badge/%E6%96%87%E6%A1%A3%E4%BC%98%E5%85%88-Documentation%20First-0f766e)](#仓库结构)
[![双语支持](https://img.shields.io/badge/%E5%8F%8C%E8%AF%AD%E6%94%AF%E6%8C%81-English%20%7C%20%E4%B8%AD%E6%96%87-8b5cf6)](./README.md)
[![核心用途](https://img.shields.io/badge/%E6%A0%B8%E5%BF%83%E7%94%A8%E9%80%94-AdSense%20Readiness-f59e0b)](#arb-能做什么)
[![覆盖范围](https://img.shields.io/badge/%E8%A6%86%E7%9B%96%E8%8C%83%E5%9B%B4-Core%2079%20%7C%20Full%20105-374151)](#评分范围)

[English](./README.md) | 中文

ARB 是一个以文档为中心的网站审核框架，用来评估网站是否具备 AdSense 审核准备度，以及更广义的发布商变现准备度。它将基准模型、固定评分契约和 26 个技能工作流组合在一起，覆盖诊断、修复、复核、监控与拒审恢复。

整个框架围绕 6 个评分类目展开，默认使用固定的 Core 79 基线检查集，也支持扩展到完整的 105 项基准，并通过 veto 硬性否决规则保证高风险问题不会被平均分掩盖。

## ARB 能做什么

- 把发布商准备度审核标准化为有证据支撑的检查流程。
- 提供从首次审计到重新提交前复核的完整工作路径。
- 同时支持快速排查和全量深度审计。
- 输出结构化结果，便于做报告、修复计划和后续复审。
- 在需要时扩展到多广告网络准备度、竞品基准和收益优先级分析。

## 适用对象

- 准备首次提交 AdSense 的站长。
- 想在重提之前降低拒审风险的运营者。
- 需要批量审核站点的顾问或代理机构。
- 希望用统一审计契约替代随意人工评估的团队。

## 为什么使用 ARB

ARB 的设计基于三个前提：

1. 高风险政策问题必须尽早拦截。
2. 审计输出必须可复现、可追溯。
3. 不同网站类型要有不同权重，但不能破坏统一的基础评分契约。

因此，ARB 采用：

- 4 个审核 Gate。
- 6 个评分支柱：CI、PC、TH、UX、TD、SI。
- 3 种评分模式：Core 79、Core 79 + Profile、Full 105。
- 针对关键风险的 veto 优先级。

## 仓库结构

| 路径 | 作用 |
|------|------|
| [ARB-benchmark.md](ARB-benchmark.md) | 全部检查项定义、评分规则、站点类型扩展配置和报告要求的唯一基准 |
| [skills/README.md](skills/README.md) | 技能地图和调用路径说明 |
| [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md) | 大多数用户的最佳起点 |
| [AGENTS.md](AGENTS.md) | 贡献者与代理执行质量要求 |
| [skills/](skills/) | 各类审核、修复、监控和恢复技能 |

## 核心概念

### 1. 六大支柱

| 代码 | 支柱 | 关注点 |
|------|------|--------|
| CI | Content Integrity | 原创性、深度、结构、更新频率 |
| PC | Policy Compliance | 禁止内容、披露、数据权利 |
| TH | Technical Health | HTTPS、性能、抓取、标记化 |
| UX | User Experience | 导航、可读性、无障碍、广告干扰 |
| TD | Trust & Disclosure | 法务页面、身份透明、商业可信度、编辑可信度 |
| SI | Search Integrity | 反垃圾、链接质量、SEO 合规 |

### 2. 评分范围

| 模式 | 适用场景 | 覆盖范围 |
|------|----------|----------|
| `Core 79` | 快速基线排查 | 仅固定基线检查项 |
| `Core 79 + Profile` | 常规单站审计 | Core 79 加站点类型扩展项与触发项 |
| `Full 105` | 混合型站点或对外交付审计 | 完整基准范围 |

### 3. Veto 否决规则

如果关键阻断项失败，准备度不能判定为通过。至少应把下列情况视为硬性阻断：

- TH01：全站未启用 HTTPS
- TD01：缺少隐私政策
- 任意 PC 项存在未解决的 Fail
- 联盟披露存在冲突且无法用证据澄清

详细规则请查看 [ARB-benchmark.md](ARB-benchmark.md)。

## 完整使用文档

### 前置条件

这个仓库是以文档为中心的框架，不提供独立 CLI 或打包好的扫描器。实际使用方式是在编辑器或代理环境中打开并执行这些 benchmark 与 skill 文档。

推荐准备：

- 支持 Markdown 的编辑器，例如 VS Code
- 目标站点 URL、源码文件，或两者同时具备
- 能记录证据的方式，例如截图、页面链接、抓取记录、示例片段

### 最快开始方式

在仓库根目录执行：

```bash
open ./skills/arb-full-audit/SKILL.md
open ./ARB-benchmark.md
open ./skills/README.md
```

如果你只想先做快速排查，而不是完整工作流：

```bash
open ./skills/ads-readiness-assessment/SKILL.md
```

### 标准工作流

大多数审核建议按以下路径执行：

1. 明确站点 URL、站点类型和评分模式。
2. 从 [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md) 开始。
3. 执行 Gate 1 技术基线检查。
4. 执行 Gate 2 内容、政策、垃圾与版权检查。
5. 执行 Gate 3 信任、体验和披露检查。
6. 汇总评分，应用 veto 逻辑，并整理优先修复项。
7. 进入对应的修复技能。
8. 最后使用 [skills/resubmission-readiness-check/SKILL.md](skills/resubmission-readiness-check/SKILL.md) 做提交前复核。

### 手动分 Gate 使用方式

如果你想精细控制每个阶段，可以按下面使用：

| Gate | 目标 | 主要技能 |
|------|------|----------|
| Gate 1 | 技术基线 | `technical-audit` |
| Gate 2 | 内容、政策与垃圾风险 | `ads-readiness-assessment`、`content-audit`、`policy-risk-scanner`、`seo-spam-detection`、`copyright-ip-check` |
| Gate 3 | 信任、体验与披露 | `ux-compliance-audit`、`trust-credibility-strategy`、`affiliate-link-compliance` |
| Gate 4 | 修复与最终校验 | `content-improvement-blueprint`、`technical-remediation-guide`、`ux-optimization-roadmap`、`policy-remediation-plan`、`resubmission-readiness-check` |

### 如何选择入口技能

| 场景 | 建议起点 |
|------|----------|
| 首次做完整审计 | `arb-full-audit` |
| 快速初筛 | `ads-readiness-assessment` |
| 先看技术阻断项 | `technical-audit` |
| 联盟链接占比较高 | `affiliate-link-compliance` |
| 拒审原因分析 | `rejection-root-cause-analysis` |
| 审核通过后的持续监控 | `active-compliance-monitor` |
| 代理机构批量评估 | `agency-batch-auditor` |

### 开始前建议准备的输入

| 输入项 | 是否必需 | 说明 |
|------|----------|------|
| 站点 URL | 通常必需 | 需要完整协议头 |
| 站点类型 | 评分时必需 | blog、tool、affiliate、news、ecommerce、forum |
| 评分模式 | 强烈建议提供 | `Core 79`、`Core 79 + Profile`、`Full 105` |
| 流量层级 | 可选 | 对基准与收益扩展更有帮助 |
| 目标广告网络 | 可选 | 用于 AdSense 之外的准备度评估 |
| 证据材料 | 强烈建议 | 截图、链接、示例、抓取观察 |

### 支持的审查方式

大多数技能都支持以下一种或多种方式：

- URL 模式：直接检查线上网站。
- Source 模式：检查本地项目源码。
- Manual 模式：按清单人工核验并记录结果。

各技能支持矩阵见 [skills/README.md](skills/README.md)。

## 你应该得到哪些输出

一次完整审计通常应输出：

- 明确声明的评分模式和评估范围
- CI、PC、TH、UX、TD、SI 六个支柱分数
- veto 状态和中止条件
- 对所有非 Pass 项的证据化说明
- 优先级修复列表
- 下一步建议技能
- 可选的通过概率估计和多网络差距分析

推荐沉淀以下产物：

| 产物 | 价值 |
|------|------|
| Markdown 审计报告 | 便于阅读与共享 |
| JSON 评分卡 | 便于聚合、对比和自动化处理 |
| 证据笔记 | 便于复现 |
| 修复计划 | 便于推进整改 |

## 典型使用路径

### 站长自查

1. 从 `arb-full-audit` 开始。
2. 先修复优先级最高的阻断项。
3. 再跑 `resubmission-readiness-check`。
4. 所有接近 veto 的问题都清理完后再提交。

### 顾问或代理机构

1. 多站点使用 `agency-batch-auditor` 做入口。
2. 对重点站点使用 `arb-full-audit` 深挖。
3. 将问题转换为客户整改路线。
4. 交付前或重提前做定向复检。

### 被拒审后的恢复路径

1. 从 `rejection-root-cause-analysis` 开始。
2. 用 `recovery-action-plan` 排整改顺序。
3. 进入与失败支柱对应的修复技能。
4. 最后用 `resubmission-readiness-check` 收口。

## 技能分组

### 编排层

- `arb-full-audit`

### 诊断层

- `ads-readiness-assessment`
- `content-audit`
- `technical-audit`
- `ux-compliance-audit`
- `policy-risk-scanner`

### 修复层

- `content-improvement-blueprint`
- `technical-remediation-guide`
- `ux-optimization-roadmap`
- `policy-remediation-plan`
- `trust-credibility-strategy`

### 跨阶段检查

- `affiliate-link-compliance`
- `copyright-ip-check`
- `seo-spam-detection`

### 监控与恢复

- `active-compliance-monitor`
- `health-check-automation`
- `alert-rules-setup`
- `rejection-root-cause-analysis`
- `recovery-action-plan`
- `appeal-strategy-builder`
- `resubmission-readiness-check`

### 扩展能力

- `ai-content-compliance`
- `multi-network-readiness`
- `revenue-potential-estimator`
- `geo-localization-compliance`
- `competitive-benchmark`
- `agency-batch-auditor`

## 推荐阅读顺序

如果你第一次接触这个仓库，建议按下面顺序看：

1. [README.md](README.md)
2. [ARB-benchmark.md](ARB-benchmark.md)
3. [skills/README.md](skills/README.md)
4. [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md)
5. 你准备实际使用的具体技能文档

## 使用规则

在使用或扩展 ARB 时，建议始终遵守：

- 不要编造证据。
- 不要压制 veto 信号。
- 不要在未声明的情况下切换评分范围。
- 不要因为加权总分高就直接判定站点已准备好。
- 要保证结论可复现、可追踪。

更详细的执行契约见 [AGENTS.md](AGENTS.md)。

## 常见问题

### 这是软件产品还是文档框架？

它是一个文档优先的框架，定义了基准、评分模型、技能工作流和输出要求。

### 可以不评估全部 105 项吗？

可以。需要更快或更聚焦时，可以从 `Core 79` 或 `Core 79 + Profile` 开始。

### 是否总要从 `arb-full-audit` 开始？

对大多数用户来说是的。只有在你已经明确知道问题集中在哪个方向时，才建议先用专项技能。

### 高分是否等于一定通过？

不是。ARB 只能帮助你降低风险，不能替代官方审核结果。

## 相关文档

- [README.md](README.md)
- [ARB-benchmark.md](ARB-benchmark.md)
- [skills/README.md](skills/README.md)
- [skills/arb-full-audit/SKILL.md](skills/arb-full-audit/SKILL.md)