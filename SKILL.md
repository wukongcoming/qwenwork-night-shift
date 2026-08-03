---
name: night-shift-brief
description: 生成「千问办公帮我值夜班，呈现AI行业真实原声」日报——每日科技媒体原声速览、播客中英对照逐字稿、开发者口碑、榜单动态。当用户要求生成夜班日报、媒体监测简报、每日科技舆情、或提到"夜班""夜班模版""媒体口碑"时触发。
version: 2.2.0
---

# 千问办公帮我值夜班，呈现AI行业真实原声 · 日报生成规范

## 定位
每天凌晨 5:00 云端自动开始抓取制作。主题：「千问办公帮我值夜班，呈现AI行业真实原声」——突出原声和真实感，不做一般媒体的二手速报，直接呈现原文/原话/原文标题+中文翻译。播客逐字稿在你打开电脑时本地 ASR 制作，做好后整合推送。

## 板块呈现规则（v1.4）
- **人物观点**：必须用浏览器（用户已登录的 X 会话）按 `x.com/search?q=(from:handle OR ...) since:YYYY-MM-DD&f=live` 逐一检索名单人物，提取英文原帖+互动量；无新帖者如实标注。
- **美股板块**：按黄仁勋"AI 五层蛋糕"（能源→芯片→云与基础设施→模型→应用）做成一屏可见的财经软件式盘面面板（双列网格、紧凑 ticker 行、红绿涨跌、每层附层信号），顶部必须有"七姐妹 Mag 7"全覆盖条（AAPL/MSFT/NVDA/GOOGL/AMZN/META/TSLA 周五收盘价+涨跌幅）。芯片层必须覆盖高关注公司：韩系存储（SK 海力士 000660.KS、三星 005930.KS，含周一亚洲盘数据）、Cerebras（CBRS）、AVGO/ASML 等；云层含 Neocloud（CRWV/NBIS/IREN/APLD）；BABA 归云层，驱动力涉及模型层时在备注说明。传统软件（SaaS：CRM/SAP/NOW/WDAY/HUBS/DDOG/SNOW/MDB/INTU/PLTR/ADBE）单列，个股附公司新闻与距 52 周高点回撤幅度。股价一律用 Yahoo Finance 浏览器抓取真实收盘价。
- **引用来源超链接化**：人物原声、媒体标题、层信号、财报引用等处尽量附可点击的英文原文链接，方便媒体查证。
- **播客板块格式**：每集"一段总结 + 超链接"，点击跳转到独立的中英对照逐字稿文件（文件名：podcast-{节目}-{主题}-中英逐字稿.md），逐字稿含时间戳、英文原声、中文翻译。
- **分析板块命名为「桌面下的信号」**：综合盘面变化、播客内容、X 原声与外部观点（投行/分析师），每条信号标注来源类型标签（盘面/播客/X/投行），呈现"表面之下正在发生什么"。

## 信源与时间窗规则（强制）
- **信源**：板块一/三/四/六/七的原声内容一律使用**英文信源**（官方 IR 页、财报电话会 transcript、X/Twitter、TechCrunch、The Verge、Reuters、Bloomberg、Ars Technica、Wired、FT、官方博客等），**禁止引用国内信息源**（新浪、搜狐、网易、百家号、知乎、雪球、36氪、澎湃等）。抓取到英文原文后由 agent 翻译成中文，形成英文原文+中文翻译的双语对照。国内财经媒体（如华尔街见闻）仅可用于盘面数字的交叉验证，不得作为人物原声来源。
- **时间窗**：周二至周五的日报抓取「过去 24 小时」；**周一的日报抓取「北京时间上周五 18:00 → 本周一 06:00」**（约 60 小时，覆盖美股周五盘面、财报电话会与周末发言）。
- **逐一搜索**：板块一须对人物名单逐一发起搜索，不可只呈现少数人；窗口内无公开新发言者标注「今日暂无」，不得用旧闻顶替。
- 播客逐字稿制作完毕后，须自动刷新日报 HTML/Markdown 并重新推送钉钉/飞书，同时通知用户。

## 输出格式
- **主格式**：HTML 文件（品牌色 #41D87E 排版，手机自适应，表格美观，中英对照清晰，内容可复制，**卡片式折叠——点击条目展开/收起详情**，适配微信/钉钉/飞书内置浏览器）
- **群发格式**：Markdown 纯文本（可直接粘贴到钉钉/飞书/微信群，媒体复制即用，无格式依赖）
- **辅助格式**：今日速览海报图片（3-5 条今日头条 + 品牌元素，用于 IM 群吸引点击）
- **推送方式**：海报+Markdown 文本推送到钉钉/飞书群；HTML 通过链接推送

