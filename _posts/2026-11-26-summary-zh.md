---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 32 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [1Password 披露后端代码推送安全事件](#item-tech-news-1) ⭐️ 8.0/10
2. [Aaronson 谈 AI 数学进展，社区激辩 Lean 与证明](#item-tech-news-2) ⭐️ 8.0/10
3. [腾讯开源 Hy4 flash 量化权重：最小版可跑 64 GB Mac mini](#item-tech-news-3) ⭐️ 8.0/10
4. [Minecraft Java 曝未修复 RCE 漏洞，1.20.5 起受影响](#item-tech-news-4) ⭐️ 8.0/10
5. [Anthropic 的 GRH Lean 验证出现社区精简版](#item-tech-news-5) ⭐️ 7.0/10
6. [Google 发布 Cogentic 整数分解与离散对数论文](#item-tech-news-6) ⭐️ 7.0/10
7. [随笔主张用 LLM 工具，讨论聚焦验证责任](#item-tech-news-7) ⭐️ 7.0/10
8. [用 Lean 检查 Clojure 核心库，声称发现未上报缺陷](#item-tech-news-8) ⭐️ 7.0/10
9. [SemiAnalysis 推出 GDPx 基准并更新新模型榜单](#item-tech-news-9) ⭐️ 7.0/10
10. [三星与 SK 海力士据报采用长江存储 Xtacking 技术](#item-tech-news-10) ⭐️ 7.0/10

**财经新闻**
1. [美商务部被曝威胁英特尔交出 10%股权](#item-finance-news-1) ⭐️ 9.0/10
2. [美国拟对 14 个贸易伙伴加征第 301 条关税](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [1Password 披露后端代码推送安全事件](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 发布了关于 2026 年 11 月安全事件的更新，社区评论引述的公告内容称，攻击者曾将恶意代码推送到后端服务，并称少数属于特定状态的用户已收到单独通知。现有材料是事件更新而非完整技术复盘，因此员工设备如何被攻破、分支保护或主分支推送限制是否失效、加密保险库是否被下载等关键问题，都未得到充分说明。对使用其云托管密码库的用户来说，这一披露把关注点集中在开发终端被攻破后，恶意代码能否进入生产环境，以及通知范围是否足够明确。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「事件时间线」** 根据 1Password 的博客更新，公司于 2026 年 11 月 19 日开始调查一起安全事件：有迹象显示一名员工的公司 GitHub 账号遭到入侵，攻击者利用该账号访问源代码，并向其后端服务推送了恶意代码（tool-2-1、tool-2-2）。11 月 25 日发布的这篇博文是该事件的进展更新。

**「实际影响与用户行动」** 对 1Password 用户而言，按官方说法，客户保险库未被访问、库内内容仍然安全，实际暴露面集中在后端系统和部分客户记录，因此收到单独通知的用户应按指引核对账户状态，而未收到通知者不必因本次事件假定保险库密码已泄露。对企业客户来说，更紧迫的检查项可能不在密码库本身，而在自身向生产后端推送代码的权限与分支保护流程，因为此次事件的已知路径是员工设备失陷后恶意代码进入后端服务。

**「社区讨论」** 评论中，tptacek 认为员工终端被攻破后可向 GitHub 推送代码是 SaaS 公司的标准攻击面，并称随着员工数量增长，至少一台设备被攻破的概率趋近于 1；ChrisHardie 则作为坚持使用本地保险库的老用户，仍担心生产服务被推入恶意代码后会侵入用户账户访问流程。ctidd 追问 1Password 是否缺少分支保护或主分支推送限制，fn-mote 希望公告明确说明加密保险库未被下载；这些是社区质疑与担忧，不是已确认事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving 1 Password ’s backend ...</a></li>
<li><a href="https://www.macrumors.com/2026/11/25/1password-security-breach/">1 Password Security Breach: What Was Accessed and... - MacRumors</a></li>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving 1Password’s backend ...</a></li>
<li><a href="https://techcrunch.com/2026/11/25/1password-said-hackers-broke-into-its-internal-systems-but-customer-passwords-are-safe/">1Password said hackers broke into its internal systems, but ...</a></li>

</ul>
</details>

**标签**: `#security incident`, `#password managers`, `#SaaS security`, `#supply chain security`, `#code deployment`

---

<a id="item-tech-news-2"></a>
### [Aaronson 谈 AI 数学进展，社区激辩 Lean 与证明](https://scottaaronson.blog/?p=10379) ⭐️ 8.0/10

Scott Aaronson 在一篇新博客中称当前 AI 数学进展的规模惊人，Hacker News 讨论把它视为一次重要的 AI 辅助数学/自动定理证明事件，受影响的主要是数学研究者和 Lean/MathLib 工具链使用者。供给内容没有给出完整论文、证明范围或独立验证结果，只附带了一条指向“矩阵乘法指数为 9/4”的 PDF 链接，因此具体突破内容仍不明确。眼下能确认的是讨论热度与关注点，而不是一个已被独立核实的定理证明。

hackernews · Kotlopou · 11月25日 19:11 · [社区讨论](https://news.ycombinator.com/item?id=50646108)

**「背景」** 矩阵乘法指数 ω 衡量两个 n×n 矩阵相乘所需的算术运算量随 n 增长的速度，数值越小，理论上的渐近复杂度越低。OpenAI 仓库中一份日期为 2026 年 11 月 24 日的预印本声称得到 ω=9/4，并给出配套 Lean 开发，形式化了“在所有域上、对形式多项式恒等式使用无除法电路”的平方指数 9/4；该结果针对这一理论电路模型，而不是实际运行时间的优化。这为 Aaronson 博文围绕 AI 辅助数学证明展开的讨论提供了直接的技术背景。

**「影响」** 对 Lean/MathLib 使用者来说，真正的门槛是 AI 生成的证明能否通过形式化检查并接受人工审稿；评论中反复提到费马定理、Clay 问题和“更短的证明”，说明可验证性与可读性仍是落地条件。

**「社区讨论」** 评论者对 AI 生成证明的看法分裂：atbpaca 担心重大数学问题被 AI 解决后人类可挑战的空间变小，utopiah 则追问若没有 LLM、只靠 Lean/MathLib 和算力是否也会取得同样进展。gorgoiler 用物理学在 19 世纪末看似“已解决”、随后又被量子力学改写的历史作类比，认为数学可能进入新的问题域。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.alphaxiv.org/abs/2611.matrix-multiplication-exponent-lower-bound">The Matrix Multiplication Exponent Is Nine Fourths | alphaXiv</a></li>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/README.md">math/preprints/The- matrix - multiplication - exponent - is ...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>

</ul>
</details>

**标签**: `#AI mathematics`, `#automated theorem proving`, `#Lean/MathLib`, `#matrix multiplication`, `#research impact`

---

<a id="item-tech-news-3"></a>
### [腾讯开源 Hy4 flash 量化权重：最小版可跑 64 GB Mac mini](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 8.0/10

腾讯混元通过模型压缩工具 AngelSlim 开源了 224B 参数模型 Hy4 flash 的 GGUF 量化权重，原权重约 410.27GiB，最小 IQ2-AH 版为 125.73GiB、约为原版 30%。据发布信息，借助 Strata offload 框架，该最小版可在 64 GB Mac mini 上运行；在 48 GB 显存设备上，10K 上下文生成速度为每秒 89 个 token，M5 Max 128 GB 运行 Q3\_K 版、32K 上下文时为每秒 47 个 token。DeepSWE v1.1 等评测中，Q3\_K 与原模型得分差距不超过 0.4 分，但上述数字来自该发布信息，尚非独立复测结果。

telegram · zaihuapd · 11月25日 09:29

**「背景」** GGUF 是面向本地推理的模型文件格式，量化通过降低权重精度来压缩模型体积和内存占用，因此同一模型通常会提供从高精度到低精度的多个版本。此次 64 GB Mac mini 的用例之所以成立，还因为最小版权重可借助 Strata offload 框架运行；来源没有进一步说明该框架具体如何实现 offload。

**「实际影响」** 对想在 64 GB Mac mini 上本地运行 224B 参数 Hy4 flash 的开发者，关键限制是：最小 IQ2-AH 权重仍有 125.73 GiB，无法整体放入 64 GB 统一内存，必须依赖 Strata 将 checkpoint 拆分到显存、主机内存和只读 NVMe。实际可用性因此会受存储读速和 offload 配置影响；腾讯给出的 Q3\_K 评测差距不超过 0.4 分，但该版本测试环境是 128 GB 的 M5 Max。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ro99/strata">GitHub - ro99/strata: C/C++ MoE inference engine for models ...</a></li>

</ul>
</details>

**标签**: `#Tencent Hunyuan`, `#model quantization`, `#GGUF`, `#local inference`, `#open-source AI`

---

<a id="item-tech-news-4"></a>
### [Minecraft Java 曝未修复 RCE 漏洞，1.20.5 起受影响](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

11 月 22 日公开的 minecraft2shell 漏洞显示，Minecraft Java 版服务器资源包中的特制 TrueType 字体可触发 FreeType 2.14.3 及更早版本的原生越界写，并在 Java 版 26.3 Windows 客户端上执行任意代码。受影响版本为 1.20.5 至 1.21.10 以及 26.1 至 26.4 快照；1.20.4 及更早版本和基岩版不受影响。Mojang 仍使用 lwjgl-freetype 3.4.3，尚无官方补丁；社区于 11 月 24 日发布 m2sfix 1.0.0，可通过 Java agent 或 mod 关闭 hinting。在修复前，投稿人建议不要添加任何资源包，将多人游戏服务器资源包权限设为“禁用”，或安装该临时修复。

telegram · zaihuapd · 11月25日 12:46

**「背景：字体渲染链路如何变成攻击面」** Minecraft Java 版通过 LWJGL 的 lwjgl-freetype 绑定调用 FreeType 来渲染 TrueType 字体，客户端依赖目录中可见对应的本地库文件（如 lwjgl-freetype-natives-windows）。由于服务器下发的资源包可自带字体并由客户端加载解析，FreeType 的字体解析缺陷便落在客户端进程内；公开的 PoC 正是针对 Mojang 签名的 Java 26.3 Windows 客户端及其随附的 FreeType 2.14.3 x64 构建实现的。

**「对玩家的直接影响」** 对连接多人服务器的 Java 版玩家来说，在官方补丁发布前，最直接的处置是把“服务器资源包”权限设为“禁用”，或安装社区 m2sfix 1.0.0（Java agent 或 mod）。该修复通过在不启用 hinting 的情况下加载所有字体，使字体自带字节码不执行，从而阻断这一攻击路径；代价是所有字体都不再使用 hinting。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/bikini/minecraft2shell">GitHub - bikini/ minecraft 2 shell : Minecraft to native RCE · GitHub</a></li>
<li><a href="https://www.minecraftforum.net/forums/support/java-edition-support/3231268-minecraft-1-21-1-openjdk-platform-binary-not">Minecraft 1.21.1 &quot;OpenJDK Platform Binary not responding&quot; - Java ...</a></li>
<li><a href="https://github.com/sunrisemc-tw/minecraft2shell-fix">GitHub - sunrisemc-tw/minecraft2shell-fix: Client-side ...</a></li>
<li><a href="https://modrinth.com/project/PiuygVWJ">Server Pack Unlocker - Minecraft Mod - Modrinth</a></li>

</ul>
</details>

**标签**: `#Minecraft`, `#RCE`, `#FreeType`, `#security vulnerability`, `#resource packs`

---

<a id="item-tech-news-5"></a>
### [Anthropic 的 GRH Lean 验证出现社区精简版](https://github.com/lsernau/grh-lean) ⭐️ 7.0/10

Anthropic 的 GRH（广义黎曼猜想）Lean 形式化出现了社区制作的精简版：评论称证明从约 1700 万行降到约 7.6 万行，并增加了“已知数学/新数学”分区和面向人的文档。另有评论把可读版本描述为约 30 万行，材料未说明这些数字的统计口径，因此缩减幅度仍需以仓库为准。一条评论引述的项目说明还称，该证明只依赖 propext、Classical.choice 与 Quot.sound 三条公理。对数学家和 Lean 用户而言，主要变化是审查对象变得更可分区阅读；但这是可读性和规模上的改进，不等同于新的数学结论。

hackernews · nb-t · 11月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=50648050)

**「背景」** 广义黎曼猜想（GRH）此前的 Anthropic Lean 证明是一个约 1740 万行、175,187 个文件的大型归档，外部编译测试称完整构建约需 36 小时 44 分钟。现在这个紧凑仓库把同一组五个定理压缩到约 7.6 万行，并以 Lean v4.35.0 和 Mathlib 提交 56a00585 作为构建前提。

**「影响」** 对需要复核该形式化的数学家和 Lean 用户，直接后果是可按文档及“已知数学/新数学”分区阅读，而不必先面对约 1700 万行的原始证明；在把它当作原验证的替代品前，应核对两者的对应关系、构建状态和公理依赖。

**「社区讨论」** 评论者把可读文档和“已知数学/新数学”分区视为主要改进，并引用约 99.56% 的缩减；也有人追问这是否回应 Tao 此前关于“巨大但缺乏洞见的形式化证明”的批评，以及不熟悉 Lean 的数学家该如何理解所用公理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/lsernau/grh-lean">GitHub - lsernau / grh - lean : A short Lean 4 proof of the Generalized...</a></li>
<li><a href="https://www.youtube.com/watch?v=aDl7-MWFLVc">17 Million Lines Claim to Prove Riemann. We Ran Them. - YouTube</a></li>

</ul>
</details>

**标签**: `#Lean`, `#formal verification`, `#mathematics`, `#AI-assisted proof`, `#GRH`

---

<a id="item-tech-news-6"></a>
### [Google 发布 Cogentic 整数分解与离散对数论文](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research 已在 GitHub 发布一批 Cogentic 研究论文，主题包括整数分解、离散对数及相关方向。现有条目没有提供论文摘要、方法或实验数据，因此无法确认这些结果在算法或密码学上的实际强度，也不能将其视为已证实的突破。对关注密码学和 AI 数学推理的研究者而言，目前只能确认论文主题，尚不能判断其具体影响。

hackernews · rgwohlbold · 11月25日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50642086)

**「背景」** 整数分解和离散对数都是公钥密码学所依赖的计算困难问题：RSA 的安全性建立在分解大整数之上，Diffie–Hellman、DSA 等方案则建立在离散对数之上。离散对数可理解为模运算中的“求指数”问题，即已知底数、模数和结果，反推指数。

**「对密码学部署的影响」** 对密码学工程团队来说，当前不应根据这批论文调整 RSA 或有限域离散对数系统的部署：相关报道称这些结果仍属理论上的最坏情况界，Lean 4 形式化验证尚待完成，且未对 RSA 构成实际威胁。

**「社区讨论」** 评论中，有人把近期数学发现类比为 AlphaGo 在大搜索空间中的探索，认为这类进展并不意外；也有人提到关于“更大成果”的传闻，但该说法未获本条目证实。另有评论从投资角度质疑数学突破与 AI 市场走势的脱节。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Discrete_logarithm">Discrete logarithm - Wikipedia</a></li>
<li><a href="https://news.ycombinator.com/item?id=50642086">Google releases Cogentic papers on integer factorization , discrete ...</a></li>
<li><a href="https://www.rdworldonline.com/google-cogentic-ai-integer-factoring-bounds-lean-proofs/">Google’s Gemini 4 agent claims six math proofs in a day ...</a></li>
<li><a href="https://aicrier.com/post/3hiujknt9rho2mnds0q9">Google drops Cogentic papers on integer factoring — AICrier</a></li>

</ul>
</details>

**标签**: `#cryptography`, `#integer-factorization`, `#discrete-logarithms`, `#AI-for-math`, `#Google Research`

---

<a id="item-tech-news-7"></a>
### [随笔主张用 LLM 工具，讨论聚焦验证责任](https://www.iankduncan.com/engineering/2026-11-19-smart-people-who-give-a-shit-use-tools) ⭐️ 7.0/10

Ian K. Duncan 的工程随笔《Smart people who give a shit use tools》主张，重视质量的软件工程师应当把大语言模型当作工具使用；该文于 11 月 19 日发布，11 月 25 日被提交到 Hacker News 引发讨论。这是一篇观点文章而非产品发布或实测结果，其核心论点围绕「LLM 只是又一层抽象」以及「模型写的」能否在代码评审中作为免责理由展开。HN 评论者并未形成共识，而是分别从抽象类比是否成立、验证成本如何变化、开发者如何避免知识退化三个角度提出质疑或补充。

hackernews · matthewsinclair · 11月25日 07:46 · [社区讨论](https://news.ycombinator.com/item?id=50639698)

**「争论背景」** 围绕 LLM 编程工具的讨论中，一个常见类比是把 LLM 说成“又一层抽象”，与从汇编到 C、再从 C 到 JavaScript 的迁移相提并论；评论者 anothaway 不接受这个类比，认为前几次迁移中开发者仍在把问题建模成代码，而把工作交给 LLM 并不是同一类活动。Ian Duncan 这篇 11 月发布的文章则把判断标准从“有没有用 LLM”移开：文中提出，要判断一个人是否真的在意某个系统，该问的是他合并的代码在凌晨两点崩溃时会发生什么。

**「影响」** 对采用 LLM 编码的团队来说，直接后果是瓶颈从编写代码转向验证代码：Sonar 的调查数据显示，38% 的开发者认为审查 AI 生成代码比审查人类同事的代码更费力，另有分析指出评审质量现在决定提速是收益还是负债。因此团队需要为代码评审预留与生成相当甚至更多的人力，并事先明确“模型写的”不构成责任豁免——这正是原文追问代码评审中该借口是否成立的实际落点。

**「社区讨论」** 评论者 anothaway 认为，把 LLM 类比为此前的抽象跃迁（如汇编到 C、C 到 JavaScript）并不成立，因为那些转变中开发者仍在做同样的建模工作，而使用 LLM 改变的是活动本身。xnorswap 提出一个更尖锐的推论：LLM 放大效率后，愿意花时间额外验证的人反而可能被不认真验证却大量产出的人「卷」下去；notpachet 则强调需要有意识地保持对系统的理解，否则知识会萎缩。chrisra 从个人体验出发表达矛盾：如果模型确实比自己强，「模型写的」既不像正当理由，也并非完全不合理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.iankduncan.com/engineering/2026-11-19-smart-people-who-give-a-shit-use-tools">Smart People Who Give a Shit Use Tools - Ian Duncan</a></li>
<li><a href="https://www.iankduncan.com/engineering">Engineering - Ian Duncan</a></li>
<li><a href="https://www.sonarsource.com/company/press-releases/sonar-data-reveals-critical-verification-gap-in-ai-coding/">Sonar Data Reveals Critical &quot;Verification Gap&quot; in AI Coding ...</a></li>
<li><a href="https://nhimg.org/articles/ai-generated-code-is-creating-a-verification-bottleneck-for-developers/">AI-generated code is creating a verification bottleneck for ...</a></li>

</ul>
</details>

**标签**: `#LLM coding tools`, `#software engineering`, `#code review`, `#developer productivity`, `#AI accountability`

---

<a id="item-tech-news-8"></a>
### [用 Lean 检查 Clojure 核心库，声称发现未上报缺陷](https://s.conao3.com/blog/2026/e4f733) ⭐️ 7.0/10

一篇博客文章报告称，作者用 Lean 检查 Clojure 核心库，并列出了一批此前未上报的缺陷，面向的是 Clojure 维护者和关心核心库可靠性的开发者。该结论目前仍是作者的单方面审计结果，未经 Clojure 项目确认，也没有独立复现。评论者已指出清单中至少两例更像误报：\`\(.indexOf \(seq \(byte-array \[1 2 3\]\)\) 2\)\` 把 Long 传给按 byte 处理的 \`.indexOf\`，而 \`\(get &quot;abc&quot; 1.9\)\` 涉及 \`get\` 在字符串场景下对键的整数强制转换。因此，缺陷数量和实际影响尚不能按文章标题中的说法视为已确认。

hackernews · encyclopedism · 11月25日 14:56 · [社区讨论](https://news.ycombinator.com/item?id=50642939)

**「背景」** Lean 4 是交互式定理证明器，可把程序语义写成机器可检查的模型；模型给出反例后，仍需回到原实现复现。该方法的可检验范围也受限制：相关技术说明称，Lean 只能直接处理可归约为整数和位运算的小函数，较大的持久化数据结构则要靠差分测试核对。

**「实际影响」** 对打算把这份清单当作 Clojure core 缺陷列表来处理的开发者来说，先逐条甄别是必要步骤：评论者 rvprasad 指出至少两项源于调用方类型误用——\`\(.indexOf \(seq \(byte-array \[1 2 3\]\)\) 2\)\` 拿 Long 型参数去匹配 byte 数组元素，\`\(get &quot;abc&quot; 1.9\)\` 则依赖 \`get\` 在字符串上把键强制转换为整型的既有语义，因此这些结果不能直接换算成 core 库的 bug 数量。若要把这类 Lean 审计接入实际修复流程，需要先把参数类型约束和强制转换规则建进模型，否则误报会稀释真正值得排查的条目。

**「社区讨论」** rvprasad 认为这类工作虽有意义，但清单里的 \`\(.indexOf \(seq \(byte-array \[1 2 3\]\)\) 2\)\` 是类型用错，简单类型检查就能发现，建议减少此类噪声；他还解释 \`\(get &quot;abc&quot; 1.9\)\` 源于 \`get\` 在字符串对象上把键强制转换为整数。另有评论者追问这是否意味着 Lean 正在取代 Rocq（原 Coq）用于程序正确性验证，以及语言模型是否更擅长写 Lean。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=7dhNNeMDCkw">Formal Verification Exposes Hidden Bugs in Clojure Core CircuitProver: Agentic Lean 4 Theorem Proving with Reusable RH Lean proof: verification files - MIT Mathematics Lean 4.35 Ships with Four Verified Kernels: Proving the Proof ... I checked Clojure&#x27;s core with Lean and differential testing ...</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#Lean`, `#Clojure`, `#programming languages`, `#bug discovery`

---

<a id="item-tech-news-9"></a>
### [SemiAnalysis 推出 GDPx 基准并更新新模型榜单](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis 于 11 月 1 日发布 GDPx 基准，并在一个月内多款前沿模型问世后更新了排行榜。该基准由 14 家专业数据合作伙伴构建 206 项任务，覆盖芯片设计、网络安全、生物学、金融、法律、量化交易、递归自我改进（RSI）、硬件设计、材料科学、对齐和软件工程共 11 个领域，刻意排除政府、房地产等行业；SemiAnalysis 批评 GDPVal、Agent&\#x27;s Last Exam 等综合基准按 GDP 占比或 O\*NET 分类选题的做法有缺陷。难度上，发布日得分最高的 Opus 5.5 仅得 12%，而多数基准首次亮相时榜首模型常超过 50%，SemiAnalysis 称这让 GDPx 相比已饱和的 Terminal Bench 4.0 更能区分后续模型。文章还指出，Fable 5.2 与 GPT-6.2 Astra 因安全分类器在网络安全、生物学、对齐三个领域拒答而整体得分偏低；剔除这三项并对默认二值评分的法律、金融改用部分评分后，榜单排序发生变化。文中提到 Anthropic、OpenAI 的新模型、Google Gemini 4 系列以及阿里巴巴、Moonshot 的发布，但正文摘录未给出这些模型的具体分数。

rss · Semianalysis · 11月26日 00:05

**「背景：为何另建基准」** GDPx 之前的综合性评测多按“经济占比”或职业分类挑选领域：OpenAI 的 GDPVal 依据各行业占 GDP 比重选取任务，Agent&\#x27;s Last Exam 则依托 O\*NET 职业分类组织题目，重心在覆盖面而非难度集中。SemiAnalysis 同时点名 Terminal Bench 4.0 这类“饱和”基准——头部模型得分已接近上限，难以再区分新模型之间的差距。GDPx 于 11 月 1 日发布，发布当日得分最高的 Opus 5.5 仅拿到 12%，正是针对这两点设计。

**「对模型选型的影响」** 对于用 GDPx 挑选模型的团队来说，总榜排名不宜直接当作能力排序：SemiAnalysis 指出，Fable 5.2 和 GPT-6.2 Astra 因安全分类器在网络安全、生物、对齐三个领域触发拦截，整体分数被拉低；若剔除这三个领域、并对默认二元评分的法律与金融改用部分打分，榜单次序会改变。GDPx 站点还按任务列出前沿模型的成本，因此选型时应把安全触发导致的分数损失与单任务成本一并纳入考量。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gdpx.semianalysis.com/">gdpx.semianalysis.com - GDPx: The General Agentic Benchmark</a></li>
<li><a href="https://www.datastudios.org/post/claude-opus-5-5-tops-semianalysis-gdpx-agent-benchmark-12-percent">Claude Opus 5.5 tops SemiAnalysis GDPx agent benchmark with ...</a></li>

</ul>
</details>

**标签**: `#AI benchmarks`, `#frontier models`, `#model evaluation`, `#GDPx`, `#agentic AI`

---

<a id="item-tech-news-10"></a>
### [三星与 SK 海力士据报采用长江存储 Xtacking 技术](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

据凤凰网报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分技术；三星、SK 海力士和长江存储均拒绝置评，协议是否最终执行尚无法确认。Xtacking 将存储单元和 CMOS 控制电路分别制作在两片晶圆上，再通过键合工艺合二为一，使两部分可以独立生产和优化。

telegram · zaihuapd · 11月25日 14:33

**「背景」** 长江存储早在 2018 年就展示了 Xtacking 方案，该公司称此后已在全球提交逾 1.2 万件专利、在美国提交逾 4000 件专利申请（据 aiweekly 转述）。随着 3D NAND 堆叠层数持续增加、制造难度上升，把存储阵列与外围逻辑电路分开制作再键合的思路才被更多厂商视为可行选项。此次报道最初来自日经亚洲，其称三星与 SK 海力士已与长江存储达成交叉许可（TrendForce、sammyguru 均转述日经）。

**「影响」** Omdia 高级分析师指出，这种分离生产的方式可让厂商自行制造存储阵列，并把逻辑电路交给晶圆代工厂，从而使用更先进的制程；若该安排实施，三星和 SK 海力士的 3D NAND 逻辑部分可能使用外部代工能力，但报道未说明具体制程、产品范围或时间表。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.trendforce.com/news/2026/11/25/news-sk-hynix-reportedly-joins-samsung-in-licensing-ymtcs-xtacking-technology-as-nand-race-heats-up/">[News] SK hynix Reportedly Joins Samsung in Licensing YMTC’s ...</a></li>
<li><a href="https://aiweekly.co/alerts/samsung-and-sk-hynix-tap-ymtcs-xtacking-tech-in-cross-license">Samsung and SK Hynix cross-license YMTC&#x27;s Xtacking 3D NAND</a></li>
<li><a href="https://sammyguru.com/samsung-sk-hynix-ymtc-xtacking-nand-technology/">Samsung and SK hynix Want to License YMTC&#x27;s Xtacking Technology</a></li>

</ul>
</details>

**标签**: `#3D NAND`, `#Xtacking`, `#YMTC`, `#Samsung`, `#SK Hynix`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美商务部被曝威胁英特尔交出 10%股权](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

据 Wired 报道，美国商务部律师在 2025 年 8 月与英特尔首席财务官通话时称，董事会可以拒绝交出 10%股权，但会带来无法预测的后果；几天后，英特尔董事会交出了美方要求的股份。特朗普随后表示，美国政府未支付对价即“完全拥有并控制”英特尔 10%股份，这批股份现值约 110 亿美元。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 这些细节出自英特尔股东诉讼中被解封的法庭文件：股东理查德·佩斯纳（Richard Paisner）起诉公司董事会，指其屈从于商务部的要求（tool-1-3）。据法庭文件报道，美方索要的约 10%股权对应此前已发放的 89 亿美元联邦补贴，英特尔董事会在会议纪要中称相关条款“缺乏吸引力”，但最终仍予接受（tool-1-2）。

**「影响」** 对英特尔股东而言，政府没有付钱就取得 10%股份，意味着公司治理中新增一个持股 10%的政府股东，董事会决策和股东权利将直接受到影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gate.com/news/detail/us-commerce-department-threatened-intel-over-10-equity-stake-for-89b-25860002">U.S. Commerce Department Threatened Intel Over 10% Equity ...</a></li>
<li><a href="https://phemex.com/news/article/intel-shareholder-sues-board-over-coerced-10-stake-handover-to-us-government-104804">Intel Shareholder Sues Board Over US Government 10% Stake De ...</a></li>
<li><a href="https://www.cnbc.com/2025/08/22/intel-goverment-equity-stake.html">U.S. takes 10% stake in Intel Trump expands control of ... - CNBC</a></li>

</ul>
</details>

**标签**: `#美国政府持股`, `#英特尔`, `#半导体政策`, `#产业政策`, `#法庭文件`

---

<a id="item-finance-news-2"></a>
### [美国拟对 14 个贸易伙伴加征第 301 条关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

美国政府提议依据 1974 年《贸易法》第 301 条，对中国、欧盟、日本、印度等 14 个贸易伙伴按国别加征新关税，理由是制造业存在结构性产能过剩。对中国拟在 2018 年已加征的 25%关税之上再加征 20%，若中国未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，对华新关税可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 第 301 条授权美国贸易代表办公室调查并应对外国不公平贸易做法，可据此加征关税；美方今年 3 月已就制造业“结构性产能过剩”启动相关调查。2025 年 10 月 30 日，中美领导人在韩国釜山达成为期一年的贸易休战，同意降低部分关税和出口管制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ustr.gov/trade-topics/enforcement/section-301-investigations/section-301-structural-excess-capacity-and-production-manufacturing-sectors">Section 301 – Structural Excess Capacity and Production in ...</a></li>
<li><a href="https://www.congress.gov/crs_external_products/IF/PDF/IF11346/IF11346.31.pdf">Section 301 of the Trade Act of 1974 - Congress.gov</a></li>
<li><a href="https://ustr.gov/about/policy-offices/press-office/press-releases/2026/march/ustr-initiates-section-301-investigations-relating-structural-excess-capacity-and-production">USTR Initiates Section 301 Investigations Relating to ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Busan_Summit">Busan Summit - Wikipedia</a></li>
<li><a href="https://www.cfr.org/articles/united-states-and-china-agree-trade-truce">United States and China Agree to Trade Truce | Council on ...</a></li>

</ul>
</details>

**标签**: `#US tariffs`, `#Section 301`, `#China trade`, `#EU trade`, `#global trade policy`

---