# qwenwork-night-shift

🌙 **千问办公帮我值夜班，呈现 AI 行业真实原声**

每日 AI/科技媒体原声速览、31 档播客中英对照逐字稿、美股 AI 五层盘面、开发者口碑、榜单动态。

> 核心理念：**不做二手速报，只呈现原声**——英文原文 + 中文翻译，全部可点击溯源。

---

## 它是什么

这是一个运行在 [千问办公](https://qwenwork.cn) 上的日报生成 skill。每天凌晨自动抓取过去 24 小时（周一为周五 18:00 → 周一 06:00 约 60 小时）的 AI 行业动态，产出一份中英对照的「真实原声」日报，并推送到钉钉/飞书/微信群。

## 日报板块（顺序固定）

1. **播客制作状态** — 打开第一眼
2. **高影响力人物观点（X 原声）** — 用已登录的 X 会话按 `from:handle` 逐一检索约 50 位 AI 学者/高管/VC/分析师
3. **科技媒体速览** — TechCrunch / The Verge / Ars Technica / MIT Tech Review / Wired / Reuters / Bloomberg / The Information / Stratechery / Semafor / FT / Economist
4. **夜间专属 · AI 五层盘面** — 按黄仁勋「AI 五层蛋糕」（能源→芯片→云→模型→应用）组织的美股盘面面板，含七姐妹全覆盖条、韩系存储、Cerebras、Neocloud、SaaS 单列
5. **播客精华** — 每集「一段总结 + 超链接」，跳转独立中英对照逐字稿
6. **开发者口碑** — Hacker News / Reddit / GitHub Trending / HuggingFace Trending
7. **AI 与人文**（哲学·艺术）
8. **开源与模型榜单** — GitHub Trending / HF 热门 / Product Hunt / LMSYS Arena
9. **桌面下的信号** — 唯一分析板块：综合盘面+播客+X 原声+投行观点，每条标注来源类型
10. **产品更新**

## 播客监测名单（31 档）

| 类别 | 播客 | 数量 |
|---|---|---|
| AI / 科技 | Acquired · The AI Daily Brief · Dwarkesh Podcast · Latent Space · No Priors · AI + a16z · Lex Fridman Podcast · Practical AI | 8 |
| AI 基础设施 | SemiAnalysis · Gradient Dissent | 2 |
| 商业 / 创业 | How I Built This · My First Million · Masters of Scale · The Tim Ferriss Show · Lenny's Podcast | 5 |
| 投资 | All-In Podcast · Invest Like the Best · 20VC · Bloomberg Odd Lots · In Good Company (NBIM) | 5 |
| 科技产业评论 | Hard Fork · Stratechery (Sharp Tech) · The Vergecast · Prof G Pod | 4 |
| 科学 / 健康 | Huberman Lab · Huberman Lab Clips · The Diary Of A CEO | 3 |
| 认知 | The Knowledge Project | 1 |
| 中国 / 亚洲 | Sinica Podcast · ChinaTalk | 2 |
| 企业 AI 落地 | The AI in Business Podcast | 1 |

## 核心规则（强制）

- **只用英文信源**：官方 IR 页、财报电话会 transcript、X、英文科技媒体等；禁止国内信息源。英文原文抓回后翻译成中文，形成双语对照。
- **时间窗**：周二至周五「过去 24 小时」；周一「北京时间上周五 18:00 → 本周一 06:00」。
- **逐一搜索**：人物名单逐个检索，窗口内无新发言者如实标注「今日暂无」，禁止旧闻顶替。
- **ASR 真实性**：RSS show notes 不是逐字稿——有音频 enclosure 的集必须下载音频跑真实 whisper ASR，禁止拿介绍文字冒充；纯文字刊物（SemiAnalysis 文章、Latent Space 通讯等）除外并标注「文字刊物」。
- **股价真实**：一律用 Yahoo Finance 浏览器抓取真实收盘价，不凭记忆编。
- **引用超链接化**：人物原声、媒体标题、层信号、财报引用附可点击英文原文链接。
- **防中断**：单源失败标「今日暂无」继续，绝不中断整体。

## 输出格式

- **HTML 主格式**：品牌色 #41D87E、手机自适应、卡片式点击展开（原生 `<details>/<summary>`，微信内置浏览器原生支持）
- **Markdown 群发版**：纯文本，可直接粘贴到钉钉/飞书/微信群
- **推送**：Markdown + HTML 链接推到钉钉/飞书/微信群

## 如何使用

把本仓库的 `SKILL.md` 放入千问办公的 skills 目录（`~/.qwenworkcn/skills/night-shift-brief/SKILL.md`），即可在千问办公中触发「夜班日报」生成。

## 品牌

- 主色 `#41D87E`
- 报头：「千问办公帮我值夜班，呈现 AI 行业真实原声」+ 日期
- 页尾：本日报由千问办公自动生成。千问办公——专业人士，都用千问办公。

---

*Powered by [千问办公 QwenWork](https://qwenwork.cn)*