## HTML 交互规范（点击看详情，强制）
日报 HTML 必须支持「点击展开详情」的手机阅读交互，实现方式与默认状态如下：

1. **卡片式折叠**：每条内容（人物观点/媒体条目/论文/播客逐字稿/帖子）用原生 `<details>/<summary>` 实现。折叠态显示标题+一句话摘要，点击展开完整中英对照原文。不用外部 JS 库——微信内置浏览器（iOS WKWebView / Android X5）原生支持，JS 被禁用时内容仍可读。
2. **默认展开/折叠策略**：
   - 默认展开：板块九「共识与非共识」（唯一分析板块，是阅读重点）
   - 默认折叠：板块五播客逐字稿（篇幅最长）、板块八榜单表格
   - 其余条目默认折叠，只露标题+摘要行，吸引点击
3. **全局控件**：顶部工具条提供「全部展开 / 全部收起」按钮；右下角「回到顶部」浮动按钮；板块标题带锚点导航。
4. **交互细节**：summary 右侧 chevron 随展开旋转；展开内容 0.2s 淡入下滑动画；整行可点击，最小点击高度 44px（手机拇指友好）。
5. **微信兼容**：单文件内联 CSS/JS；不用 localStorage；字体用系统字体栈 + 品牌字体 fallback（微信内 webfont 加载慢）；托管链接必须 https。

卡片参考结构：
```html
<details class="card">
  <summary>
    <span class="card-title"><strong>{English Title}</strong><span class="zh">{中文标题翻译}</span></span>
    <span class="chevron">▾</span>
  </summary>
  <div class="card-body">
    <p class="en">{English original…}</p>
    <p class="zh">{中文翻译…}</p>
    <p class="source"><a href="{link}">{Source}</a></p>
  </div>
</details>
```

全局展开/收起参考 JS：
```html
<script>
document.getElementById('expandAll').onclick=()=>document.querySelectorAll('details.card').forEach(d=>d.open=true);
document.getElementById('collapseAll').onclick=()=>document.querySelectorAll('details.card').forEach(d=>d.open=false);
</script>
```

## 日报板块顺序与规范

### 一、高影响力人物观点
> 直接引用原话，不二次加工

人物分组（不分国籍）：
- AI 学者/研究员：Andrew Ng、Yann LeCun、Andrej Karpathy、Fei-Fei Li、Geoffrey Hinton、Yoshua Bengio、Pieter Abbeel、Sebastian Raschka、Jim Fan、Lilian Weng、Percy Liang、Jürgen Schmidhuber、Stuart Russell、Timnit Gebru、Emily Bender、Gary Marcus、Melanie Mitchell、Eliezer Yudkowsky、Bindu Reddy、Clementine Delangue
- AI 公司高管：Sam Altman、Greg Brockman、Dario Amodei、Demis Hassabis、Sundar Pichai、Jensen Huang、Mark Zuckerberg、Elon Musk、Aidan Gomez、Arthur Mensch、Clem Delangue、Thomas Wolf、Aravind Srinivas、Satya Nadella、Lisa Su、Pat Gelsinger
- 投资人/VC：Tomasz Tunguz、Marc Andreessen、Sarah Tavel、Connie Chan、Anjney Midha、Vinod Khosla、Reid Hoffman、Chamath Palihapitiya、Patrick O'Shaughnessy、Bill Gurley、Mary Meeker
- 独立分析师：Ben Thompson、Casey Newton、Kevin Roose、Kara Swisher、Alex Kantrowitz、Will Knight、Khari Johnson、Dylan Patel (SemiAnalysis)

格式：每条直接引用英文原话（引用格式），下方中文翻译，附 X/Twitter 链接。

---

### 二、播客正在制作中（状态提示）
> 用户打开日报第一眼看到的内容

```
🎧 千问值夜班 — 播客逐字稿制作中

31 档播客的最新一期正在本地进行语音识别和中英对照翻译。
完成后将自动整合到本日报的「播客精华」板块。

今日正在处理的播客：
- {播客名1}
- {播客名2}
- ...

完成后将在千问办公中通知您。
```

说明：如果播客已处理好，此板块显示「✅ 播客逐字稿已就绪，请见第五板块」并列出已完成的播客名。

---

### 三、科技媒体速览（中英对照原声）
> 直接呈现原文标题+摘要和中文翻译，不总结不提炼

格式：每条包含英文原文标题（加粗）、英文一句话摘要、中文标题翻译、中文摘要翻译、来源链接。

