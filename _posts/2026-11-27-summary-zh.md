---
layout: default
title: "Horizon Summary: 2026-11-27 (ZH)"
date: 2026-11-27
lang: zh
---

> 从 39 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [英伟达据报暂停向东南亚四国发运 AI 服务器](#item-tech-news-1) ⭐️ 8.0/10
2. [AMD 专用 llama.cpp 社区分支](#item-tech-news-2) ⭐️ 7.0/10
3. [谷歌将让 AI 代理使用 Workspace MCP，Gmail 服务被指不能发信](#item-tech-news-3) ⭐️ 7.0/10
4. [华为拟公布数据引脚密度翻倍的 HBM 研究](#item-tech-news-4) ⭐️ 7.0/10
5. [三部门发布通信网方案：2030 年适时建 6G](#item-tech-news-5) ⭐️ 7.0/10
6. [Neuralink 获 FDA 批准启动渐冻症脑机接口关键试验](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [德银：半导体出口额首次超过石油和天然气](#item-finance-news-1) ⭐️ 8.0/10
2. [荷兰大臣称不接受美国 MATCH Act 限制 ASML 对华销售](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [英伟达据报暂停向东南亚四国发运 AI 服务器](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

据《金融时报》援引三名知情人士报道，英伟达已要求主要制造伙伴暂停向马来西亚、新加坡、泰国和印度尼西亚发运 AI 服务器，戴尔、美超微等将英伟达芯片组装成整机的厂商已通知这四国的买家，相关订单无法出厂。知情人士称，此次冻结与美国商务部上周出台的新规有关：区域云服务商须在 90 天内取得出口许可，并核实其客户中不包含受限的中国实体。这四国此前是中国 AI 公司获取英伟达最先进处理器的中转地，因为这类芯片不得直接出口中国大陆。报道依赖未具名消息人士，冻结是否为临时措施尚不清楚。

telegram · zaihuapd · 11月26日 07:38

**「背景」** 英伟达最先进的 AI 芯片不得直接出口中国大陆，因此马来西亚、新加坡、泰国和印度尼西亚长期充当中国 AI 公司采购这类处理器的中转地。美国商务部上周出台新规，要求区域云服务商在 90 天内取得出口许可，并核实客户中不含受限的中国实体，多家媒体将此次暂停出货与此轮管制联系起来。

**「影响」** 对马来西亚、新加坡、泰国和印度尼西亚的 AI 服务器买家及当地云服务商而言，最直接的影响是已组装订单无法出厂、交付时间被冻结，而且这次冻结是否为临时措施尚不明确。区域云服务商还需按新规在 90 天内申请出口许可并核验客户是否包含受限中国实体，相关采购方应预留合规审查与改道交付的时间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/world/asia-pacific/nvidia-halts-chip-shipments-southeast-asia-ft-reports-2026-11-26/">Nvidia halts server shipments to four Southeast Asian ...</a></li>
<li><a href="https://www.paulhastings.com/thought-leadership/us-department-of-commerce-issues-regulations">US Department of Commerce Issues Regulations to Restrict ...</a></li>
<li><a href="https://www.lw.com/en/insights/us-commerce-department-adopts-rule-restricting-remote-access-to-advanced-ai-chips">US Commerce Department Adopts Rule Restricting Remote Access ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI servers`, `#export controls`, `#Southeast Asia`, `#supply chain`

---

<a id="item-tech-news-2"></a>
### [AMD 专用 llama.cpp 社区分支](https://devnull.land/amd-specific-llama-cpp) ⭐️ 7.0/10

一个面向 AMD GPU 的 llama.cpp 社区分支在 Hacker News 上引发讨论，目标是改善在这类硬件上运行本地大语言模型的推理体验。该分支针对 AMD 显卡用户，而非 llama.cpp 上游的通用路径；但现有材料没有给出具体支持的 GPU 型号、代码变更、版本号或可复现的基准结果。因此目前只能确认它是一个社区维护的 AMD 优化分支，尚不能核验其相对上游或其他 AMD 推理方案的实际性能提升。

hackernews · julianlam · 11月26日 17:11 · [社区讨论](https://news.ycombinator.com/item?id=50657265)

**「背景」** llama.cpp 是一个通用推理引擎，AMD 显卡通常通过 ROCm 后端运行；据 Hacker News 讨论，ROCm 对 gfx906（MI50/Radeon VII）等较旧 GPU 只在 nightly 构建中提供支持，官方稳定版尚未覆盖。这促使社区以叠加在主线 llama.cpp 上的小补丁（如 rdna-boosts）或针对特定 AMD 卡的移植来补足优化。

**「部署影响」** 对仍在使用 gfx906 等 AMD 旧卡的用户，这类分支的可用性受 ROCm 支持范围约束：有讨论指出 ROCm 仅在夜间构建中支持 gfx906，而 llama.cpp 需针对相应 ROCm 版本编译，因此部署时应固定 ROCm 与编译工具链，并先做数值和稳定性验证。针对 32GB HBM2 的优化还需确认模型能完全驻留显存，避免回退到系统内存拖慢推理。

**「社区讨论」** 评论者把这类优化形容为一个围绕特殊 AMD 卡的小生态：有人称约 2018 年的 gfx906 数据中心卡以 32GB 显存和约 1 TB/s 的 HBM2 带宽、约 200 美元的价格成为低成本本地推理选择；也有人报告在 MI100、R9700 上通过改造 ROCm 内核或换用其他引擎获得明显加速。这些价格、吞吐和加速数字都是个人经验或主张，未经独立验证，也不一定对应本文讨论的分支。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50657265">AMD -specific fork of llama . cpp | Hacker News</a></li>
<li><a href="https://devnull.land/amd-specific-llama-cpp">AMD -specific fork of llama . cpp | devnull.land</a></li>
<li><a href="https://github.com/xxDoman/ollama-mi50-rocm7.2-optimized-gfx906">GitHub - xxDoman/ollama- mi 50 - rocm 7.2-optimized- gfx 906 : Optimized...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50657265">AMD -specific fork of llama . cpp | Hacker News</a></li>
<li><a href="https://smarthomecircle.com/run-gpu-on-latte-panda-mu-lite-carrier-board">Running an AMD Instinct MI 50 on a LattePanda... | Smart Home Circle</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#AMD GPUs`, `#local LLM inference`, `#open source`, `#GPU optimization`

---

<a id="item-tech-news-3"></a>
### [谷歌将让 AI 代理使用 Workspace MCP，Gmail 服务被指不能发信](https://techstackups.com/articles/google-workspace-ai-agents-mcp/) ⭐️ 7.0/10

据报道，Google 计划让其 Workspace 的 MCP 服务器允许 AI 代理访问各项服务，但 Gmail 的 MCP 服务器不提供发送邮件的能力。现有信息尚未说明这些服务器的普遍可用时间、面向哪些开发者，以及 Gmail 发信限制的具体技术或政策条件，因此这仍应视为已宣布的方向，而非已交付的完整能力。相关讨论的焦点是：这一限制究竟出于安全确认的需要，还是商业上的访问控制。

hackernews · ritzaco · 11月26日 09:44 · [社区讨论](https://news.ycombinator.com/item?id=50653477)

**「背景」** MCP（模型上下文协议）是让 AI 代理通过统一接口调用外部服务和工具的协议。Google 的 Gmail MCP 服务器文档将其能力描述为搜索邮件、读取会话和列出标签，重点在读取数据；这为“代理可接入 Gmail 却不能发信”的限制提供了背景。

**「对开发者的直接影响」** 对基于 Workspace MCP 构建 agent 的开发者来说，实际结果是“能读不能发”：一旦需要真正投递邮件，就得退回浏览器自动化或自建 IMAP/CalDAV 通道（评论中已有自建 Gmail/gCal CLI 的例子），并自行承担账号条款风险。评论者还指出，MCP 规范自 2025-06-18 版起已提供 elicitation，允许服务端在工具调用前暂停并请求用户确认，因此“发送”被限制为合作方专用更像是商业决定而非纯安全约束。

**「社区讨论」** 评论者认为，禁止 Gmail 发信未必能阻止代理，反而可能迫使人们用浏览器自动化代发邮件，过程繁琐且浪费；也有人指出，MCP 已有 elicitation 原语，可在工具调用前暂停并请求用户确认，因此把发信设为仅合作伙伴可用更像是商业决定而非安全需要。另有评论提到企业按用量计费并执行条款限制，以及有人用 IMAP/CalDAV 自建 Gmail 与 Google 日历 CLI 作为绕行方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server">Configure the Gmail MCP server | Google for Developers</a></li>
<li><a href="https://modelcontextprotocol.io/specification/2025-06-18/client/elicitation">Elicitation - Model Context Protocol</a></li>

</ul>
</details>

**标签**: `#MCP`, `#AI agents`, `#Google Workspace`, `#API access`, `#platform policy`

---

<a id="item-tech-news-4"></a>
### [华为拟公布数据引脚密度翻倍的 HBM 研究](https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix) ⭐️ 7.0/10

彭博社报道，华为计划于明年 2 月在旧金山的一场会议上发表一篇新型 HBM 芯片的研究论文，论文标题称其数据引脚密度是三星电子和 SK 海力士量产产品的两倍，理论上可显著提升内存带宽。华为同时在推动 HBM 在中国本土生产，而该部件目前受美国制裁限制。目前披露的仅是论文预告，尚无确认的产品、量产时间或独立技术验证。

telegram · zaihuapd · 11月26日 05:30

**「背景」** 高带宽内存（HBM）通过堆叠 DRAM 裸片并用极宽的总线连接处理器，数据引脚密度直接决定单颗芯片可提供的内存带宽。华为的论文已出现在国际固态电路会议（ISSCC）的预发表日程中，说明这是面向学术会议的芯片研究披露，而非已量产的产品发布。

**「影响」** 若论文披露的引脚密度优势成立，中国 AI 芯片和服务器厂商可能获得一条国产 HBM 替代路径；但在量产时间、良率、容量与兼容性数据公布前，采购和设计切换仍缺乏依据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wccftech.com/huawei-poised-to-grow-chinas-ai-chip-market-next-generation-hbm-design-double-data-pin-density/">Huawei Poised To Grow China’s AI Chip Market With...</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix">Huawei Teases Next-Gen AI Memory Chip to Take On Samsung , Hynix</a></li>

</ul>
</details>

**标签**: `#Huawei`, `#HBM`, `#semiconductor manufacturing`, `#AI hardware`, `#export controls`

---

<a id="item-tech-news-5"></a>
### [三部门发布通信网方案：2030 年适时建 6G](https://www.news.cn/politics/20261126/9fe827a2d98741acb60f62d36ba89cf7/c.html) ⭐️ 7.0/10

经国务院同意，工业和信息化部、国家网信办、国家发展改革委于 11 月 26 日发布《新一代通信网建设实施方案》，提出到 2030 年建成覆盖完善、性能领先的新一代通信网。方案明确适时开展 6G 网络建设、推进 5G-A 网络规模覆盖，并使低轨卫星互联网系统基本建成，推动工业互联网、车联网等融合网络规模化发展。文件还要求加快 6G、卫星互联网、算网融合等标准研制，并深化脑机接口、具身智能、智能网联汽车与新一代通信网的融合。上述均为规划目标，不是已经完成的网络部署。

telegram · zaihuapd · 11月26日 06:30

**「背景」** 该方案以“工信部联通信〔2026〕267 号”文印发，经国务院同意后下发各省、自治区、直辖市人民政府、国务院各部委及相关中央企业执行，工信部网站上的文件落款日期为 2026 年 11 月 17 日，11 月 26 日对外公布。同一时期，中国移动广东公司宣布在公告发布 30 日后逐步让广东的 2G 网络退出服务，这与方案推进 5G-A 规模覆盖、布局 6G 的方向一致，都体现了通信网络代际更替正在从旧制式退网和新制式扩容两端同时进行。

**「影响」** 对运营商和设备商而言，近期可执行的重点是 5G-A 规模覆盖及相关标准研制；6G 目前只有“适时开展”的目标表述，尚无可依据的商用时间表。另据公告，广东移动将在公告发布 30 日后逐步退出省内 2G 网络，仍依赖 2G 的终端和物联网设备需要提前迁移。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wap.miit.gov.cn/jgsj/txs/wjfb/art/2026/art_a1d34268890a4de691214c7d808361db.html">工业和信息化部 国家网信办 国家发展改革委关于印发《新一代通信网建...</a></li>
<li><a href="https://www.miit.gov.cn/zwgk/zcwj/wjfb/tz/art/2026/art_808db1814bb74a0e87965d66e74f5b4b.html">三部门关于印发《新一代通信网建设实施方案》的通知</a></li>

</ul>
</details>

**标签**: `#6G`, `#5G-A`, `#satellite internet`, `#telecom policy`, `#2G shutdown`

---

<a id="item-tech-news-6"></a>
### [Neuralink 获 FDA 批准启动渐冻症脑机接口关键试验](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 7.0/10

Neuralink 宣布已获得 FDA 批准，将在美国启动名为「LINK」的植入式脑机接口关键临床试验，面向渐冻症（ALS）患者招募，目标是把大脑信号直接转化为计算机控制指令。据 Bloomberg 报道，这是美国首个获批的此类关键试验。公司称，此前通过早期研究已在全球为超过 30 名瘫痪患者植入设备。此次获批意味着项目进入关键临床阶段，产生的数据将作为未来申请医疗器械上市许可的核心依据；目前尚无该试验的设计、终点指标、样本量或疗效数据公开。

telegram · zaihuapd · 11月26日 07:15

**「背景」** 关键临床试验（pivotal trial）是医疗器械申请上市前的大规模验证阶段，其数据通常作为向监管机构申请上市许可的核心依据。Neuralink 此前通过早期研究已在全球为超过 30 名瘫痪患者植入设备；此次获批的 LINK 试验是美国首个植入式脑机接口关键试验，招募对象为渐冻症成年患者。

**「影响」** 对渐冻症患者而言，这项试验是当前少数可及的植入式脑机接口临床渠道之一，但获批只是获准启动试验，并不等于设备已被证明有效或可上市。能否入组取决于尚未公布的招募标准与中心分布；该试验数据将成为后续监管审评的关键依据，因此试验方案与结果披露的完整度会直接影响外界对这一技术路线的判断。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://interestingengineering.com/health/neuralink-fda-approval-link-pivotal-brain-implant-trial">Neuralink gets FDA approval for first pivotal brain implant trial</a></li>
<li><a href="https://neuralink.com/updates/neuralink-receives-fda-approval-to-launch-link-pivotal-study/">Neuralink Receives FDA Approval to Launch LINK Pivotal Study</a></li>

</ul>
</details>

**标签**: `#Neuralink`, `#brain-computer interface`, `#FDA`, `#clinical trial`, `#ALS`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [德银：半导体出口额首次超过石油和天然气](https://www.cnbc.com/2026/11/26/semiconductor-chips-are-the-new-oil-heres-why.html) ⭐️ 8.0/10

德意志银行基于国际贸易中心数据的分析显示，按四季度滚动总额计算，截至 2026 年 1—3 月，半导体出口额约 1.61 万亿美元，首次超过石油和天然气的约 1.53 万亿美元。

rss · CNBC Finance · 11月26日 17:52

**「背景」** 德银宏观研究主管吉姆·里德称，这或许意味着从“石油美元”走向“芯片美元”；“石油美元”指产油国把石油出口收入回流购买美国国债等资产。

**标签**: `#semiconductors`, `#AI`, `#global trade`, `#market volatility`, `#macroeconomy`

---

<a id="item-finance-news-2"></a>
### [荷兰大臣称不接受美国 MATCH Act 限制 ASML 对华销售](https://www.bloomberg.com/news/articles/2026-11-26/netherlands-plans-to-fight-rollout-of-proposed-us-curbs-on-asml) ⭐️ 8.0/10

荷兰外贸与发展合作大臣 Sjoerd Sjoerdsma 于 11 月 26 日在议会表示，荷兰不会接受美国 MATCH Act 对 ASML 对华销售的域外限制。该法案由美国两党共同提出，要求荷兰、日本等盟友对华实施更严格的半导体设备出口管制，否则美方将单方面限制其设备出口；中国约占 ASML 今年销售额的 20%，外界预计美国国会将于 12 月中旬表决。

telegram · zaihuapd · 11月26日 14:56

**「背景」** MATCH Act 由美国两党共同提出，要求荷兰、日本等盟友在 150 天内对华实施同等严格的半导体设备出口管制，否则美方将单方面限制其半导体设备出口，包括禁止 ASML 对华销售深紫外（DUV）光刻机并提供维护服务。该法案拟附入美国年度国防政策法案，荷兰因此联合德国、法国及欧盟委员会游说，争取将其剔除。

**「对 ASML 中国业务的影响」** 若 MATCH Act 生效，ASML 向中国出口低端 DUV 光刻机、以及为现有中国客户提供维护服务都可能被禁止（tool-2-3）；中国客户贡献 ASML 今年约 20% 的销售额，其在 2026 年第一季度的系统销售占比已降至 19%（tool-2-1）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/business/dutch-minister-says-us-chip-curbs-bill-would-hurt-europe-2026-11-26/">Dutch minister says US chip curbs bill would hurt Europe</a></li>
<li><a href="https://peopleofinternet.com/articles/legislating-allied-compliance-the-match-act-s-extraterritori.html">Legislating Allied Compliance: The MATCH Act&#x27;s ...</a></li>
<li><a href="https://www.faf.ae/home/2026/7/6/the-silicon-chokepoint-asml-china-and-the-geopolitics-of-the-worlds-most-important-machine">The Silicon Chokepoint: ASML , China , and the Geopolitics of the...</a></li>
<li><a href="https://www.linkedin.com/posts/edsonbellido_semiconductor-asml-semiconductorindustry-activity-7460705612981719040-r3vz">Netherlands Challenges US Chip Sanctions on ASML China Market</a></li>

</ul>
</details>

**标签**: `#ASML`, `#export controls`, `#US-China tech competition`, `#Netherlands`, `#semiconductors`

---