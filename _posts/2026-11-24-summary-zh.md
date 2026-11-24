---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 35 条内容中筛选出 15 条重要资讯。

---

**科技新闻**
1. [Ladybird 首个 Alpha 登陆 macOS 与 Linux](#item-tech-news-1) ⭐️ 8.0/10
2. [Anthropic 称 Claude 发现 VP≠VNP 并公布 Lean 4 证明](#item-tech-news-2) ⭐️ 8.0/10
3. [VMware vCenter 曝 9.8 分免鉴权漏洞，补丁前疑遭零日利用](#item-tech-news-3) ⭐️ 8.0/10
4. [Brendan Gregg 方法、火焰图与确定性 VM 的适用边界](#item-tech-news-4) ⭐️ 7.0/10
5. [Quad9 因法律限制撤出法国 DNS 服务](#item-tech-news-5) ⭐️ 7.0/10
6. [Stalwart 宣称可直接替换 Microsoft Exchange](#item-tech-news-6) ⭐️ 7.0/10
7. [《2035 came early》引发 LLM 低层开发讨论](#item-tech-news-7) ⭐️ 7.0/10
8. [Phoronix：EPYC 从 Zen 1 到 Zen 6 几何均值性能提升 12.1 倍](#item-tech-news-8) ⭐️ 7.0/10
9. [Z.ai 发布 GLM-5.4：首个循环 Transformer 模型](#item-tech-news-9) ⭐️ 7.0/10
10. [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](#item-tech-news-10) ⭐️ 7.0/10
11. [诺华 CEO：AI 十年内难治愈癌症，研发周期或缩短四年](#item-tech-news-11) ⭐️ 7.0/10

**科技博客**
1. [ERNIE 5.5 Flash 的 vLLM Day-0 插件支持](#item-tech-blog-1) ⭐️ 6.0/10
2. [vLLM-GR：生成式推荐推理框架](#item-tech-blog-2) ⭐️ 6.0/10

**财经新闻**
1. [黄循财：新加坡不会成为规避美国芯片管制的通道](#item-finance-news-1) ⭐️ 7.0/10
2. [小米 2026 年三季度经调整净利同比下降 56.8%，汽车交付 100,975 辆](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Ladybird 首个 Alpha 登陆 macOS 与 Linux](https://simonwillison.net/2026/Nov/23/ladybird/) ⭐️ 8.0/10

Ladybird 发布了首个 Alpha 版本，macOS 和 Linux 用户现在可以下载预编译安装包，无需自行编译。该浏览器使用独立实现的 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 组件，仅复用 HarfBuzz、Skia、ffmpeg 和 SQLite 等外部库；官方提醒这仍是 Alpha，部分网站无法使用且可能崩溃。项目 10 月通讯称，其将样式和布局移至独立线程、加入新的 JavaScript JIT，并把 WebAssembly 引擎替换为基于 Cranelift 的新实现，在 JetStream 3 WASM 基准上提升 7 倍，同时在 web-platform-tests 中新增 75,650 项通过、总数达到 2,184,722，超过 Safari。

rss · Simon Willison · 11月23日 21:46

**「背景」** Ladybird 是源自 SerenityOS 的独立浏览器项目，长期自行实现 HTML 解析、CSS 引擎、布局和 JavaScript 等核心组件，仍使用 HarfBuzz、Skia、FFmpeg 和 SQLite 等少量外部组件。2026 年 2 月，项目宣布借助 AI 编码工具把部分 LibJS 从 C++ 移植到 Rust；10 月又通过编码代理集中修复 Web Platform Tests 的缺口，单月新增 75,650 项通过。

**「影响」** 对希望评估新浏览器引擎但不想搭建编译环境的开发者，预编译包把试用门槛降到了直接下载安装；但依赖 service worker 的复杂 Web 应用仍可能失败，Simon Willison 测试 Datasette Lite 时就遇到 \`navigator.serviceWorker.startMessages\` 未实现，项目源码中也有相应 FIXME，因此目前不适合作为日常或生产浏览器。

**标签**: `#browser engines`, `#Ladybird`, `#open source`, `#alpha release`, `#web platform`

---

<a id="item-tech-news-2"></a>
### [Anthropic 称 Claude 发现 VP≠VNP 并公布 Lean 4 证明](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 8.0/10

Anthropic 的 formal-math 仓库于 11 月 24 日公开论文《VP ≠ VNP over every field》及 Lean 4 形式化证明，仓库称结果由内部研究用 Claude 模型发现，论文与代码均由 AI 撰写。论文给出哈密顿圈多项式的超多项式算术电路下界，据此推出 VP 是 VNP 的真子类；若成立，这将解决 Valiant 1979 年的代数复杂度猜想，但只针对算术电路，不涉及 P 与 NP。仓库称证明已按三条标准公理审计，并由独立内核 nanoda 复核，除预留文件外没有 sorry。尚无人类数学家通读，Lean 也无法确认形式化陈述与其声称命题一致，附录 Q 列出了出入，正等待独立审阅。

telegram · zaihuapd · 11月24日 06:02

**「背景：Valiant 的代数复杂度猜想」** VP 与 VNP 是代数复杂度理论中按算术电路规模划分的复杂度类；Leslie Valiant 在 1979 年提出 VP ≠ VNP 猜想，它常被视为 P ≠ NP 在代数电路模型中的对应问题，但两者并不等同。

**「审阅状态」** 对希望引用该结果的读者，目前可供检查的是公开的 Lean 4 代码以及仓库所述的公理和 nanoda 复核；在独立数学家核对形式化陈述与论文命题、尤其是附录 Q 所列出入之前，不应将其视为已确立的 VP≠VNP 证明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/anthropic-posts-claude-written-vp-vnp-proof-unverified">Anthropic posts Claude-written VP ≠ VNP proof, unverified</a></li>

</ul>
</details>

**标签**: `#complexity theory`, `#Lean 4`, `#AI for math`, `#formal verification`, `#Anthropic`

---

<a id="item-tech-news-3"></a>
### [VMware vCenter 曝 9.8 分免鉴权漏洞，补丁前疑遭零日利用](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom 为 VMware 产品线发布了覆盖 23 个漏洞的补丁，其中 vCenter 目录服务（vmdir）的鉴权绕过漏洞 CVE-2026-123903 被评为 9.8 分。该漏洞允许任何能访问 vCenter 的一方绕过认证直接进入系统。据报道，在补丁发布前几天，该漏洞已被作为零日漏洞利用；目前信息来自单一报道，尚无独立验证。

telegram · zaihuapd · 11月24日 14:50

**「背景」** vmdir（VMware Directory Service）是 vCenter 内部负责身份与认证的核心目录服务，一旦其认证逻辑可被绕过，攻击面就直接落在 vCenter 的入口认证环节，而不需要先取得任何账号凭据。据 The Hacker News 报道，此次 CVE-2026-123903 评分为 9.8，属于 vCenter 认证绕过类漏洞，且据称在 Broadcom 发布补丁前几天已被作为零日利用；不过另一家漏洞跟踪站点（securityonline.info）将利用状态标为“无已知利用”，说明公开信息对是否已遭实际利用仍不一致。

**「影响与处置」** 对运行 vCenter 的组织而言，该漏洞无需有效凭据，只要攻击者能通过网络访问 vCenter 即可绕过认证进入系统，因此暴露在不可信网络中的实例风险最高。在应用 Broadcom 本轮补丁前，应优先收敛 vCenter 的网络可达范围，避免管理接口对非受信来源开放。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html">VMware vCenter Hit by Another Critical 9.8-Rated Auth Bypass ...</a></li>
<li><a href="https://www.theexploitdesk.tech/article/vmware-vcenter-hit-by-another-critical-9-8-rated-auth-bypass-flaw-afte-ab68da">VMware vCenter Hit by Another Critical 9.8-Rated Auth Bypass ...</a></li>
<li><a href="https://securityonline.info/cve-watchtower/cve-2026-123903/">CVE-2026-123903: VMware vCenter, CVSS 9.8</a></li>

</ul>
</details>

**标签**: `#VMware vCenter`, `#authentication bypass`, `#zero-day exploitation`, `#security patching`, `#critical vulnerability`

---

<a id="item-tech-news-4"></a>
### [Brendan Gregg 方法、火焰图与确定性 VM 的适用边界](https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg) ⭐️ 7.0/10

这篇博文围绕 Brendan Gregg 的性能分析方法，介绍作者在确定性 VM 上进行性能剖析的实践，并讨论火焰图等工具在排障中的使用。它属于方法论与经验分享，而不是新工具或版本发布。文章引发的讨论进一步聚焦于这些方法在多线程和异步负载中的适用范围。

hackernews · kqr · 11月24日 10:50 · [社区讨论](https://news.ycombinator.com/item?id=50626413)

**「背景」** 火焰图由 Brendan Gregg 创造，并在《Communications of the ACM》上正式定义，如今已被多种编程语言和可观测性产品采纳为 CPU 性能分析的常用可视化方式（tool-2-1、tool-2-2）。与此同时，关于火焰图采样偏差和性能盲点的讨论也已出现（tool-2-3），这为文章及其评论区围绕多线程与异步工作负载的争论提供了背景。

**「影响」** 对准备采用类似方法的性能工程师而言，评论者提出的实际疑问是：单线程确定性 VM 可能难以代表高吞吐多线程流水线，而异步请求的关键路径追踪往往还需要在框架中嵌入请求上下文，才能把不同线程上的后续任务关联起来。

**「社区讨论」** 有评论者表示已对用火焰图做多线程性能分析明显降温，因为跨线程依赖很难从图中推断；也有人追问单线程确定性 VM 对高吞吐多线程管线的代表性。另有评论指出，若不修改框架（例如嵌入请求上下文），很难判断线程 A 上的后续任务是否其实是请求 R 的延续。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.brendangregg.com/flamegraphs.html">Flame Graphs - Brendan Gregg</a></li>
<li><a href="https://www.brendangregg.com/Slides/YOW2022_flame_graphs/">YOW2022_flame_graphs.pdf - Brendan Gregg</a></li>
<li><a href="https://martinuke0.github.io/posts/2026-05-22-deep-dive-into-flame-graphs-profiling-blind-spots-sampling-bias-and-hidden-execution-costs/">Deep Dive into Flame Graphs: Profiling Blind Spots, Sampling ...</a></li>

</ul>
</details>

**标签**: `#performance profiling`, `#flame graphs`, `#deterministic VMs`, `#multithreaded analysis`, `#async profiling`

---

<a id="item-tech-news-5"></a>
### [Quad9 因法律限制撤出法国 DNS 服务](https://quad9.net/news/blog/quad9-service-deactivation-in-france/) ⭐️ 7.0/10

Quad9 已停止在法国提供公共 DNS 服务，原因是法国法律限制，法国境内依赖其解析的用户和本地网络会受到影响。Quad9 使用 9.9.9.9 等地址；给定材料没有说明具体法律依据、是否覆盖所有法国出口流量，或服务何时恢复。

hackernews · farrokhi · 11月24日 08:33 · [社区讨论](https://news.ycombinator.com/item?id=50625384)

**「背景」** Quad9 是一家免费公共 DNS 解析器，2017 年上线时以 9.9.9.9 地址提供解析服务，并根据每日聚合的威胁情报源拦截恶意域名。

**「对法国用户的实际影响」** 自 2026 年 11 月 24 日起，在法国境内发往 Quad9 任意服务地址的 DNS 查询都会被拒绝，返回 REFUSED 并附带 EDE 18（因法国法律限制而不可用），因此把 9.9.9.9 直接写进路由器、防火墙或 AdGuard Home 上游的法国用户会立刻无法解析域名，必须改配其他递归解析器或上游服务。鉴于法院此前因 Quad9 未屏蔽被指侵权的域名而对其处以每日 1,000 欧元的罚款，切换到其他境外公共解析器并不等于规避同类屏蔽义务，网络管理员在选型时应把这一法律风险一并纳入考虑。

**「社区讨论」** 有用户报告，其局域网提示互联网断开，后来发现是 AdGuard Home 无法访问上游；另一位用户贴出的 dig 查询显示，向 9.9.9.9 发起的请求返回 REFUSED，并附带 EDE 18（Prohibited）和“Service unavailable due to French legal constraints”。也有评论质疑 Quad9 的处理方式，称其显得不够专业，这属于个人评价而非已证实的技术结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arstechnica.com/information-technology/2017/11/new-quad9-dns-service-blocks-malicious-domains-for-everyone/">New “ Quad 9 ” DNS service blocks malicious domains ... - Ars Technica</a></li>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://quad9.net/news/blog/quad9-service-deactivation-in-france/">Quad9 Service Deactivation in France</a></li>
<li><a href="https://quad9.net/news/blog/au-revoir-france/">Farewell, France | Quad9</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet privacy`, `#censorship`, `#France`, `#network infrastructure`

---

<a id="item-tech-news-6"></a>
### [Stalwart 宣称可直接替换 Microsoft Exchange](https://stalw.art/blog/microsoft-exchange-replacement/) ⭐️ 7.0/10

Stalwart 在博客中宣称，其邮件服务器已成为 Microsoft Exchange 的直接替换方案，面向考虑迁移到开源、自托管邮件基础设施的系统管理员和组织。现有材料未给出具体版本、兼容范围或独立验证结果，因此这仍是厂商公告，而非已证实的能力。社区还指出，德国 GoBD 等合规归档要求可能构成实际障碍，因为 Stalwart 的常规套餐和开源版本不含相关功能。

hackernews · shaunpud · 11月23日 22:32 · [社区讨论](https://news.ycombinator.com/item?id=50620349)

**「背景」** Exchange 长期是企业邮件服务器，而 Outlook 等客户端依赖 MAPI、EWS、ActiveSync 和 Autodiscover 等微软协议与自动发现机制来连接邮箱。Stalwart 1.2.0 的发布信息称，这个开源邮件服务器已支持上述接口，因此现有 Outlook 客户端无需更换即可连接，这也是其“可直接替换 Exchange”说法的技术前提。

**「迁移前需核对 Outlook 客户端」** 计划用 Stalwart 替换本地 Exchange 的组织应先核对客户端兼容性：微软支持社区 2025 年 7 月的答复称，新版 Outlook for Windows 尚不支持本地 Exchange，该功能仍只存在于经典 Outlook 中。因此“可直接替换 Exchange”不应被理解为新版 Outlook 用户也能无缝连接，迁移前需用实际客户端验证。

**「社区讨论」** 评论者 hobo123 质疑迁移路径：如果 Outlook 不再支持本地 Exchange，用户可能得先换客户端才能使用 Stalwart；rmoriz 则指出，德国企业或自由职业者须按 GoBD 以防篡改方式归档邮件，最长保存 10 年，而 Stalwart 的常规方案和开源版本并不包含这一功能。andreashaerter 认为，继续支持 MAPI 等微软协议只会进一步固化协议和客户端锁定，不利于开放邮件生态。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://stalw.art/blog/microsoft-exchange-replacement/">Stalwart is now a drop-in replacement for Microsoft Exchange</a></li>
<li><a href="https://www.learn.telusko.com/newsletter/stalwart-1-2-0-is-now-a-drop-in-replacement-for-microsoft-exchange">Stalwart 1.2.0 is now a drop-in replacement for Microsoft ...</a></li>
<li><a href="https://learn.microsoft.com/en-us/answers/questions/2337260/unable-to-connect-on-premise-exchange-2016-2019-se">unable to connect on-premise exchange 2016/2019 server to new ...</a></li>

</ul>
</details>

**标签**: `#open-source email`, `#Microsoft Exchange`, `#email servers`, `#interoperability`, `#self-hosting`

---

<a id="item-tech-news-7"></a>
### [《2035 came early》引发 LLM 低层开发讨论](https://fzakaria.com/2026/11/23/2035-came-early) ⭐️ 7.0/10

Hacker News 上题为《2035 came early》的帖子获得 723 分和 268 条评论，讨论集中在 AI 辅助的软件与系统开发，尤其是用 LLM 构建低层项目。由于原文正文未提供，帖子的具体技术主张无法核实；现有材料主要显示评论者围绕“通过提示 Claude 编排项目”的实践及其影响展开争论。

hackernews · setheron · 11月24日 06:30 · [社区讨论](https://news.ycombinator.com/item?id=50624497)

**「背景」** 这一讨论的背景是，LLM 编程工具正被用于从常规软件延伸到更低层的系统项目；评论中，gbl08ma 称自己用两个月时间“提示 Claude”开发 waarm64.com，并把该项目与另一个项目 unkernel 相提并论。

**「社区讨论」** 评论区最具体的经验来自 gbl08ma：他称自己投入超过 100 小时，却因 unkernel 先获得关注而匆忙发布 waarm64.com，并对此感到失落。其他评论则转向对 Gary Bernhardt 的推崇，以及 JavaScript 是否真的主导软件业的争论，显示讨论并未就 LLM 低层开发形成一致判断。

**标签**: `#AI coding agents`, `#systems programming`, `#operating systems`, `#software engineering`, `#Hacker News discussion`

---

<a id="item-tech-news-8"></a>
### [Phoronix：EPYC 从 Zen 1 到 Zen 6 几何均值性能提升 12.1 倍](https://www.phoronix.com/review/amd-epyc-9006-7601) ⭐️ 7.0/10

Phoronix 发布跨代 EPYC 基准对比，在双路 Zen 1（Naples）与双路 Zen 6（Venice）之间测得 12.1 倍的几何均值性能提升，跨度不到十年。这个数字是大型测试套件的聚合结果，不能等同于任一单线程或真实业务负载的提速；评论区围绕提升该如何归因，以及编译和能效表现展开了讨论。特定 SKU、频率和价格细节来自评论引用，未在给定材料中独立核实。

hackernews · zdw · 11月24日 05:15 · [社区讨论](https://news.ycombinator.com/item?id=50624061)

**「背景」** EPYC 9006（代号 Venice）是 AMD 的 Zen 6 服务器平台。2026 年 7 月公布时，AMD 未提供完整的 SKU 表，SP7 平台要到第四季度才可用，因此 Phoronix 将其视为一次软发布；直到 11 月，AMD 才披露完整的频率、缓存和架构细节。Phoronix 的跨代对比因此把 2P EPYC 7601（Zen 1 Naples）与 2P Zen 6 Venice 系统放在同一测试体系中，用两代平台衡量不到十年的累计变化。

**「影响」** 对仍在使用 Zen 1 服务器的组织，升级评估应把核心数扩展与每核心改进分开：并行吞吐型任务更可能接近总提升，而单线程敏感或按核心计费的软件收益会低得多，需按实际负载复测后再做容量规划。

**「社区讨论」** 评论区一条详细拆解指出：双路配置的核心数从 64 增至 192，仅此一项约带来 3 倍提升，剩余约 4 倍来自每核心改进，因此 12.1 倍不应直接当作单线程收益。另有用户惊叹 Linux 内核约 18 秒、LLVM 近 1 分钟的编译成绩，并摘录评测称两代旗舰的每瓦性能约为 5 倍；也有人提醒软件栈和价格上涨会影响实际性价比。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.phoronix.com/review/amd-epyc-9006-7601/2">AMD EPYC Zen 6 vs. Zen 1 Performance: 12.1x Geo ... - Phoronix</a></li>
<li><a href="https://www.phoronix.com/review/amd-epyc-9006-venice">AMD EPYC 9006 Venice Announced &amp; Looks Poised To ... - Phoronix</a></li>
<li><a href="https://hothardware.com/reviews/amd-epyc-9006-venice-zen-6-architecture-reveal">AMD EPYC 9006 Venice Unveiled: Inside The Zen 6 Architecture</a></li>

</ul>
</details>

**标签**: `#amd-epyc`, `#cpu-benchmarks`, `#server-hardware`, `#zen-6`, `#performance-scaling`

---

<a id="item-tech-news-9"></a>
### [Z.ai 发布 GLM-5.4：首个循环 Transformer 模型](https://simonwillison.net/2026/Nov/23/glm-54/) ⭐️ 7.0/10

中国 AI 实验室 Z.ai 发布 GLM-5.4，这是其首个采用循环 Transformer（Loop Transformer）架构的模型。按 Z.ai 的说法，标准 Transformer 的每层在前向传播中只运行一次，而循环 Transformer 让一组共享权重的层迭代运行多次，以细化上一轮的隐藏状态，从而在不增加参数量的前提下加深网络。该模型目前尚未开放权重；Simon Willison 测试时需订阅 Z.ai 的 Coding Plan 才能访问，因为 5.4 暂时无法通过普通 API 调用，但两者共用位于 https://api.z.ai/api/v1 的 OpenAI 兼容 Responses API，Coding Plan 的密钥可直接使用。Willison 用“骑自行车的鹈鹕”提示做了低、高、最高三档测试，认为 5.4 与 5.3 质量相近，且风格明显不同于 5.1 和 5.2；他没有给出基准测试数据。

rss · Simon Willison · 11月23日 23:40

**「背景」** 循环 Transformer 的核心是权重共享：同一组层被反复执行，用迭代次数换取等效深度，而不是靠堆叠更多参数。Willison 指出，这是他在一周内看到的第二次此类发布——Thinking Machines Lab 于 11 月 20 日推出的 Inkling 2 Mini 同样采用循环结构，对每个 token 将中间层运行三次，并宣称这能用更少 token 完成智能体编程等推理任务。GLM-5.4 延续了此前 GLM 5.1、5.2、5.3 的版本序列，Willison 也补做了此前遗漏的 5.3 鹈鹕测试以作对照。

**「影响」** 对想立即使用该模型的开发者来说，实际门槛是订阅 Coding Plan，而非普通 API；不过由于接口兼容 OpenAI Responses 格式，现有客户端改指向 api.z.ai/api/v1 即可接入。由于尚未发布开放权重，自托管与本地部署目前不可行；工具链也存在缺口——Willison 提到 Tommy Hughes 的 llm-zai 插件尚不支持 5.4，他因此临时另写了 llm-glm，并计划在后者跟上后弃用自己的版本。

**标签**: `#GLM-5.4`, `#looped transformers`, `#model architecture`, `#AI models`, `#coding`

---

<a id="item-tech-news-10"></a>
### [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 7.0/10

百度于 11 月 24 日通过官方 X 账号宣布开源文心 5.5 Flash Preview，模型权重以 Apache 2.0 协议在 Hugging Face 和 ModelScope 开放，并支持使用 vLLM 或 SGLang 部署及微调。该模型采用 MoE 架构，总参数 280B，每个 token 激活 14B，上下文长度为 1M token，是基于 ERNIE 5.5 Flash Base 训练的首个后训练模型。目前流传的基准图表显示，其在 Terminal-Bench 4.0 得 46.5 分、DeepSWE v1.1 得 71.2 分，但百度未说明这些成绩是否经过第三方独立验证。

telegram · zaihuapd · 11月24日 07:32

**「背景」** 混合专家（MoE）架构将模型的总参数分散到多个专家中，每个 token 只路由到其中一部分，因此 280B 总参数与 14B 激活参数描述的是不同层面。文心 5.5 Flash Preview 是百度基于 ERNIE 5.5 Flash Base 训练的首个后训练模型，本次以 Preview 形式开放的是该后训练阶段的权重。

**「部署影响」** 希望自托管或微调的团队可按 Apache 2.0 使用权重，但需按 280B 总参数规模准备推理资源；由于模型仍属 Preview 且基准成绩尚未经独立验证，生产选型前应先在实际任务上复现表现。

**标签**: `#Baidu ERNIE`, `#open-source LLM`, `#Mixture-of-Experts`, `#Apache 2.0`, `#long context`

---

<a id="item-tech-news-11"></a>
### [诺华 CEO：AI 十年内难治愈癌症，研发周期或缩短四年](https://www.ft.com/content/1e5a9d70-221d-461d-ae03-dc235b1db340) ⭐️ 7.0/10

诺华 CEO 万思瀚（Vas Narasimhan）表示，AI 不会在未来 5 到 10 年内治愈癌症；即便只是把药物研发周期从平均 12 年压缩到 8 年，也大约需要十年。他同时担任 Anthropic 董事，并称科技界用“工程思维”看待医学，而人类对人体内机制只了解约 5%。按诺华的经验，AI 提速最明显的是通常耗时 4 年的临床前早期发现阶段，最多可缩短 2 年；他预计进入人体试验的成功率可从 8% 提高到 12%，但动物实验和临床试验无法跳过。上述均为高管估计，不是已实现的临床结果；这与 Anthropic CEO 所称癌症等疾病将在十年内成为“历史遗迹”相左，礼来 CEO 也公开表示怀疑。

telegram · zaihuapd · 11月24日 08:54

**「背景」** 这番表态针对的是 AI 业界近来的乐观预测：Anthropic CEO 曾称癌症等疾病可能在十年内成为“历史遗迹”，而礼来 CEO 也公开对此表示怀疑。万思瀚同时担任 Anthropic 董事，因此他的质疑来自同一技术阵营内部，而非外部旁观者。

**「影响」** 对药物研发组织而言，短期内更应把 AI 的收益预期放在临床前发现阶段提速和人体试验成功率的有限提升上，同时仍须为动物实验与临床试验保留完整时间与预算，而不能把 AI 当作跳过这些环节的捷径。

**标签**: `#AI in drug discovery`, `#biotech`, `#pharmaceutical R&amp;D`, `#AI hype`, `#Novartis`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [ERNIE 5.5 Flash 的 vLLM Day-0 插件支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 6.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 百度 ERNIE 团队与 vLLM 合作，为 280B 总参数、每 token 激活 14B 的稀疏 MoE 模型 ERNIE 5.5 Flash Preview 提供发布日支持；该模型面向 100 万 token 上下文和长程 Agent 任务，设计重点是把推理成本压下来。

**「方案」** 作者的关键做法是发布独立的 vLLM-ERNIE 插件，而不是维护 vLLM 分支：它与 PyPI 上的 vllm==0.32.0 装在同一环境，通过 vllm.general\_plugins 入口自动注册模型和解析器，仅对 ERNIE 架构生效。围绕 HCA/MLA-DSA 注意力、Multi-Router Latent MoE 和 MultiMax 输出头等结构，团队在加载时预折叠权重并融合 VHA 混头、路由 GEMM、门控等算子，作者报告单核提速 1.55×–6.53×。FlashIndexer 用只依赖当前 token 的小路由器挑选稀疏索引头，再加阈值预过滤，在 1M 上下文下测得约 1.4 倍（40%）加速。默认检查点将路由专家量化为 MXFP4（W4A8），其余权重和 KV 缓存用 FP8，并以 QAT 对齐训练与推理数值；随权重发布的 3 层 DSpark 草稿模型每步最多提议 7 个 token，作者称在真实编码和 Agent 负载上平均接受长度超过 4.0。插件还让块 FP8 权重、注意力张量并行、MXFP4 专家等更新不必等待 vLLM 发版，同时复用前缀缓存、分块预填充、CUDA graph、PD 分离和 KV 卸载等现有能力。

**「启示」** 文章的核心论点是，插件化集成让模型团队无需 fork 推理框架即可实现 Day-0 支持，并把架构、量化和投机解码优化封装在模型侧；不过这些加速与接受长度数据主要来自厂商自测，仍需独立基准验证。

**标签**: `#vLLM plugin`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`, `#FP4 quantization`

---

<a id="item-tech-blog-2"></a>
### [vLLM-GR：生成式推荐推理框架](https://vllm.ai/blog/2026-11-24-vllm-gr-announcement) ⭐️ 6.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 生成式推荐模型（如 OneRec）根据用户历史生成语义 ID（SID），一次请求需在严格时延内用束搜索探索大量候选；通用 LLM 推理栈并不直接支持这种共享历史、跨步复用的搜索。

**「方案」** vLLM-GR 在 vLLM 的调度、模型执行和分页 KV 缓存上加入贯穿整次搜索的 beam session，由 EngineCore 管理。调度器派发 prefill/decode 阶段，模型 runner 为下一 token 打分，beam selection 记录存活路径的分数与父索引，下一次 decode 据此读取对应 KV。所有候选共享用户历史的 prompt KV，避免逐路径复制；目录约束把搜索限制在真实商品 SID，逐阶段束宽和每父节点候选上限允许先探索更多部分 ID。主机还在加速器执行当前阶段时准备下一阶段（PDD 流水线），减少解码步间等待。基准以 P99 时延测试 1,024 token 输入、束宽 256/128、批量 1/4/8：作者称束宽 256、批量 4 和 8 时 vLLM-GR 在六种加速器上均最低，如 H20 批量 8 为 369.4 ms，SGLang 1,280.1 ms，NVIDIA SID-GR 428.1 ms；但 RTX PRO 6000 批量 1 上 SID-GR 以 28.25 ms 略胜 29.21 ms，束宽 128 时领先者随平台变化。文章也提示各汇总的计时口径、样本数和后端设置不同，部分版本与预热次数未记录。

**「启示」** 作者的核心论点是：把束搜索作为一等会话嵌入推理引擎，并用共享 prompt KV、父索引复用和主机/加速器重叠，可在宽候选搜索下压低尾时延；但这些跨平台优势仍需统一基准来确认。

**标签**: `#generative-recommendation`, `#llm-inference-serving`, `#beam-search`, `#kv-cache`, `#vllm`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [黄循财：新加坡不会成为规避美国芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，不允许新加坡被用作企业规避美国芯片出口管制的通道，当局正在调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部以存在向未获授权用户转移先进计算产品的「重大风险」为由，将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单，其中包括其在马来西亚和泰国的关联实体。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 美国商务部在前一天将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单，即限制其与美国企业交易，理由是这些企业存在向未获授权用户转移先进计算产品的“重大风险”。新加坡警方则正在调查 Megaspeed 采购英伟达芯片的交易。

**「影响」** 对在新加坡运营的芯片采购商和分销商而言，Megaspeed 及其前高管被调查、公司又被列入美国贸易黑名单，意味着相关交易将同时面对新加坡本地合规审查和美国供应限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nypost.com/2026/11/23/us-news/commerce-department-blacklists-megaspeed-after-nvidia-reinstates-jensen-huang-as-ceo/">Commerce Department blacklists Megaspeed after Nvidia reinstates...</a></li>
<li><a href="https://www.ft.com/content/52b5f9a8-346f-4dae-8a16-14d5d9eb1244?syn-25a6b1a6=1">Nvidia spy scandal exposes Singapore ’s role in China’s AI chip trade</a></li>
<li><a href="https://www.ft.com/content/6ca21b39-ff62-42e0-9695-9220b438f7eb?syn-25a6b1a6=1">Singapore is no backdoor for US chips , says PM</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says">Singapore Won’t Be Conduit to Skirt US Chip Curbs, Wong Says</a></li>

</ul>
</details>

**标签**: `#US export controls`, `#semiconductors`, `#Singapore`, `#Nvidia`, `#trade blacklist`

---

<a id="item-finance-news-2"></a>
### [小米 2026 年三季度经调整净利同比下降 56.8%，汽车交付 100,975 辆](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

小米集团发布的 2026 年第三季度财报显示，经调整净利润为 48.84 亿元，同比下降 56.8%，但略高于市场预期的 47.46 亿元。同期汽车交付量为 100,975 辆，公司称手机业务在主动收缩中低端机型后，均价创历史新高。

telegram · zaihuapd · 11月24日 10:09

**「背景」** 小米集团是一家同时经营智能手机与电动汽车业务的上市公司；本季利润承压，发生在存储芯片等核心元器件涨价、研发投入加大的背景下。财报中的“经调整净利润”是剔除部分非经营性项目后的盈利口径，为市场常用的比较基准。

**标签**: `#小米集团`, `#季度财报`, `#盈利下滑`, `#新能源汽车`, `#智能手机`

---