```html
<div class="media-item">
  <p class="en-title"><strong>{English Title}</strong></p>
  <p class="en-summary">{English one-line summary}</p>
  <p class="zh-title">{中文标题翻译}</p>
  <p class="zh-summary">{中文摘要翻译}</p>
  <p class="source"><a href="{link}">{Source}</a></p>
</div>
```

监测来源（12家国际科技媒体）：
TechCrunch、The Verge、Ars Technica、MIT Technology Review、Wired、Reuters Tech、Bloomberg Tech、The Information、Stratechery、Semafor Tech、Financial Times Tech、The Economist Tech

---

### 四、夜间专属·昨夜发生了什么（中英对照原声）
> 中国夜间时段发生的事件，直接呈现原文+译文

子板块：
1. **美股盘面/盘后异动**：NVDA/MSFT/GOOGL/META/TSM/ARM/AMD 等 AI 标的的盘后异动，英文来源+中文翻译
2. **arXiv 论文速递**：cs.AI/cs.CL/cs.LG 当日新论文标题（英文原题）+ 中文翻译 + arXiv 链接
3. **模型发布/产品更新**：新发布的 AI 模型/产品，英文公告原文摘要 + 中文翻译
4. **融资快报**：AI 领域融资，英文来源+中文翻译
5. **会议与活动日历**：即将举行的 AI 会议/发布会

每条均中英对照，不总结。

---

### 五、播客精华（中英对照原声转写）
> 完整中英对照逐字稿，按时间戳段落交替排列，不总结不提炼

当播客逐字稿已就绪时，直接嵌入中英对照内容：
```
[00:00] > English original text...
中文翻译……

[00:12] > English original text...
中文翻译……
```

当播客仍在制作中时，显示「⏳ 本期逐字稿正在制作中，完成后自动更新」并列出正在处理的播客名。

覆盖 31 档播客（监测名单）：
- AI/科技（8）：Acquired、The AI Daily Brief、Dwarkesh Podcast、Latent Space、No Priors、AI + a16z、Lex Fridman Podcast、Practical AI
- AI 基础设施（2）：SemiAnalysis、Gradient Dissent
- 商业/创业（5）：How I Built This、My First Million、Masters of Scale、The Tim Ferriss Show、Lenny's Podcast
- 投资（5）：All-In Podcast、Invest Like the Best、20VC、Bloomberg Odd Lots、In Good Company (NBIM)
- 科技产业评论（4）：Hard Fork、Stratechery (Sharp Tech)、The Vergecast、Prof G Pod
- 科学/健康（3）：Huberman Lab、Huberman Lab Clips、The Diary Of A CEO
- 认知（1）：The Knowledge Project
- 中国/亚洲（2）：Sinica Podcast、ChinaTalk
- 企业 AI 落地（1）：The AI in Business Podcast

**ASR 真实性规则（强制）**：RSS 的 show notes（节目介绍文字）不是逐字稿。只要某集有音频 enclosure，就必须下载音频跑真实 ASR，禁止拿介绍文字冒充逐字稿；只有纯文字刊物（如 SemiAnalysis 文章、Latent Space 通讯）才可保留文本本身并标注「文字刊物」。

---

### 六、开发者口碑
> Reddit/HN 热帖原帖标题+翻译，不加工

监测平台：
- X (Twitter)：搜索 `from:karpathy OR from:sama OR from:ylecun OR from:AndrewYNg OR from:tunguz OR ...`
- Reddit：r/MachineLearning、r/LocalLLaMA、r/artificial、r/ChatGPT
- Hacker News：front 页前10条
- GitHub Trending、HuggingFace Trending

格式：原帖标题（英文）+ 中文翻译 + 链接 + upvotes/points。

---

### 七、AI 与人文（哲学 · 艺术）
> AI 在哲学和艺术交叉领域的表达和观点

哲学人物：David Chalmers、Nick Bostrom、Philip Goff、Ted Chiang、Susan Schneider、Shannon Vallor、Mark Coeckelbergh、John Danaher、Douglas Hofstadter、Eric Schwitzgebel
艺术人物：Refik Anadol、Mario Klingemann、Holly Herndon、Sougwen Chung、Luba Elliott、Memo Akten、Stephanie Dinkins、Anna Ridler、Tom White

监测来源：Aeon、NYRB、Boston Review、Philosophy Now、3:AM Magazine、Rhizome、Artnome、The Art Newspaper、It's Nice That、Cerebral Dirt

---

### 八、开源与模型榜单

- GitHub Trending（AI/ML 类）前5
- HuggingFace 热门模型前5
- HuggingFace 热门 Spaces 前3
- Product Hunt AI 新品前3
- LMSYS Arena Top 5

