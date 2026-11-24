---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 35 条内容中筛选出 14 条重要资讯。

---

**科技新闻**
1. [Quad9 因法国法律限制停用法国 DNS 服务](#item-tech-news-1) ⭐️ 8.0/10
2. [AMD EPYC Zen 6 对比 Zen 1：几何平均性能提升 12.1 倍](#item-tech-news-2) ⭐️ 8.0/10
3. [Ladybird 发布首个 alpha，macOS 与 Linux 可直接安装](#item-tech-news-3) ⭐️ 8.0/10
4. [Anthropic 称内部 Claude 发现 VP≠VNP 并公开 Lean 4 证明](#item-tech-news-4) ⭐️ 8.0/10
5. [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](#item-tech-news-5) ⭐️ 8.0/10
6. [vCenter 修复 9.8 分免鉴权漏洞，此前据称遭零日利用](#item-tech-news-6) ⭐️ 8.0/10
7. [Stalwart 宣称可即插即用替代 Microsoft Exchange](#item-tech-news-7) ⭐️ 7.0/10
8. [围绕 Brendan Gregg 谈火焰图与确定性虚拟机的局限](#item-tech-news-8) ⭐️ 7.0/10
9. [GLM-5.4 发布：Z.ai 首个循环 Transformer 编码模型](#item-tech-news-9) ⭐️ 7.0/10
10. [黄循财：新加坡不会成为规避美国芯片管制的通道](#item-tech-news-10) ⭐️ 7.0/10

**科技博客**
1. [vLLM-GR：生成式推荐推理框架](#item-tech-blog-1) ⭐️ 7.0/10
2. [vLLM 插件实现 ERNIE 5.5 Flash 首日支持](#item-tech-blog-2) ⭐️ 5.0/10

**财经新闻**
1. [纽约联储行长威廉姆斯：通胀仍过高，抗通胀“仍有工作要做”](#item-finance-news-1) ⭐️ 7.0/10
2. [小米三季度经调整净利同比降 56.8%，汽车交付超 10 万辆](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Quad9 因法国法律限制停用法国 DNS 服务](https://quad9.net/news/blog/quad9-service-deactivation-in-france/) ⭐️ 8.0/10

Quad9 宣布因法国法律限制，已停用其在法国的 DNS 解析服务。社区测试显示，自 2026 年 11 月 24 日起，向 9.9.9.9 发起的查询会返回 REFUSED，并带有 EDE 18（Prohibited）及“Service unavailable due to French legal constraints”说明。法国境内将 Quad9 用作上游解析器的用户和网络管理员因此需要改用其他解析器。

hackernews · farrokhi · 11月24日 08:33 · [社区讨论](https://news.ycombinator.com/item?id=50625384)

**「背景」** Quad9 是一家非营利的免费公共 DNS 解析器；法国法院此前命令它屏蔽被指侵犯版权的网站（TorrentFreak 报道称涉及盗版网球直播），但 Quad9 拒绝执行。EFF 在 2026 年 10 月 27 日的报道中称，Quad9 因此决定于 11 月 24 日停止为法国用户提供服务；Quad9 的公告随后确认，巴黎时间当天 09:00 起，发往其服务地址的查询将被拒绝。

**「实际影响」** 影响集中在法国境内把 Quad9 作为上游的部署：有评论报告 AdGuard Home 因无法访问上游而导致局域网“断网”，运维者需切换到其他递归解析器或调整转发配置。

**「社区讨论」** 评论中有人用 dig 复现了 REFUSED/EDE 18 响应，也有人报告 AdGuard Home 上游失效导致家庭网络中断；另有评论者批评 Quad9 的处理方式，并讨论按法国 ASN 屏蔽的思路。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://quad9.net/news/blog/quad9-service-deactivation-in-france/">Quad9 Service Deactivation in France</a></li>
<li><a href="https://torrentfreak.com/quad9-exits-france-as-expired-piracy-order-lingers-at-google-and-isps/">Quad9 Exits France as Expired Piracy Order Lingers at Google ...</a></li>
<li><a href="https://www.eff.org/deeplinks/2026/10/french-courts-site-blocking-orders-drive-quad9-out-france">French Court’s Site-Blocking Orders Drive Quad9 Out Of France</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet infrastructure`, `#privacy`, `#internet censorship`, `#France`

---

<a id="item-tech-news-2"></a>
### [AMD EPYC Zen 6 对比 Zen 1：几何平均性能提升 12.1 倍](https://www.phoronix.com/review/amd-epyc-9006-7601) ⭐️ 8.0/10

Phoronix 发布了一项 AMD EPYC 服务器 CPU 的代际基准测试，将 Zen 6 与 Zen 1 对比，报告几何平均性能提升 12.1 倍，时间跨度不到十年。这是一项媒体基准评测，并非厂商产品发布。该对比横跨核心数、缓存、内存和 PCIe 等平台配置差异，因此 12.1 倍应理解为整机平台级提升，而不是同规格下的纯架构 IPC 增益。

hackernews · zdw · 11月24日 05:15 · [社区讨论](https://news.ycombinator.com/item?id=50624061)

**「背景」** 这项对比以 AMD 第一代 Zen 架构的 EPYC 服务器处理器为起点，对照当前的 Zen 6 平台。Phoronix 给出的 12.1x 是跨多项测试的几何平均值，而非单一工作负载的结果；由于两代平台的核心数、缓存、内存通道和 PCIe 规格均已变化，这一汇总数字同时包含单核性能提升与平台规模扩大带来的收益。

**「升级评估提示」** 对仍运行 Zen 1 平台的服务器运维者，这项对比可作为升级收益的量级参考，但预算评估必须把核心数增加带来的吞吐增长与单核性能提升分开计算，并另行核对功耗、内存成本和按核心计费的软件许可，否则 12.1 倍会高估同核数替换的收益。

**「评论中的分歧」** 评论区最集中的讨论是把 12.1 倍拆成两部分：x-complexity 依据 Phoronix 的测试配置估算，核心数从 64 增至 192 已带来约 3 倍提升，剩余约 4.03 倍来自单核与架构改进；kvemkon 则提醒，若把价格上涨计入，编译等场景的性价比未必同步提升，且今天的软件栈已不同于 Zen 1 时代。skywal\_l 引用测试称每瓦性能约为 5 倍，samuelknight 则认为软件栈进步会让实际体验改善高于纯硬件对比。

**标签**: `#AMD EPYC`, `#Zen 6`, `#server CPUs`, `#performance benchmarks`, `#hardware`

---

<a id="item-tech-news-3"></a>
### [Ladybird 发布首个 alpha，macOS 与 Linux 可直接安装](https://simonwillison.net/2026/Nov/23/ladybird/) ⭐️ 8.0/10

Ladybird 发布了首个 alpha 版本，macOS 和 Linux 用户现在可以直接下载安装，无需自行编译。这个独立浏览器引擎自行实现 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 等核心组件，同时复用 HarfBuzz、Skia、ffmpeg 和 SQLite 等外部库。官方提醒，alpha 阶段部分网站无法正常工作，浏览器有时也会崩溃；用户可从浏览器内报告损坏站点，并选择是否发送崩溃报告。

rss · Simon Willison · 11月23日 21:46

**「背景」** Ladybird 的前身是 SerenityOS 项目，部分核心代码直接沿袭自后者。该项目在 2026 年 2 月还宣布借助 Claude Code 和 Codex，将 LibJS 的部分代码从 C++ 移植为约 2.5 万行 Rust，这构成其近期加速开发的具体背景。

**「影响」** 对希望评估这一新引擎的开发者，当前更合适的用途是站点兼容性测试而非日常使用：Simon Willison 的测试中，ffmpeg 与 Pyodide 的 WebAssembly 示例可运行，但 Datasette Lite 因 \`navigator.serviceWorker.startMessages\` 未实现而失败，他已提交 issue 并在源码中看到相应 FIXME。

**标签**: `#browsers`, `#open-source`, `#Ladybird`, `#web-engines`, `#software-engineering`

---

<a id="item-tech-news-4"></a>
### [Anthropic 称内部 Claude 发现 VP≠VNP 并公开 Lean 4 证明](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

11 月 24 日，Anthropic 在 GitHub 的 formal-math 仓库公开论文《VP ≠ VNP over every field》及配套 Lean 4 形式化证明；仓库称结果由内部研究用 Claude 模型发现，论文与代码均由 AI 撰写。论文给出哈密顿圈多项式的超多项式算术电路下界，据此推出 VP 是 VNP 的真子类，若成立即解决 Valiant 1979 年提出的代数复杂度猜想，但结论只针对算术电路，不涉及 P 与 NP 的关系。据该帖，证明已通过三条标准公理审计并经独立内核 nanoda 复核，除预留文件外不含 sorry；不过尚无人类数学家通读，Lean 只能保证形式化本身可核验，无法确认其陈述与论文声称的命题一致，附录 Q 还列出了若干出入，结果仍待独立审阅。

telegram · zaihuapd · 11月24日 06:02

**「背景」** Valiant 在 1979 年提出代数复杂度类 VP 与 VNP，并追问 VP 是否为 VNP 的真子类；这被视为 P 与 NP 问题在算术电路模型中的类比，但解决它并不直接等同于解决 P 与 NP。该猜想已悬置约 47 年，是代数复杂性理论的核心开放问题之一。

**「影响」** 对代数复杂度理论研究者而言，目前可用的产物是一个通过内核检查的 Lean 4 形式化证明，而非已获确认的定理：在引用或在此基础上继续工作之前，需由人类专家核对该形式化语句是否确实表达了 VP≠VNP，并厘清附录 Q 所列与论文表述的出入。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://interestingengineering.com/ai-robotics/claude-proves-vp-not-vnp-valiant-conjecture">Claude claims to prove VP VNP in Valiant&#x27;s 47-year-old conjecture</a></li>

</ul>
</details>

**标签**: `#complexity theory`, `#Lean 4`, `#formal verification`, `#AI for math`, `#Anthropic`

---

<a id="item-tech-news-5"></a>
### [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 8.0/10

百度在 11 月 24 日通过官方 X 账号宣布开源文心 5.5 Flash Preview，权重以 Apache 2.0 协议在 Hugging Face 和 ModelScope 开放，并可用 vLLM 或 SGLang 部署和微调。该模型采用 MoE 架构，总参数 280B、每 token 激活 14B，上下文长度为 1M token；百度称它是基于 ERNIE 5.5 Flash Base 训练的首个后训练模型。流传的基准图表给出 Terminal-Bench 4.0 46.5 分和 DeepSWE v1.1 71.2 分，但百度未说明这些成绩是否经过第三方独立验证。

telegram · zaihuapd · 11月24日 07:32

**「背景」** 文心 5.5 Flash Preview 早在 11 月 11 日就已在百度 ERNIE 官网亮相，当时给出的规格是 280B 总参数、每 token 激活 14B、100 万 token 上下文，并称权重“即将”以 Apache 2.0 协议开源（tool-2-1）。11 月 24 日的这次发布，是把当时的开源承诺落实为 Hugging Face 与 ModelScope 上可下载的权重，也因此才真正支持 vLLM、SGLang 本地部署与微调。

**「对开发者的影响」** 对已经使用 vLLM 或 SGLang 的团队来说，这次发布提供了按现有工具链部署并微调 Apache 2.0 权重的路径；实际采用时仍需按 280B 总参数和 1M token 上下文评估显存、吞吐与部署资源。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ernie.baidu.com/release/ernie-5-5-flash-preview/">Introducing ERNIE 5.5 Flash Preview · ERNIE - ernie.baidu.com</a></li>

</ul>
</details>

**标签**: `#open-source LLM`, `#Baidu ERNIE`, `#mixture-of-experts`, `#Apache 2.0`, `#model release`

---

<a id="item-tech-news-6"></a>
### [vCenter 修复 9.8 分免鉴权漏洞，此前据称遭零日利用](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom 为 VMware 产品线发布覆盖 23 个漏洞的补丁，其中包括 vCenter 目录服务（vmdir）的鉴权绕过漏洞 CVE-2026-123903，评分 9.8。该漏洞允许任何能访问 vCenter 的一方绕过认证直接进入系统。相关报告称，它在补丁发布前几天曾被作为零日漏洞利用；运行 vCenter 的团队需要据此核查受影响版本并安排修复。

telegram · zaihuapd · 11月24日 14:50

**「背景」** vCenter 是集中管理虚拟化环境的控制面，vmdir 则是其目录服务与身份认证组件。若攻击者能绕过 vmdir 的鉴权，就可能在无需有效凭据的情况下获得 vCenter 的管理访问权，因此这类免鉴权漏洞的评分和利用状态格外受关注。

**「实际影响」** 由于利用该漏洞只需能通过网络访问 vCenter，无需任何凭据或用户交互，暴露在管理网段之外或可从互联网触达的 vCenter 实例应被视为高风险资产；管理员应尽快套用此次包含 CVE-2026-123903 修复的补丁，并在打补丁前限制对 vCenter 管理接口的网络访问。参照上周的情况，同一目录服务组件的另一个鉴权绕过 CVE-2026-123890（同为 9.8 分，已在 VMSA-2026-0009 中修复）在补丁发布前即被疑似中国背景的 Armory Castle 组织作为零日利用，这表明此类 vCenter 免鉴权漏洞在真实环境中会被迅速武器化，不能按常规补丁周期排期。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.rapid7.com/blog/post/etr-cve-2026-123890-critical-authentication-bypass-vmware-vcenter/">CVE-2026-123890: Critical Authentication Bypass in VMware vCenter</a></li>
<li><a href="https://cybersecuritynews.com/vmware-vcenter-authentication-bypass/">Critical VMware vCenter Vulnerabilities Let Hackers Bypass ...</a></li>
<li><a href="https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html">VMware vCenter Hit by Another Critical 9.8-Rated Auth Bypass ...</a></li>

</ul>
</details>

**标签**: `#VMware vCenter`, `#critical vulnerability`, `#authentication bypass`, `#zero-day exploitation`, `#security patching`

---

<a id="item-tech-news-7"></a>
### [Stalwart 宣称可即插即用替代 Microsoft Exchange](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart 在博客中宣称自己可作为 Microsoft Exchange 的即插即用替代品，目标是帮助邮件服务器用户降低迁移与许可成本。但现有材料只有公告本身，未说明兼容的 Exchange 版本、支持的功能范围或迁移条件，因此这一“drop-in replacement”目前仍是项目方说法，而非已证实或独立验证的能力。

hackernews · shaunpud · 11月23日 22:32 · [社区讨论](https://news.ycombinator.com/item?id=50620349)

**「背景」** 长期以来，Microsoft Exchange 承担企业邮件服务器的角色，Outlook 则是与之配套的客户端；因此，“替代 Exchange”首先要解决的是服务器端协议兼容与数据迁移的问题，并不自动等同于 Outlook 客户端会获得支持。此次声明对应 Stalwart 1.2.0 版本；Stalwart 是开源邮件服务器，已有 Bulwark 这类通过 JMAP 连接它的网页客户端。

**「迁移影响」** 对仍运行本地 Exchange 的组织，迁移评估不能只看服务器端：Stalwart 的博客称 Exchange 2016/2019 已停止支持、微软正把 Exchange 推向云端，因此应先用现有 Outlook 版本验证连接和协议兼容性，而不能把“drop-in”视为已证实的能力。受监管用户还需单独确认归档能力；有评论指出 Stalwart 的常规/开源方案不包含德国 GoBD 要求的十年不可篡改归档，若属实这将成为采用前的硬门槛。

**「社区讨论」** 评论者质疑迁移可行性：有人指出 Outlook 正转向仅支持云端 Exchange，用户可能得先更换客户端；也有人称德国 GoBD 要求邮件以不可删除、不可篡改的方式归档并供税务部门访问最长十年，而 Stalwart 的常规套餐或开源版本不含该功能。另有评论认为支持 MAPI 等协议只会延续客户端和协议锁定、不利于开放邮件生态，并提到 Mozilla 的 Thundermail 使用 Stalwart。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop - in replacement for Microsoft Exchange</a></li>
<li><a href="https://bulwarkmail.org/">Bulwark - JMAP Webmail Client for Stalwart Mail Server</a></li>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop-in replacement for Microsoft Exchange | Stalwart</a></li>

</ul>
</details>

**标签**: `#email servers`, `#open source`, `#Microsoft Exchange`, `#self-hosting`, `#interoperability`

---

<a id="item-tech-news-8"></a>
### [围绕 Brendan Gregg 谈火焰图与确定性虚拟机的局限](https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg) ⭐️ 7.0/10

这是一篇技术博客随笔，以 Brendan Gregg 的剖析（profiling）工作为线索，讨论性能分析方法、确定性虚拟机（deterministic VM）以及火焰图在诊断中的局限。文章属于分析/观点类内容，而非产品发布、版本更新或独立基准测试；由于未提供原文正文，其具体实现方式与实测数据无法在此核实。标题中的「朝圣」口吻表明作者是以 Gregg 的方法论为参照展开评述，而非报道某一项新能力上线。

hackernews · kqr · 11月24日 10:50 · [社区讨论](https://news.ycombinator.com/item?id=50626413)

**「背景」** 这类讨论中的“确定性虚拟机”指让程序执行可重复回放、便于反复比较的分析环境，而不是只靠采样观察。评论中拿来类比的 rr 是 Linux 上的记录—回放调试器：它只记录执行中的非确定性事件（尤其是系统调用结果），之后可在未修改的硬件、编译器和操作系统上逐位重放，并在 gdb 下支持反向执行。

**「影响」** 对性能工程师而言，实际的采纳条件在于工具的线程模型是否与待分析的负载匹配：评论者指出，若确定性 VM 为单线程设计，则在分析高吞吐多线程管线时可能损失关键的并发信息；同理，异步代码（协程、fiber、future）的关键路径能否被这类方法捕获也仍存疑问。因此在使用前应先确认分析手段能否覆盖目标负载的并发结构，而不是直接套用单线程场景下的结论。

**「社区讨论」** 有评论者表示，自己已对用火焰图做多线程性能分析「降温」，因为跨线程依赖关系极难从图中推断，尽管他同时认可确定性 VM 的思路（并将其与 Antithesis 类比）。另有读者询问该方法与 rr 记录/回放调试器在功能与限制上的异同，还有人提出可用 sleep profiling 或 CPU stall profiling 达到类似目的，代价是要在 Linux 内核中做权衡或增加 CPU 晶体管。关于异步负载，一位评论者认为若不改动框架代码（例如在请求上下文中嵌入标识以追踪跨线程的续延），定位关键路径几乎不可能。以上均为评论者的个人判断，不代表已证实的结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Rr_%28debugging%29">rr (debugging) - Wikipedia</a></li>
<li><a href="https://github.com/acailic/agent_debugger/blob/main/docs/papers/rr-engineering-record-and-replay.md">agent_debugger/docs/papers/rr-engineering-record-and-replay ...</a></li>

</ul>
</details>

**标签**: `#performance analysis`, `#flamegraphs`, `#deterministic VM`, `#profiling`, `#async workloads`

---

<a id="item-tech-news-9"></a>
### [GLM-5.4 发布：Z.ai 首个循环 Transformer 编码模型](https://simonwillison.net/2026/Nov/23/glm-54/) ⭐️ 7.0/10

Z.ai 发布了 GLM-5.4，这是该公司首个采用循环 Transformer（Loop Transformer）架构的模型，定位为通用编码任务。按 Z.ai 的说法，标准 Transformer 每层在一次前向传播中只运行一次，而循环 Transformer 让一组共享权重的层迭代多次、不断精化隐藏状态，从而在不增加参数量的前提下加深网络。Simon Willison 指出，这是他在一周内第二次看到循环 Transformer：Thinking Machines Lab 于 11 月 20 日发布的 Inkling 2 Mini 也把中间层对每个 token 运行三次。GLM-5.4 目前尚未以开放权重形式发布，也无法通过常规 API 访问，需订阅 Z.ai 的 Coding Plan 才能使用；Willison 实测发现 Coding Plan 的 API key 可用于同一套 OpenAI 兼容的 Responses API（https://api.z.ai/api/v1）。

rss · Simon Willison · 11月23日 23:40

**「背景」** 常规 Transformer 中，每个层在一次前向传播中只执行一次；循环 Transformer 则让一组共享权重的层重复运行多次，在前一轮隐藏状态的基础上继续细化，因此能在不增加参数量的情况下提高有效深度。GLM-5.4 发布前几天，Thinking Machines Lab 的 Inkling 2 Mini 也采用了循环结构，并称其中间层会对每个 token 运行三次。

**「影响」** 对想试用该模型的开发者而言，当前唯一的入口是订阅 Coding Plan，而不是按量计费的常规 API，这会直接影响接入方式与成本预期；好消息是 Coding Plan 的密钥可沿用标准 OpenAI 兼容接口，无需另建调用路径。工具链上仍有缺口：现有的 llm-zai 插件尚未支持 GLM-5.4，Willison 因此临时发布了自己的 llm-glm 插件，并表示待 llm-zai 跟上后会考虑弃用。

**标签**: `#LLM architecture`, `#looped transformers`, `#GLM-5.4`, `#AI model release`, `#coding models`

---

<a id="item-tech-news-10"></a>
### [黄循财：新加坡不会成为规避美国芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，新加坡不会成为企业规避美国芯片出口管制的通道，当局正在调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单，《联邦公报》称这些企业存在向未获授权用户转移先进计算产品的“重大风险”，名单还包括其在马来西亚和泰国的关联实体。路透社报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 同样在列；阿里巴巴称从未转移受管制的先进计算芯片。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 被列入美国商务部实体清单的企业，在采购受美国出口管制约束的物项（包括先进计算芯片）前须获得许可，审批通常从严。美国近年来不断收紧对先进计算芯片的出口限制，东南亚因转口贸易活跃而成为执法关注区域，这也是新加坡总理此时就「通道」问题表态的直接背景。

**「对相关企业的直接影响」** 被列入实体清单后，Megaspeed、Apex Enterprise Solutions 等实体在获取美国受管制先进计算产品时须申请出口许可，实际采购渠道将明显收窄；阿里巴巴方面已表示 Apex 从未转移受管制的先进计算芯片，称此次列名有误。对经新加坡、马来西亚或泰国中转 AI 芯片的企业来说，黄循财的表态意味着当地监管会配合美方执法，相关方需要重新核查最终用户与转运路径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/ai/articles/us-blacklists-alibaba-owned-company-014536273.html">US Blacklists Alibaba-Owned Company in Setback to AI Ambitions</a></li>
<li><a href="https://www.straitstimes.com/world/united-states/us-blacklists-megaspeed-chip-firm-linked-to-nvidia-scandal">US blacklists Megaspeed , Alibaba unit amid... | The Straits Times</a></li>

</ul>
</details>

**标签**: `#export controls`, `#semiconductors`, `#Nvidia`, `#Singapore`, `#AI hardware`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM-GR：生成式推荐推理框架](https://vllm.ai/blog/2026-11-24-vllm-gr-announcement) ⭐️ 7.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 生成式推荐要在一个请求的延迟预算内，从用户的长交互历史中生成多个候选物品 ID。每个 ID 往往只包含少数几个 token，但服务必须并行探索大量候选路径，并确保结果能映射到真实物品目录。若按候选分别处理，就会重复计算用户历史，并增加主机与加速器之间的协调开销。

**「方案」** vLLM-GR 在 vLLM 的调度、模型执行和分页 KV 缓存之上加入贯穿整个搜索过程的 beam session：EngineCore 从请求准入到完成管理会话，调度器把 prefill/decode 阶段分派给 worker，模型运行器为下一个 token 打分，beam selection 记录存活路径的分数和父索引，下一次 decode 再据此读取正确的 KV 状态。候选路径共享用户历史的 prompt KV，同时主机在加速器执行当前阶段时准备下一阶段，形成 prefill–decode–decode 流水线；搜索既可覆盖全词表，也可按目录中的语义 ID 约束过滤，并支持逐阶段 beam 宽度和逐父候选上限。作者报告，在 H20、RTX PRO 6000、A100、L20 及 Ascend A2/A5 上，beam 宽度为 256、batch 为 4 或 8 时，vLLM-GR 的 P99 最低；例如 H20 batch 8 为 369.4 ms，SGLang 为 1,280.1 ms，NVIDIA SID-GR 为 428.1 ms。不过作者也承认，RTX PRO 6000 在 beam 256、batch 1 时 SID-GR 的 28.25 ms 优于 vLLM-GR 的 29.21 ms；各后端计时口径、样本数以及部分后端配置并不一致，这些基准又由项目团队运行，因此结论主要适用于生成式推荐服务。

**「启示」** 作者认为，把推荐搜索原生化到 vLLM 的 KV 缓存和调度路径中，能在宽束搜索与高并发下显著压低尾延迟；其更大意义是为同时承载候选生成与排序的推荐服务打基础，但跨后端公平比较仍有待更完整的基准元数据。

**标签**: `#vLLM`, `#generative recommendation`, `#beam search`, `#LLM inference serving`, `#KV cache`

---

<a id="item-tech-blog-2"></a>
### [vLLM 插件实现 ERNIE 5.5 Flash 首日支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 5.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** ERNIE 5.5 Flash Preview 是总参数 280B、每 token 激活 14B 的稀疏 MoE 模型，支持 1M token 上下文和工具调用；vLLM 需在模型发布当天提供可部署支持，而不必维护专用分支或等待 nightly 构建。

**「方案」** 作者介绍，vLLM 通过独立插件 vLLM-ERNIE 在官方 vllm==0.32.0 上实现首日支持，插件经 vllm.general\_plugins 自动注册模型、分词器和聊天/工具调用解析器，并只在加载对应架构时导入模型代码。模型 43 层中 37 层用 HCA、6 层用 MLA-DSA；作者称针对 VHA、Multi-Router Latent MoE 和 MultiMax 输出头的融合内核，比逐算子实现快 1.55–6.53 倍。默认检查点将路由专家量化为 MXFP4（W4A8）、其余权重和 KV 缓存用 FP8，配套 3 层 MoE DSpark 草稿模型每步最多提议 7 个 token，并称在真实编码与 Agent 负载上平均接受长度超过 4.0。FlashIndexer 通过动态头路由和阈值预过滤降低长上下文索引成本，作者报告 1M 上下文下约 40% 加速（另处称 1.4×）；部署还支持专家并行、TP2/4/8 注意力张量并行、Mooncake PD 分离和 KV 缓存卸载。上述性能数字来自厂商发布说明，未附完整基准方法、基线与取舍分析。

**「启示」** 作者认为，独立插件让模型专用代码和内核按模型节奏发布，同时复用 vLLM 的服务与并行能力，是高效的首日支持路径；但文中加速数据仍待独立基准验证。

**标签**: `#vLLM`, `#ERNIE 5.5 Flash`, `#MoE inference`, `#kernel fusion`, `#model serving`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [纽约联储行长威廉姆斯：通胀仍过高，抗通胀“仍有工作要做”](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储行长约翰·威廉姆斯 11 月 23 日表示，美联储要让通胀回到 2%“仍有工作要做”，并称确保通胀及时、持续回落的行动可能“随时间推进”。他没有直接谈及 12 月会议，但市场目前预计，12 月 8 日至 9 日的会议将加息 25 个基点，把联邦基金利率目标区间从 3.75%-4%上调。

rss · CNBC Finance · 11月24日 13:33

**「背景」** 美联储的长期通胀目标是 2%，而上一次联邦公开市场委员会（FOMC）会议在 10 月底会后声明中表示，将依靠“积累更多信息”来决定后续政策路径；下一次议息会议定于 12 月 8 日至 9 日举行。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#John Williams`

---

<a id="item-finance-news-2"></a>
### [小米三季度经调整净利同比降 56.8%，汽车交付超 10 万辆](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

小米集团公布的 2026 年第三季度财报显示，经调整净利润为 48.84 亿元人民币，同比下降 56.8%，但仍略高于市场预期的 47.46 亿元；总营收 1072.4 亿元，同比下降 5.2%。同期汽车业务交付新车 100,975 辆。

telegram · zaihuapd · 11月24日 10:09

**「背景」** 小米同时经营智能手机与新能源汽车两块业务，单季利润既受手机零部件成本波动影响，也受汽车业务投入拖累；公司称本季盈利承压，主要原因是存储芯片等核心元器件涨价，以及研发投入加码。

**「影响」** 小米主动收缩中低端手机机型以拉高均价，预算有限的换机用户将面对更少的低价选择。

**标签**: `#Xiaomi`, `#quarterly earnings`, `#EV deliveries`, `#smartphone shipments`, `#China tech`

---