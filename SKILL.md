---
name: night-shift-brief
description: 生成「千问办公帮我值夜班」日报——呈现AI行业真实原声，每日科技媒体原声速览、播客精华、开发者口碑、榜单动态。当用户要求生成夜班日报、媒体监测简报、每日科技舆情、或提到"夜班""夜班模版""媒体口碑"时触发。
version: 2.1.0
---

# 千问办公帮我值夜班，呈现AI行业真实原声 · 日报生成规范

## 定位
生成一份「千问办公帮我值夜班」日报——突出原声和真实感，不做一般媒体的二手速报，直接呈现原文/原话/原文标题+中文翻译。云端运行，任何千问办公用户均可使用。

## 输出格式
- **主格式**：HTML 文件（品牌色 #41D87E 排版，手机自适应，表格美观，中英对照清晰，内容可复制）
- **群发格式**：Markdown 纯文本（可直接粘贴到钉钉/飞书/微信群，媒体复制即用，无格式依赖）
- **推送方式**：如已连接 IM 通道（钉钉/飞书），自动推送到指定会话

## 日报板块顺序与规范

### 一、高影响力人物观点
> 直接引用原话，不二次加工

人物分组（不分国籍）：
- AI 学者/研究员：Andrew Ng (@AndrewYNg)、Yann LeCun (@ylecun)、Andrej Karpathy (@karpathy)、Fei-Fei Li (@drfeifei)、Geoffrey Hinton、Yoshua Bengio (@BengioYoshua)、Pieter Abbeel (@pabbeel)、Sebastian Raschka (@rasbt)、Jim Fan (@DrJimFan)、Lilian Weng (@lilianweng)、Percy Liang (@pliang278)、Jürgen Schmidhuber (@SchmidhuberAI)、Stuart Russell (@StuartJRusse)、Timnit Gebru (@timnitGebru)、Emily Bender (@emilymbender)、Gary Marcus (@garymarcus)、Melanie Mitchell (@MelMitchell1)、Eliezer Yudkowsky (@ESYudkowsky)、Bindu Reddy (@bindureddy)、Clementine Delangue (@clemdelangue)
- AI 公司高管：Sam Altman (@sama)、Greg Brockman (@gdb)、Dario Amodei、Demis Hassabis (@demaborat)、Sundar Pichai (@sundarpichai)、Jensen Huang (@nvidia)、Mark Zuckerberg (@zuck)、Elon Musk (@elonmusk)、Aidan Gomez (@aidangomez)、Arthur Mensch (@arthurmensch)、Thomas Wolf (@thom_wolf)、Aravind Srinivas (@AravSrinivas)、Satya Nadella、Lisa Su (@LisaSu)、Pat Gelsinger (@PGelsinger)
- 投资人/VC：Tomasz Tunguz (@tunguz)、Marc Andreessen (@pmarca)、Sarah Tavel (@SarahTavel)、Connie Chan (@conniechan)、Anjney Midha (@anjney)、Vinod Khosla (@vkhosla)、Reid Hoffman (@reidhoffman)、Chamath Palihapitiya (@chaborat)、Patrick O'Shaughnessy (@Patrick_0S)、Bill Gurley (@bgurley)、Mary Meeker
- 独立分析师：Ben Thompson (@bthompson)、Casey Newton (@CaseyNewton)、Kevin Roose (@kevinroose)、Kara Swisher (@karaswisher)、Alex Kantrowitz (@kantrowitz)、Will Knight (@willknight)、Khari Johnson (@kharijohnson)、Dylan Patel (@SemiAnalysis)

格式：每条直接引用英文原话（引用格式），下方中文翻译，附 X/Twitter 链接。

---

### 二、播客状态
> 提示播客逐字稿制作状态。如无本地逐字稿，通过 RSS 检查新集

用 WebFetch 检查以下播客 RSS 是否有新集发布，列出标题和日期：