---

### 九、共识与非共识的边际变化
> 跨源综合分析：今日所有来源中，AI 圈的思维边界在哪里移动

三个子板块：
1. **➡ 从共识走向非共识**：曾经是主流观点，今天开始被质疑——谁在质疑、为什么、什么证据
2. **⬅ 从非共识走向共识**：曾经是边缘观点，今天开始被接受——谁在推动、什么事件
3. **⚡ 今日新出现的非共识观点**：首次出现、值得追踪的反主流声音

这是日报唯一的分析性板块（其他板块均为原声呈现）。需要跨源综合分析（媒体+播客+社媒），投入最多分析精力。

---

### 十、千问办公产品更新
> 千问办公自身的版本更新、功能发布、已知问题修复等

---

## 执行步骤

1. **人物观点（板块一）**：WebSearch 搜索 `site:x.com from:sama OR from:karpathy OR from:ylecun OR from:AndrewYNg OR from:tunguz OR from:pmarca OR ...` 限制24小时。直接引用原话+翻译。
2. **播客状态（板块二）**：检查本地 done.log 和 _podcasts/ 目录。如不可访问（云端），用 WebFetch 检查重点播客 RSS 是否有新集，列出标题+日期，标注"逐字稿制作中"。
3. **科技媒体（板块三）**：用 WebFetch 逐个抓取 12 家媒体的 AI 版块首页，提取最新 3-5 篇文章标题+摘要。英文原文+中文翻译，不总结。
4. **夜间专属（板块四）**：
   - 美股：WebSearch 搜索 "NVDA OR MSFT OR GOOGL" + "after hours"
   - arXiv：WebFetch 抓取 arxiv.org/list/cs.AI/recent、cs.CL/recent、cs.LG/recent
   - 模型发布：WebSearch 搜索 "OpenAI OR Anthropic OR Google DeepMind OR Meta AI" + "release"
   - 融资：WebSearch 搜索 "AI startup funding"
   - 会议：WebSearch 搜索 "AI conference OR summit"
5. **播客精华（板块五）**：读取本地逐字稿文件（如可访问），完整中英对照。如不可访问，显示"⏳ 制作中"。
6. **开发者口碑（板块六）**：WebFetch 抓取 Reddit hot 页和 HN front 页。原帖标题+翻译。
7. **AI与人文（板块七）**：WebSearch 搜索哲学/艺术+AI 相关内容。
8. **榜单（板块八）**：WebFetch 抓取 GitHub Trending、HuggingFace、Product Hunt、LMSYS。
9. **共识与非共识（板块九）**：综合以上所有来源，分析观点的边际变化。唯一分析板块，投入最多精力。
10. **千问办公产品更新（板块十）**：WebSearch 搜索 "千问办公 OR QwenWork" 限制24小时。
11. **组装输出**：同时生成 HTML（品牌色排版+卡片式点击展开交互，见「HTML 交互规范」）和 Markdown（群发纯文本）两个版本。
12. **保存**：用 qwenwork_file_present_files 保存。
13. **IM 推送**：用 qwenwork_channel_list_conversations 查找钉钉/飞书会话，用 qwenwork_channel_delegate_to_im 推送 Markdown 文本+HTML 链接。

## 防中断指令
- 不要使用 AskUserQuestion，不要等待用户确认
- 如遇工具预算超限，选择 continue
- WebFetch/WebSearch 失败直接跳过，标"今日暂无"，继续执行后续板块，不要中断。后续再尝试其他方法提取逐字稿（RSS失败→试官网WebFetch→试YouTube浏览器工具），如仍失败标注"❌ 提取失败"。
- 优先确保完成度，宁可某板块为空也不中断

## 品牌规范
- 主色：#41D87E（Green 500）
- 中文标题字体：阿里妈妈数黑体（视觉大标题）/ 阿里巴巴普惠体3.0（正文）
- 英文字体：Plus Jakarta Sans
- 报头：「千问办公帮我值夜班，呈现AI行业真实原声」+ 日期
- 页尾：`本日报由千问办公自动生成。千问办公——专业人士，都用千问办公。`

## 注意事项
- 核心风格：突出原声和真实感，不像一般媒体做二次加工。直接呈现原文/原话+翻译。
- 板块二、三、五必须中英对照（英文原文+中文翻译），不总结不提炼。
- 共识与非共识板块（板块十）是唯一的分析性内容，放最后。
- 媒体和人物名单不分国籍，合并为一张表/一组列表。
- 英文媒体内容翻译标题+保留英文原标题。
- 如某来源抓取失败，跳过并标注"今日暂无"。
