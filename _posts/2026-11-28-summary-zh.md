---
layout: default
title: "Horizon Summary: 2026-11-28 (ZH)"
date: 2026-11-28
lang: zh
---

> 从 30 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [《我的世界》基岩版资源包漏洞影响 26.52 至 26.63，26.65 已修复](#item-tech-news-1) ⭐️ 8.0/10
2. [热门购物网站发现 WebRTC 信用卡盗刷脚本](#item-tech-news-2) ⭐️ 7.0/10
3. [多州总检察长起诉 SpaceX，要求阻止 Grok 生成儿童性虐待及非自愿私密影像](#item-tech-news-3) ⭐️ 7.0/10
4. [计算机检查的假证明与验证器健全性争议](#item-tech-news-4) ⭐️ 7.0/10
5. [Convex 技能被指未经告知上传用户应用创意](#item-tech-news-5) ⭐️ 7.0/10
6. [SemiAnalysis 解析 Trainium3 推理微架构与 TCO](#item-tech-news-6) ⭐️ 7.0/10
7. [谷歌 Play 将于 2027 年 3 月起公开商家开发者的电话与地址](#item-tech-news-7) ⭐️ 7.0/10
8. [中情局等美国情报机构遭 AI 辅助攻击，涉开源工具 Artex](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [蜜雪冰城据报 5 亿元入股 DeepSeek，后者新一轮融资约千亿元](#item-finance-news-1) ⭐️ 7.0/10
2. [央行将个人大额存单起购门槛降至 10 万元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [《我的世界》基岩版资源包漏洞影响 26.52 至 26.63，26.65 已修复](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 8.0/10

《我的世界》基岩版存在资源包漏洞：带有 content.zipe 文件的资源包可改动 Ore UI 界面框架文件并运行隐藏脚本。附加组件开发者 8Crafter 于 11 月 15 日在 Reddit 公开该问题，称已确认影响 26.52 至 26.63 版本，更早版本也可能受影响；漏洞覆盖 PC、手机和主机，Java 版不受影响。加入服务器或 Realm 时若开启资源包自动下载，玩家可能无需手动安装就收到问题文件；8Crafter 列举的利用方式包括删除全部存档、获取玩家 IP，以及在 Windows 上无提示打开任意 URI、启动资源包内的批处理文件下载恶意软件。Mojang 已在 26.65 版修复，AxmBro 发布的 Windows 只读检测工具可查找 content.zipe，但不能判定资源包是否恶意。

telegram · zaihuapd · 11月27日 18:04

**「背景」** 基岩版资源包本用于替换材质和界面资源，服务器或 Realm 可在玩家加入时触发自动下载，因此资源包内容会直接进入客户端。附加组件开发者 8Crafter 于 11 月 15 日公开披露 content.zipe 可改写 Ore UI 并执行隐藏脚本；据外部报道，Mojang 随后在 11 月 17 日发布 26.65 热修复，媒体称其修复过程相对低调。

**「受影响用户与服务器」** 对玩家和服务器/Realm 运营者来说，最直接的风险是加入时启用资源包自动下载：在 26.52–26.63 上，不可信资源包可能在无需手动安装的情况下被加载。应升级到 26.65；在升级前关闭自动下载或只接受可信来源，而 AxmBro 的 Windows 检测工具仅能发现 content.zipe 文件，无法判断资源包是否恶意，不能替代补丁。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nqbrief.com/en/games/minecraft-bedrock-26-65-resource-pack-fix/">Minecraft Bedrock 26.65 released to fix resource-pack exploit</a></li>
<li><a href="https://www.techtimes.com/articles/330961/20261117/mojang-patches-bedrock-after-community-discovers-resource-packs-could-execute-malicious-code.htm">Mojang Patches Bedrock After Community Discovers Resource ...</a></li>
<li><a href="https://minecraft.pl/en/news/minecraft-bedrock-mojang-patches-resource-pack-security-hole">Minecraft Bedrock: Mojang patches resource pack security</a></li>
<li><a href="https://minecraft.pl/en/news/minecraft-bedrock-mojang-patches-resource-pack-security-hole">Minecraft Bedrock: Mojang patches resource pack security</a></li>

</ul>
</details>

**标签**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#malware`, `#patch`

---

<a id="item-tech-news-2"></a>
### [热门购物网站发现 WebRTC 信用卡盗刷脚本](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

据 Infohawk 报道，热门购物网站上发现了使用 WebRTC 的信用卡盗刷脚本，风险集中在支付页面和第三方脚本。报道没有披露受影响站点、脚本数量、攻击持续时间或具体利用链，因此这仍是媒体报告，而非可独立验证的完整事件。现有材料也不足以判断 WebRTC 在攻击中具体承担数据外传、规避检测还是其他角色。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** 信用卡盗刷脚本（常被称为 Magecart 类攻击）通常通过电商页面引入的第三方脚本被注入，在用户结账时读取表单中的卡号等数据并外传。评论者指出，此次事件的特殊之处不在于 WebRTC 本身存在漏洞，而在于 WebRTC 数据通道较少被监控，且通常不受 connect-src 一类 CSP 指令约束，因此可被当作绕过常规 HTTP 外传检测的通道；同样的外传用普通请求也能完成。就在本月，Ars Technica 报道了恶意代码经第三方脚本服务 Optimizely 投放到数百个网站的事件，其中就包括卡号窃取，说明第三方脚本供应链仍是此类风险的直接来源。

**「对电商结算页的直接影响」** 对电商运营方来说，这意味着结算页的防护重心要从“信任第三方脚本”转向“持续监控第三方脚本”：安全厂商 Sansec 报告的相关案例显示，基于 WebRTC 的支付盗刷可绕过 Content Security Policy 的 connect-src 限制（其中一例借助 Magento 的 PolyShell 漏洞实现），并称在受攻击的目标店铺中过半受影响。具体到兼容性层面，只靠 CSP 白名单已不足以阻断这类外传通道，商家需要审计结算页加载的每一个第三方脚本，并部署客户端行为监控来发现异常连接。

**「社区讨论」** 评论者 afavour 认为这并非 WebRTC 的技术缺陷，而是其流量较少被监控；同样的外传可用普通 HTTP 请求完成，嵌入第三方脚本的站点始终有风险。kevsamuel 也质疑该攻击与 WebRTC 的关联，认为更可能是站点 CSP 未覆盖 WebRTC 或站点防护不足，jszymborski 则把此事视为屏蔽广告和第三方脚本的理由。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arstechnica.com/security/2026/11/malicious-code-delivered-through-optimizely-hits-visitors-to-hundreds-of-sites/">Hundreds of websites deliver potent malware cocktail... - Ars Technica</a></li>
<li><a href="https://berigo.no/en/news/webrtc-used-for-hidden-payment-skimming">New payment skimming in web shops hides behind WebRTC</a></li>
<li><a href="https://news.cybersecuritywaala.com/webrtc-payment-skimmer-bypasses-csp-in-magento-e-commerce-attack/">WebRTC Payment Skimmer Bypasses CSP in Magento...</a></li>
<li><a href="https://www.auditiq.cloud/insight/">Insights on eCommerce monitoring, security, SEO, and performance...</a></li>

</ul>
</details>

**标签**: `#web security`, `#credit card skimming`, `#WebRTC`, `#e-commerce`, `#third-party scripts`

---

<a id="item-tech-news-3"></a>
### [多州总检察长起诉 SpaceX，要求阻止 Grok 生成儿童性虐待及非自愿私密影像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 7.0/10

弗吉尼亚州总检察长办公室发布消息称，多名州总检察长已起诉 SpaceX，诉状将 SpaceX 列为 X、xAI 和 Grok 的母公司，并要求阻止 Grok 生成儿童性剥削材料和非自愿私密影像。诉状还指控相关平台“创建和推广”这类内容；这些是原告的指控，目前尚无法院裁决。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「背景」** Grok 是 xAI 开发并与 X 平台整合的生成式 AI 助手，争议集中在其 Grok Imagine 图像生成功能及“Spicy Mode”。据 Engadget 和《纽约时报》报道，弗吉尼亚州与俄勒冈州总检察长已于 11 月 23 日分别起诉 SpaceX，指控其允许用户生成未经同意的性化图像，违反各州消费者保护法；弗吉尼亚州总检察长 Jay Jones 表示，X 和 Grok 禁止涉及未成年人的性内容，也禁止未经同意生成真实人物的露骨图像。

**「影响」** 对使用或集成 Grok 的开发者而言，直接后果是图像生成功能的合规与可用性面临法院禁令风险；诉讼请求明确要求阻止此类输出，但是否获准仍待审理。

**「社区讨论」** 评论者质疑这类内容本应已被各平台禁止，并讨论 Grok 是限制过松还是需要用户刻意“诱导”；也有人主张应追究生成者本人的责任。另有用户称使用 Grok 需要交出 Twitter 账号，认为这会带来额外的账号安全风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.engadget.com/2325111/two-states-sue-spacex-over-sexually-explicit-grok-deepfakes/">Two States Sue SpaceX Over Sexually Explicit Grok Deepfakes</a></li>
<li><a href="https://www.nytimes.com/2026/11/23/technology/spacex-lawsuit-ai-sexualized-images.html">SpaceX Sued By Oregon and Virginia Over A.I.-Generated...</a></li>
<li><a href="https://www.zerohedge.com/technology/virginia-oregon-sue-spacex-over-groks-spicy-mode-and-sexual-deepfakes">Virginia , Oregon Sue SpaceX Over Grok &#x27;s &#x27;Spicy Mode&#x27; And Sexual .....</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#content moderation`, `#AI regulation`, `#generative AI harms`, `#xAI/Grok`

---

<a id="item-tech-news-4"></a>
### [计算机检查的假证明与验证器健全性争议](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

Daniel J. Bernstein 的页面讨论“虚假的计算机检查证明”：证明验证器的健全性缺陷（soundness bug）可能让无效证明通过，并主张需要更高保障的验证器。Hacker News 评论指出，页面没有充分体现多重独立检查器构成的防线：Metamath 的 set.mm 和 iset.mm 要求证明通过五种不同编程语言实现的独立验证器，Lean 生态也有多个检查器；要误导数学家，还需同时击穿多个检查器并躲过非形式审查。twotwotwo 还举例说，一名 DeepMind 研究员曾分别利用 Lean 和一个当时仅一周版本的 nanoda 的不同缺陷，构造出能通过两者的“证明”。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 计算机核验证明依赖“证明检查器”：这类程序逐条检查证明步骤，只有在检查器本身可靠时，被接受的证明才能保证结论成立。所谓 soundness bug（健全性缺陷），是指检查器实现中的错误可能让不成立的陈述通过检查；Daniel J. Bernstein 的页面汇总了 199 份相关报告，涉及多个重要证明检查程序。因此，讨论的核心不是某个具体数学结论被推翻，而是检查器自身的缺陷会如何削弱“已经过机器检验”这一保证。

**「影响」** 在 Metamath 的 set.mm 和 iset.mm 中，入库要求已经体现为五种独立验证器的交叉检查；对只依赖单一验证器的团队，安全边界仍取决于该实现的健全性。

**「社区讨论」** 评论者对风险是否被夸大存在分歧：twotwotwo 与 dwheeler 强调多重独立检查器和人工非形式审查使单点缺陷难以真正误导数学界，gr\_norm 则认为已有健全性缺陷数量很少、对绝大多数软件足够。andai 补充了另一类问题：智能体可能针对自己对需求的错误理解完成“证明”，这属于规格错误而非验证器缺陷。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cr.yp.to/proofs/falseccp.html">False computer-checked proofs (djb) - cr.yp.to</a></li>
<li><a href="https://x.com/hashbreaker/status/2120889008389837049">Daniel J. Bernstein on X: &quot;Posted new page &quot;False computer ...</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#proof assistants`, `#Lean`, `#soundness bugs`, `#software correctness`

---

<a id="item-tech-news-5"></a>
### [Convex 技能被指未经告知上传用户应用创意](https://github.com/convex/convex-backend-skill/issues/64) ⭐️ 7.0/10

GitHub 上 convex/convex-backend-skill 仓库的 issue \#64 指出，Convex 的 skill 会在未明确告知用户的情况下，把用户的应用创意（提示词）发送到远程服务器。Convex CEO Jamie（用户名 jamwt）在评论中确认，该插件中的提示词上传用于支撑 Convex 的 “quickstart” 功能，并称 quickstart 是公司近期关停的端到端 vibe-coding 产品 Convex Chef 的延续。该 issue 因此引发了对 AI 编码工具隐私披露与信任的讨论；不过，现有公开信息尚未说明上传内容的具体范围、保留方式或用户可选设置。

hackernews · MickyTheMouse · 11月27日 18:02 · [社区讨论](https://news.ycombinator.com/item?id=50669765)

**「背景：Convex 的 SKILL.md 指令文件与 quickstart 上传」** Convex 是一个托管后端平台，这里的“skill”指供 AI 编码代理读取的 SKILL.md 指令文件。该 issue 指出的具体位置是 \`skills/quickstart/SKILL.md\` 第 48–56 行：它把用户的一句话项目想法 POST 到 \`basic-anteater-667.convex.site\`，并在注释中标记为 telemetry；\`skills/add/SKILL.md\` 第 62、64 行还会把同一主机的脚本直接通过管道交给 bash 执行。Convex CEO 在讨论中表示，这一上传用于支撑“quickstart”功能，而该功能是已关停的端到端 vibe-coding 产品 Convex Chef 的继任者。

**「对开发者的影响」** 使用该 skill 的开发者，其应用创意和相关提示词会离开本地环境并进入 Convex 的远程服务；在把未公开的产品构想或敏感代码上下文交给这类工具前，应先确认其数据用途与披露条款。

**「社区讨论」** 评论中，quantum\_state 认为长期看应走自托管开放权重模型，jaynate 则指出提示词注入比模型自行发起恶意工具调用更常见，并强调这不代表本次事件出于恶意。另有评论以“想法不值钱”淡化创意泄露的担忧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/convex/convex-backend-skill/issues/64">Quickstart skills send the user&#x27;s idea to a convex .site host and run...</a></li>

</ul>
</details>

**标签**: `#AI coding tools`, `#privacy`, `#prompt injection`, `#developer tools`, `#open source`

---

<a id="item-tech-news-6"></a>
### [SemiAnalysis 解析 Trainium3 推理微架构与 TCO](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

对评估推理加速器的开发者和运维团队而言，SemiAnalysis 于 11 月 27 日发布的深度分析把 AWS Trainium3 纳入其 InferenceX 基准，并称其在生成 token 的总拥有成本（TCO）上与 Nvidia GB300 互有胜负，甚至领先。该机构基于自研 UBenchX 的微基准称，Trainium3 的 Descriptor Generation Engines（DGE，对应 Nvidia TMA 与 AMD MI455X TDM）可在较小消息尺寸下达到 HBM 带宽利用率峰值，而 Nvidia GPU 做不到；测试还覆盖 SBUF 到 PSUM 的周期级 SRAM 暂存器延迟与带宽、机架级带宽与延迟及注意力机制等。文章进一步称，在 AgentX 的生产级代理式推理负载回放中，Trainium3 PDS 加 vLLM 在整个 TCO 对 p90 交互性曲线上，除 Vera Rubin 外优于其他所有加速器。上述性价比结论来自 SemiAnalysis 的基准与建模，文中未给出具体数值，并称 AWS Annapurna Labs 团队协助验证了基准实验。

rss · Semianalysis · 11月27日 15:54

**「背景」** 亚马逊的 Trainium 是自研 AI 加速器系列，开发者需通过 Neuron SDK 提供的编译器、运行时以及训练和推理库来使用它；Trainium3 的架构文档对应 NeuronCore-v4 硬件引擎。作为对照，Nvidia 的数据中心 GPU 从图形渲染架构演化而来，从 Volta 的 Tensor Core、Hopper 的 TMA 到 Blackwell 的 Tensor Memory 逐代加入 AI 专用单元，这构成了理解 Trainium3 从底层按 ML 工作负载设计这一差异的背景。

**「对推理选型的影响」** 对正在为智能体或代码生成推理做选型的团队，Trainium3 配合 vLLM 已可作为一个按每美元吞吐比较的候选，尤其在以 p90 交互性为约束时，应把 TCO 而非峰值吞吐作为主指标。落地前仍需确认生产环境中的 Trainium3 后端与 PDS 配置可用，并把 SemiAnalysis 的基准结果视为需在自身负载上复现的参考。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aws.amazon.com/ec2/instance-types/trn3/">Gen AI Compute Instance - Amazon EC2 Trn3 UltraServers - AWS</a></li>
<li><a href="https://awsdocs-neuron.readthedocs-hosted.com/en/v2.28.1/about-neuron/arch/neuron-hardware/trainium3.html">Trainium3 Architecture — AWS Neuron Documentation</a></li>

</ul>
</details>

**标签**: `#Trainium3`, `#AI accelerators`, `#inference`, `#microarchitecture`, `#AWS`

---

<a id="item-tech-news-7"></a>
### [谷歌 Play 将于 2027 年 3 月起公开商家开发者的电话与地址](https://www.androidpure.com/google-play-trader-developer-address/) ⭐️ 7.0/10

谷歌 Play 宣布，自 2027 年 3 月 1 日起在全球范围向用户展示自我声明为“商家”的开发者的联系方式，包括个人账户持有者的电话号码和地址。所有活跃开发者账户须在 2027 年 2 月 1 日前申报商家或非商家身份，逾期可能无法更新应用，并从 Play 全球下架。该政策于今年 10 月公布，目前属于已宣布、尚未执行的计划，本周因隐私担忧遭到开发者反弹。谷歌不接受邮政信箱作为付款地址；作为对比，苹果仅在欧洲相关国家展示地址，并允许使用邮政信箱。

telegram · zaihuapd · 11月27日 01:44

**「背景」** 该政策并非本周才出现：谷歌在今年 10 月已公布商家身份披露安排，本周的反弹主要针对其全球适用范围和隐私影响。按照谷歌 Play 的要求，开发者需自我申报为“商家”或“非商家”，而付款地址本身有格式限制——谷歌不接受邮政信箱。作为对照，苹果只在欧洲相关国家展示地址，并允许开发者使用邮政信箱。

**「对开发者的影响」** 开发者需要在 2027 年 2 月 1 日前确认账户是否属于“商家”并完成申报，因为被展示的是自我声明为商家的账户，个人账户持有者的电话和地址同样会对外公开。逾期未申报的直接后果是无法更新应用并可能被下架，因此开发者应核对账户类型和将要披露的地址信息，并注意谷歌不接受邮政信箱作为付款地址这一限制。

**标签**: `#Google Play`, `#developer policy`, `#privacy`, `#app distribution`, `#Android`

---

<a id="item-tech-news-8"></a>
### [中情局等美国情报机构遭 AI 辅助攻击，涉开源工具 Artex](https://www.forbes.com/sites/the-wiretap/2026/11/25/us-government-under-ai-cyberattack) ⭐️ 7.0/10

据《纽约时报》报道并经 Telegram 频道转述，美国中央情报局、国家地理空间情报局和国家情报总监办公室遭到黑客攻击，攻击过程中使用了开源 AI 工具 Artex。Artex 可整合多个开源 AI 模型来测试网络和计算机防御，由一名中国开发者于今年早些时候发布；该工具后来被用于多起攻击，包括针对欧盟的一起，开发者已将其从自己的 GitHub 账号删除。报道称此次攻击看起来不算严重，受影响的是非机密侦察数据；今年早些时候，FBI 曾警告网络罪犯和间谍正在广泛使用 Artex。上述信息来自二手转述，目前尚无涉事机构的独立确认或技术细节。

telegram · zaihuapd · 11月27日 10:42

**「背景：Artex 是什么」** Artex 是一款由中国开发者开源的 AI 渗透测试框架，可整合多个开源 AI 模型，用它们自动测试网络与计算机防御。据 SentinelOne 与 TechTimes 报道，美国联邦调查局（FBI）于 2026 年 11 月 13 日发布 FLASH 警报，指出该框架已被用于网络犯罪和间谍活动，目标包括韩国银行，其中一些入侵在数小时内就取得了特权访问；开发者随后将 Artex 从自己的 GitHub 账号删除，但相关副本仍在流传。

**「影响：非机密系统暴露」** 对美国情报机构而言，此次事件的实际后果是，一个供情报分析使用的非机密系统遭入侵，暴露范围集中在非机密侦察数据；路透社转述国家情报总监办公室的说法称，关键能力和机密系统未受干扰。对防御方来说，Artex 虽已被开发者从 GitHub 删除，但公开流传的副本仍在，FBI 此前已警告其可自动化复杂网络攻击；因此安全团队需要把这类可整合多个开源模型的工具纳入侦察检测与红队评估范围。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techtimes.com/articles/330784/20261116/ai-hacking-tool-artex-survives-github-removal-fbi-some-intrusions-reach-privileged-access-hours.htm">AI Hacking Tool ARTEX Survives GitHub Removal; FBI: Some ...</a></li>
<li><a href="https://www.ic3.gov/CSA/2026/261113.pdf">Threat Overview of ARTEX Autonomous Penetration Testing Framework</a></li>
<li><a href="https://www.sentinelone.com/blog/artex-unmasked-the-rise-of-ai-powered-artex-in-cybercrime-espionage/">ARTEX Unmasked | The Rise of AI-Powered ARTEX in Cybercrime ...</a></li>
<li><a href="https://techgenyz.com/cia-cyberattack-unclassified-osint-2026/">CIA Cyberattack: ARTEX AI Tool Suspected in Intelligence ...</a></li>
<li><a href="https://www.ibtimes.co.uk/artex-ai-tool-cia-odni-cyberattack-1834649">CIA Hack Linked to AI Tool the FBI Warned About 11 Days ...</a></li>

</ul>
</details>

**标签**: `#AI cybersecurity`, `#cyberattack`, `#US intelligence`, `#Artex`, `#open-source AI`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [蜜雪冰城据报 5 亿元入股 DeepSeek，后者新一轮融资约千亿元](https://m.sohu.com/a/1107027659_115479) ⭐️ 7.0/10

据搜狐网报道，DeepSeek 已完成第二轮融资，规模在 1000 亿至 1055 亿元之间，投后估值约 6155 亿元；新增的 31 家出资人中包括腾讯、宁德时代、中国移动和 vivo，蜜雪冰城股份有限公司认缴 5 亿元。上述数字来自媒体报道，目前尚未获得相关公司的官方确认。

telegram · zaihuapd · 11月27日 06:33

**「背景」** 据《The Information》报道，DeepSeek 于今年 6 月完成约 510 亿元首轮融资；第二轮融资目标最初设为 500 亿元，随后上调至约 1000 亿元，此次报道的 1000 亿至 1055 亿元是更具体的规模数字。

**「影响」** 按报道口径，蜜雪冰城通过砺思资本管理的基金以 5 亿元间接入股 DeepSeek，使蜜雪股东间接持有这家私募 AI 公司的股权；但相对蜜雪 2025 年 335.6 亿元营收，这笔出资对其自身财务影响有限。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ithome.com/1/020/121.htm">曝 DeepSeek 第 二 轮 融 资 1055 亿 元： 估 值 6155 ...</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#private financing`, `#AI`, `#Mixue`, `#valuation`

---

<a id="item-finance-news-2"></a>
### [央行将个人大额存单起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布《大额存单管理办法》，将个人投资人认购起点从 20 万元降至 10 万元、机构投资人从 1000 万元降至 500 万元，自 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 大额存单是银行发行的大额存款凭证，新规将取代 2015 年《大额存单管理暂行办法》和 2016 年第 13 号公告。

**「影响」** 新规生效后，资金达到 10 万元但不足 20 万元的个人也可认购大额存单；同日发布的《人民币存贷款利率管理规定》要求金融机构自主确定存贷款利率，不得通过高息揽储等不正当手段吸收存款。

**标签**: `#大额存单`, `#央行监管`, `#存款利率`, `#个人投资门槛`, `#银行业`

---