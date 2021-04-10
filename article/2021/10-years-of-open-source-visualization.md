> * 原文地址：[10 Years of Open-Source Visualization](https://observablehq.com/@mbostock/10-years-of-open-source-visualization)
> * 原文作者：[Mike Bostock](https://observablehq.com/@mbostock)
> * 译文出自：[掘金翻译计划](https://github.com/xitu/gold-miner)
> * 本文永久链接：[https://github.com/xitu/gold-miner/blob/master/article/2021/10-years-of-open-source-visualization.md](https://github.com/xitu/gold-miner/blob/master/article/2021/10-years-of-open-source-visualization.md)
> * 译者：[momodiy](https://github.com/momodiy)
> * 校对者：[PassionPenguin](https://github.com/PassionPenguin)、[Chorer](https://github.com/Chorer)、[W-Qing](https://github.com/W-Qing)

# 十年可视化开源历程


> 看看我从 D3.js 中学到了什么……


为了纪念 [D3 1.0 版本](https://github.com/d3/d3/releases/tag/v1.0.0) 发布 10 周年，我觉得我应该反思一下其中的经验教训。我没打算做的特别全面或者很严肃，这只是对未来十年的一点展望，不过我还是希望其中有一两点见解能够让你感兴趣。


## 1. 造轮子最重要的是教会别人使用

当你在造轮子的时候你很容易忘记自己简化了多少，也就是说你对用户或读者已经了解的知识和背景进行了多大程度上的假设。你的工具可能对你来说很熟悉，但是对于其他人来说则完全是陌生的。如果你的目标是让别人使用这破玩意，那就意味着你不仅仅是在为自己制造这个轮子（当然这也是一个完全正当的理由），你必须帮助别人去使用它！你可能做什么或是打算做什么都没关系，重要的是用户能否在实践中成功使用它。

要想使你的影响力最大化，你的核心策略就应该是教学。这包含文档、教程、示例、视频、推文等各个方面。一对一教学或者开研讨会确实是一种很好的方式，它可以让你的知识浮出水面且与你的听众找到共同点，而你可以从他们的工作中获得启发，并学习如何更有效的进行教学（参见第 2 小节）。但是随着你的学员增加，制作一系列教程才是你无需花费个人时间就可以扩大教学规模的唯一方式。如果需要，你的教程就是你的被动收入。一天的工作室培训可以帮助 100 人，而一个教程可以帮助数万人甚至更多。我也经常受到 [Rich Harris](https://twitter.com/Rich_Harris)和 [Dan Abramov](https://overreacted.io)出色教学风格的启发（偶尔羡慕不已）。

在所有类型的文档中，示例似乎是最有效的。我一直崇尚[示例的优点](https://bost.ocks.org/mike/example/)，`Observable` 和它的前身 `bl.ocks.org` 都通过让人创建和使用示例来加快学习。示例能够通过展示可能的使用方式来激发灵感，能够展示特定的技巧，是帮助人们入门的基石。考虑到人们擅长模式匹配和从观察进行推断，示例自然而然地成为了最好的学习材料。

示例的功能太强大了，它可以弥补难用的 API，也促进了人们对复制粘贴的依赖。D3 的成功不是因为它是一个很棒的工具，而是因为它带有很多示例，难道不是吗？🤷虽然我是 D3 的作者，但我也记不住如何使用 `d3.stack` ，我也得像其他人一样复制粘贴 stack 部分的[代码示例](https://observablehq.com/@d3/tidy-stacked-area-chart)。示例也许可以让人们无视工具的缺陷，帮助人们成功，但更重要的是对于熟练度的追求，也就是让人们内化工具的用法，学会从头开始构建。对于可视化来说，从示例开始而不是从数据开始可能也是一种错误（请看第 5 小节）。而且示例也有局限性：教授特定技巧的示例可能无法广泛代表在实际项目中的用法。

## 2. 提供支持是一种强劲的研究手段

了解你和工具使用者之间存在理解鸿沟的的唯一方法是关注他们的痛点并与他们沟通。通过这种方式，一些显而易见的缺陷会很快浮现出来，快到让你难以置信。在 Stack Overflow（或 GitHub、Twitter、Slack 等地方）上解答问题并不是无私的利他行为，这是一个可以了解到用户痛点且倾听他们观点的学习机会。每一个问题都是一个为他人提供帮助的机会，同时这些问答也会形成教程或是示例，避免其他人遇到相同的问题。而这个潜在的优势也能够促进成功的工具更加成功：因为维护者可以通过无数用户的想法和批评改进项目或优化文档。要知道，任何的想法都不是凭空产生的。

但是也有一个限制。仅凭一人之力，你不能帮助所有人。而且，你的工具只是他们人生的一小部分，因此你无法满足每个人。所以不要将他们的目标作为你的目标，你应该专注于学习和开阔视野。如果你无法再获取什么建设性的帮助，那就停下来吧，而且不要觉得沮丧。我对 GitHub 与其他平台默认启用消息提醒的方式不太认可，因为它表明了一些不合理的预期，即无薪的维护者必须立即礼貌且带有实质内容地去回复所有的帮助请求。是的，我可以关闭 issue，但作为社区的成员，如果我们真的足够重视解决维护者倦怠的问题，我们就需要重新考虑自己的行为。

## 3. 请小心：交互、动画或其他技术亮点都是有代价的

这些东西确实得呈现，但是请仔细听我说。对于那些不常遇到动画与交互效果的用户而言，它们具有非常震撼的效果。知道了这一点之后，你可能会将这些功能添加到可视化效果中，但却没有意识到这么做的弊端：它们增加了项目的复杂性，并将实际有价值的信息隐藏在交互控件之后。更糟糕的是，由于实现难度较高，这些功能可能会分散你对于更加重要但无聊的真实任务的注意力。

这可不是道德批判，我也没有指责你这么做不好，事实上，我只是为自己感到内疚。无论如何，这么做确实是存在弊端的。我们首先应该关注的是静态形式（展示效果），对于某些读者来说，这可能是他们唯一能看到的东西了。请勿让技术问题（比如 web 开发）过多地吸引你的注意力。当然也不要担心简单的可视化效果会造成不好的影响：重要的是我们能了解到什么，而不是它的外在形式多么华丽。
那么我们应该在哪里使用交互效果呢？主要是为了探索可视化（请看第 4 小节）。格雷戈尔的[《为交互式图形辩护》](https://www.vis4.net/blog/2017/03/in-defense-of-interactive-graphics/)就是一个很好的答案。

## 4. 可视化是一个从探索到解释的过程

并非所有的可视化效果都是为了达到同样的目的，你自己构思制作的可视化图表也能以新的理解展示数据。相对而言，解释性的图表会向观众传达一些已知的见解。所以设计时请找好你的定位。

可视化探索的主要目的是提高速度：你能以多快的速度构建一个视图来回答你的问题？当你的目标读者已经有了一些背景知识，你也可以去省略一些东西，但是你必须提供图解来解释上下文。好的可视化图表应该知道它想表达什么，并且能够正确地表达出来。图解也可以包含一些说明性的元素，比如让读者在数据中看到他们想了解的信息，但是理想状态下这些元素都不应该影响主要信息。不要让读者在明确重点上花太多心思，这应该是作者自己的职责。

## 5. 通常来说，可视化 80% 的工作是处理数据

可视化图表是进行分析的最终成品，也是数据的可视化表现，可供专业人士和非专业人士查看、共享与理解，因此可能会获得过多的赞誉。要想完成可视化效果，首先必须通过查找数据、清洗数据、转换、链接、建模等步骤，数据处理有时会被贬低为[清洁工](https://www.nytimes.com/2014/08/18/technology/for-big-data-scientists-hurdle-to-insights-is-janitor-work.html)，但无论如何，它代表了理解数据本质的关键步骤。（请参阅 Leigh Dodds 关于该主题的[文章](https://blog.ldodds.com/2020/01/31/do-data-scientists-spend-80-of-their-time-cleaning-data-turns-out-no/)）如果数据结构正确，那么应用视觉编码的过程可能会比较简单（假设你看过第 3 小节）。因此，我最常使用的 D3 模块是 [d3-array](https://github.com/d3/d3-array) 和 [d3-dsv](https://github.com/d3/d3-dsv)。我很高兴看到例如 [tidy.js](https://pbeshai.github.io/tidy/) 和 [Arquero](https://uwdata.github.io/arquero/) 这种用于处理数据的新型 Javascript 工具。哈德利·威克姆（Hadley Wickham）的[整理数据](https://vita.had.co.nz/papers/tidy-data.pdf) 相关示例是很有价值的。

## 6. 在看到数据结构之前，请不要局限于特定的视觉展示形式

一个确定的视觉形式（比如柱状图或者是树形图）并没有完全意义上的好坏之分，但它是否适合你的数据以及你想回答的特定问题这一点则值得商榷。只有一种方法能够知道你使用的图表是否准确，那就是看它能够传达信息：你必须将数据与之结合之后再进行观察，不要着手使用特定的展示形式，而是想想你的数据是要解决什么样的问题。

如果你的数据很难确定对应什么类型的示例（请看第 1 小节），可以先试试特定类型的图表再确定其有效性。绘制可视化图表所需的精力越少，你可以尝试的变化就越多，最终效果也就越好，这就是 `Observable` 帮你快速获取数据的原因，比如单击一下鼠标就能替换文件或者让你无需 fork 就能编辑代码。但是如果你的数据结构不兼容，可能仍然需要大量的工作（参阅第 5 条）。而且 D3 主要是为定制的解释性图形而设计，例如 [Vega-Lite](https://vega.github.io/vega-lite/) 这类用于探索图形的东西需要更多的工作。如果你想降低特定[符号认知范围](https://en.wikipedia.org/wiki/Cognitive_dimensions_of_notations)的黏度，可以快速尝试多种形式并查看有效方法。我们正在降低从 Observable 中绘制可视化效果的难度，希望能尽快分享出来。敬请关注。

## 7. 10% 的代码导致了 90% 的bug

这些数字是我编的，但我感觉这结论没错：某些代码就是比其它代码更容易出错。不是因为这些代码的质量较低，而是因为它们试图做一些本就很困难或是不确定的事情。在 D3 中最容易造成 bug 的是交互式行为，比如 d3-zoom、d3-drag 和 d3-brush 。它很难通过控制变量的方法进行推理，更不用说测试所有可能的异步事件。同时，其交互行为也是不确定的，你是在点击、拖动、平移选择，还是在双击？更困难的是浏览器会发生变化，就像[被动事件监听](https://developers.google.com/web/updates/2017/01/scrolling-intervention)一样单纯地破坏页面。

以上表明你可以通过谨慎选择要解决的问题和不想解决的问题来减少一些麻烦。比如，如果你使用 `Observable` 的 [输入](https://observablehq.com/@observablehq/inputs) 和 [数据流](https://observablehq.com/@observablehq/how-observable-runs) 代替低级的事件监听器来构建页面，你的顾虑就会减少很多。

## 8. 互联网上总会有人让你难过

无论你的工作多么出色，如果你把自己置于互联网这个平台，就会有人说一些伤人的话并让你感到难过。这通常不是故意的，但这并不重要。我为 D3 感到自豪，但我也收集过一些别人分享出来的负面评价推文。这就是我的处理方式（收集负面推文），请不要批判我。（对了，我可不会分享这个列表）。

我对于那些使用工具受挫的人并无恶意，我完全理解一个工具可能给人带来的无助感 —— 明明你只需要设计一个小表格，但却不得不学习数以百万计的其它内容。一个工具的设计可以如此地随意和滞后，这就是互联网的问题，过去你可能会向同事或者朋友抱怨 D3 有多糟糕，也许他们会帮你解决，而且知道你正在发泄。因为互联网我也听到了这些抱怨，我并不认识你，然而这些抱怨让我很沮丧。如果说我当初开发工具是为了看到成功使用工具的人分享快乐，如今的我却只感受到了痛苦和挫败，那我还为什么要继续开发？为何在我只想观看 YouTube 时还要遭受贬低和否定呢？

因此，如果你发现你在互联网上抱怨，请考虑一下你的言语会造成的实际影响。这些话是否只会造成开发者的懈怠和受挫？甚至更糟，导致开源项目停更呢？或者往更好的方向考虑一下，你可以做一些贡献来让这个工具变得更好，比如通过拉取请求或文档支持等。毕竟，这就是开源之美。

## 9. 不要独自一人

为了避免将幸福感寄托于互联网（请参阅第 8 小节），你必须发展一个你尊重的小而稳定的组织，换句话说，找到一个可以提供验证、反馈、支持和指导的团队或组织。每个人都清楚这件事，除了我之外 —— **是的，麦克，有朋友真的会很棒**。尽管如此，我觉得还是有必要强调一下，毕竟如今人与人的交流大多都是在遥远的互联网上。当我使用 `Observable` 创建出一个远程共享的协作空间时，我觉得很高兴，这不是在炫耀（就像在 Twitter 上），而是因为可以与朋友们实时合作并发表见解、解决问题而真心感到高兴。

## 10. 享受美好时光

起初我写的是“放松”，但是感觉有点假。我可能是最不会放松的人，我**希望**能够活得轻松。这是我的私事，我会尝试反思自己工作生活中最喜欢的部分，并且花更多的时间做这些事情。这听起来很简单也很老套，但实际做起来却不容易。如果你知道自己喜欢做什么事情，那么（万一）当你失败（只是假设，未必真的会这样）时，你就不会有太多遗憾。矛盾的是，一个让你偏离实际目的的目标可能会帮助你成功，因为你更容易坚持下去。做自己喜欢的事情（工作）是更容易坚持的，比如我喜欢构建工具，虽然无法预测它是否能成功，但我热衷于解决难题并进行抽象，而且我也热衷于看到人们使用我的作品。另一方面，虽然我知道演讲的好处，也知道演讲之后会获得多棒的自我感觉，但我发现公开演讲会引起焦虑。因此，如果你对我较少发表公开演讲而略感失望，但愿这只是因为我正在埋头开发一些新的东西。😅


> 如果发现译文存在错误或其他需要改进的地方，欢迎到 [掘金翻译计划](https://github.com/xitu/gold-miner) 对译文进行修改并 PR，也可获得相应奖励积分。文章开头的 **本文永久链接** 即为本文在 GitHub 上的 MarkDown 链接。

---

> [掘金翻译计划](https://github.com/xitu/gold-miner) 是一个翻译优质互联网技术文章的社区，文章来源为 [掘金](https://juejin.im) 上的英文分享文章。内容覆盖 [Android](https://github.com/xitu/gold-miner#android)、[iOS](https://github.com/xitu/gold-miner#ios)、[前端](https://github.com/xitu/gold-miner#前端)、[后端](https://github.com/xitu/gold-miner#后端)、[区块链](https://github.com/xitu/gold-miner#区块链)、[产品](https://github.com/xitu/gold-miner#产品)、[设计](https://github.com/xitu/gold-miner#设计)、[人工智能](https://github.com/xitu/gold-miner#人工智能)等领域，想要查看更多优质译文请持续关注 [掘金翻译计划](https://github.com/xitu/gold-miner)、[官方微博](http://weibo.com/juejinfanyi)、[知乎专栏](https://zhuanlan.zhihu.com/juejinfanyi)。