AI/科技前沿：Lex Fridman(lexfridman.com/feed/podcast/)、No Priors(feeds.megaphone.fm/nopriors)、AI+a16z(feeds.simplecast.com/Hb_IuXOo)、Practical AI(changelog.com/practicalai/feed)、Acquired(feeds.transistor.fm/acquired)、Latent Space(www.latent.space/feed)、SemiAnalysis(semianalysis.com/feed)
AI基础设施：Gradient Dissent(feeds.captivate.fm/gradient-dissent/)
商业/创业者：How I Built This(feeds.npr.org/510313/podcast.xml)、My First Million(feeds.megaphone.fm/HS2300184645)、Masters of Scale(rss.art19.com/masters-of-scale)、The Tim Ferriss Show(rss.art19.com/tim-ferriss-show)
投资/金融：All-In Podcast(rss.libsyn.com/shows/254861/destinations/1928300.xml)、Invest Like the Best(feeds.megaphone.fm/CLS2859450455)、20VC(rss.libsyn.com/shows/61840/destinations/240976.xml)、Bloomberg Odd Lots(www.omnycontent.com/d/playlist/e73c998e-6e60-432f-8610-ae210140c5b1/8a94442e-5a74-4fa2-8b8d-ae27003a8d6b/982f5071-765c-403d-969d-ae27003a8d83/podcast.rss)
科技产业分析：Hard Fork(feeds.simplecast.com/6HKOhNgS)、Stratechery/Exponent(exponent.fm/feed/)、The Vergecast(feeds.megaphone.fm/vergecast)、Prof G Pod(feeds.megaphone.fm/WWO6655869236)
科学/健康：Huberman Lab(feeds.megaphone.fm/hubermanlab)、The Diary Of A CEO(rss2.flightcast.com/xmsftuzjjykcmqwolaqn6mdn)
认知/决策：The Knowledge Project(feeds.megaphone.fm/FSMI7575968096)
中国/亚洲：Sinica Podcast(rss.art19.com/sinica)、ChinaTalk(feeds.megaphone.fm/CHTAL4990341033)
企业AI：The AI in Business Podcast(rss.libsyn.com/shows/45920/destinations/151434.xml)

以下播客 RSS 不可达但有官网/YouTube，用 WebFetch 或浏览器工具抓取：
Dwarkesh Podcast(dwarkesh.com/podcast/archive)、Lenny's Podcast(lennysnewsletter.com/podcast/archive)、AI Daily Brief(aidailybrief.ai)、In Good Company(nbim.no/en/news-and-insights/podcast/)、Huberman Lab Clips(hubermanlab.com/all-episodes)

对于 YouTube 频道播客，用浏览器工具抓取最新视频标题和描述：
mcp__builtin_browser__navigate 导航到 YouTube 频道 /videos 页面 → mcp__builtin_browser__get_page_text 提取视频标题和描述（描述通常含 show notes 和时间戳）
YouTube 频道：Dwarkesh(youtube.com/@DwarkeshPatel/videos)、Lenny's(youtube.com/@LennysPodcast/videos)、Huberman Clips(youtube.com/@HubermanLabClips/videos)、AI Daily Brief(youtube.com/@aidailybrief/videos)

---

### 三、科技媒体速览（中英对照原声）
> 直接呈现原文标题+摘要和中文翻译，不总结不提炼

监测来源（12家国际科技媒体）：
- TechCrunch: techcrunch.com/category/artificial-intelligence/
- The Verge: theverge.com/ai-artificial-intelligence
- Ars Technica: arstechnica.com/ai/
- MIT Technology Review: technologyreview.com/topic/artificial-intelligence/
- Wired: wired.com/tag/artificial-intelligence/
- Reuters Tech: reuters.com/technology/
- Bloomberg Tech: bloomberg.com/technology
- The Information: theinformation.com/
- Stratechery: stratechery.com/
- Semafor Tech: semafor.com/tech
- Financial Times Tech: ft.com/technology
- The Economist Tech: economist.com/technology

格式：每条包含英文原文标题（加粗）、英文一句话摘要、中文标题翻译、中文摘要翻译、来源链接。

---

### 四、夜间专属·昨夜发生了什么（中英对照原声）
> 中国夜间时段发生的事件，直接呈现原文+译文

子板块：
1. **美股盘面/盘后异动**：WebSearch 搜索 "NVDA OR MSFT OR GOOGL OR META OR TSM OR ARM OR AMD" + "after hours OR premarket"
2. **arXiv 论文速递**：WebFetch 抓取 arxiv.org/list/cs.AI/recent、arxiv.org/list/cs.CL/recent、arxiv.org/list/cs.LG/recent。英文原题+中文翻译+链接
3. **模型发布/产品更新**：WebSearch 搜索 "OpenAI OR Anthropic OR Google DeepMind OR Meta AI OR Mistral" + "release OR launch OR announce" 限制24小时
4. **融资快报**：WebSearch 搜索 "AI startup funding OR raise OR Series" 限制24小时
5. **会议与活动日历**：WebSearch 搜索 "AI conference OR summit OR keynote" 限制24小时

每条均中英对照，不总结。

---

### 五、播客精华（中英对照原声转写）
> 如有本地播客逐字稿文件则嵌入完整中英对照内容；否则显示状态提示

如有本地逐字稿：按时间戳段落交替排列英文原文和中文译文。
如无本地逐字稿：显示"⏳ 本期逐字稿正在制作中"并列出板块二中检测到的新集标题。

---

### 六、开发者口碑
> Reddit/HN 热帖原帖标题+翻译，不加工

监测平台：
- X (Twitter)：WebSearch 搜索 `site:x.com from:karpathy OR from:sama OR from:ylecun OR from:AndrewYNg OR from:tunguz OR from:pmarca` 限制24小时
- Reddit：WebFetch 抓取 r/MachineLearning、r/LocalLLaMA、r/artificial 的 hot 页
- Hacker News：WebFetch 抓取 news.ycombinator.com/front 前10条
- GitHub Trending：WebFetch 抓取 github.com/trending?since=daily
- HuggingFace Trending：WebFetch 抓取 huggingface.co/models?sort=trending

格式：原帖标题（英文）+ 中文翻译 + 链接 + upvotes/points。

---

### 七、AI 与人文（哲学 · 艺术）
> AI 在哲学和艺术交叉领域的表达和观点

哲学人物：David Chalmers (@dchalmers)、Nick Bostrom (@NickBostrom)、Philip Goff (@Philip_Goff)、Ted Chiang、Susan Schneider (@NSchneidersays)、Shannon Vallor (@ShannonVallor)、Mark Coeckelbergh (@mcoeckel)、John Danaher (@JohnDDanaher)、Douglas Hofstadter、Eric Schwitzgebel (@ESchwitz)
艺术人物：Refik Anadol (@refikanadol)、Mario Klingemann (@Quasimondo)、Holly Herndon、Sougwen Chung、Luba Elliott (@lubaaelert)、Memo Akten (@memotv)、Stephanie Dinkins、Anna Ridler、Tom White (@TomWhiteArt)

监测来源：Aeon (aeon.co/technology)、NYRB (nyrb.com)、Boston Review (bostonreview.net)、Philosophy Now (philosophynow.org)、3:AM Magazine (3ammagazine.com)、Rhizome (rhizome.org)、Artnome、The Art Newspaper、It's Nice That、Cerebral Dirt

---

### 八、开源与模型榜单

- GitHub Trending（AI/ML 类）前5：WebFetch 抓取 github.com/trending?since=daily
- HuggingFace 热门模型前5：WebFetch 抓取 huggingface.co/models?sort=trending
- HuggingFace 热门 Spaces 前3
- Product Hunt AI 新品前3
- LMSYS Arena Top 5：WebFetch 抓取 lmarena.ai/leaderboard

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

WebSearch 搜索 "千问办公 OR QwenWork" 限制24小时。

---

## 执行步骤

1. **人物观点（板块一）**：WebSearch 搜索高影响力人物的最新推文。直接引用原话+翻译。
2. **播客状态（板块二）**：WebFetch 检查重点播客 RSS 是否有新集，列出标题+日期。
3. **科技媒体（板块三）**：WebFetch 逐个抓取 12 家媒体的 AI 版块首页，提取最新 3-5 篇文章。英文原文+中文翻译，不总结。
4. **夜间专属（板块四）**：WebSearch/WebFetch 抓取美股、arXiv、模型发布、融资、会议。中英对照。
5. **播客精华（板块五）**：如本地有逐字稿则嵌入，否则显示制作中状态。
6. **开发者口碑（板块六）**：WebFetch 抓取 Reddit/HN/GitHub/HuggingFace。原帖+翻译。
7. **AI与人文（板块七）**：WebSearch 搜索哲学/艺术+AI 相关内容。
8. **榜单（板块八）**：WebFetch 抓取各榜单页面。
9. **共识与非共识（板块九）**：综合以上所有来源，分析观点的边际变化。
10. **千问办公产品更新（板块十）**：WebSearch 搜索相关内容。
11. **组装输出**：同时生成 HTML（品牌色排版）和 Markdown（群发纯文本）。
12. **保存**：用 qwenwork_file_present_files 保存文件。
13. **IM 推送（可选）**：如已连接 IM 通道，用 qwenwork_channel_list_conversations 查找会话，用 qwenwork_channel_delegate_to_im 推送。

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
- 板块三、四、五必须中英对照（英文原文+中文翻译），不总结不提炼。
- 共识与非共识板块（板块九）是唯一的分析性内容。
- 媒体和人物名单不分国籍，合并为一张表/一组列表。
- 英文媒体内容翻译标题+保留英文原标题。
- 如某来源抓取失败，跳过并标注"今日暂无"。
