category: readings
description: ''
date: 2014-04-19 8:00:00
title: Top 10 Mistakes in Web Design
tags: [关于HCI,HCIBib,译系列,翻译文章,HCI,Usability]
---

这是一篇很古老的文章了--发表在2011年1月. 之所以还把它挖出来, 一方面是因为正好看到了, 更重要的方面是因为里面列举的10条即便是现在也应该极力避免的~

<strong>摘要:</strong> 最让用户讨厌的10个恶习.  网页设计和html中可诟病的东西不少, 虽然其中有一些可能已经比过去少见多了.

自从1996年第一次尝试一来, 我编写了不少列举网页设计中的top 10错误清单. 你可以在本文的结尾处看到这些文章的链接. 本文重点在列举其中的突出条目.

<ol>
    <li>
        <strong>Bad Search(糟糕的搜索)</strong>
        <p>过度依赖文本的搜索方式是很影响用户体验的, 因为它们无法处理书写错误, 复数形式, 连字符号以及query中其他的一些特殊部分. 这样的搜索引擎对于年长者尤其难用, 但是它们伤害的是所有人.</p>
        <p>还有一个相关的问题就是搜索引擎仅仅根据结果中包含的query成分的多少来排列结果, 而不是根据每个文档的重要程度. 可能你把最佳猜测的结果放在最前面要更好一些, 尤其是对一些重要的查询, 比如产品名称等.</p>
        <p>搜索是用户在导航失败的时候的唯一依赖. 即便有些时候高级搜索能提供一些帮助, 但是简简单单的搜索本身更为常用, 同时搜索应该能够展示一个简简单单的结果, 因为那才是用户所需要的.</p>
        <p style="color:#00aa0b;"><i>博主说: </i> 目前来说, google, baidu等这种大型搜索基本已经不会出现这类问题了, 所以这个问题多数出现在个人blog搜索或者小站的自建搜索上, 通常只是个简单的sql语句, 也真心不能奢求做的太过完美.</p>
    </li>
    <li>
        <strong>PDF Files for Online Reading(pdf文件的在线阅读)</strong>
        <p>用户讨厌在浏览过程中突然遇到一个pdf, 这会打乱它们的工作流. 即便是简单如打印和保存都很难使用, 因为标准的浏览器命令都不能发挥作用. 网页布局往往为纸张优化, 而无法适应用户的浏览器窗口. 所以经藏无奈的看着眼前难用的窗口和小小的字体.</p>
        <p>最糟糕的是, pdf文档本身不易于浏览.</p>
        <p>PDF对于打印或者使用手册以及其他的一些需要打印出来的大型文档而言是非常有帮助的. 所以保持这一目标, 把相关的信息都转为更适合浏览的文本呈现在网页之中.</p>
        <p style="color:#00aa0b;"><i>博主说: </i> 对当下来说, 首先是显示器有了很大的进度, 目前的显示器基本都能轻松支持pdf的阅读了, 浏览器本身的渲染也考虑的文本的问题, 不过本身pdf的浏览性确实差了一些, 当然那些有目录交互的动态pdf除外;</p>
    </li>
    <li>
        <strong>Not Changing the color of visited links(不改变已访问链接的颜色)</strong>
        <p>一个对已经进行过的行为有区分的导航能够对当前的浏览起到巨大的帮助, 因为它代表了你的每一步操作. 了解过去的位置和当前所在可以让你更容易的决定下一步去哪里. 链接是导航处理的一个核心元素. 用户可以排除那些他们已经访问过的无用链接. 相反的, 他们也可以再次访问那些有价值的链接.</p>
        <p>最为重要的是, 了解自己已经访问过的页面能够避免用户重复地访问同一个页面.</p>
        <p>这些益处必须有一个前提: 就是用户可以分辨出已访问的和未访问的链接--利用浏览器中呈现出不同的颜色. 当已访问的链接没有改变颜色, 用户测试中发现用户表现出更加容易迷失在导航之中, 持续的访问同一页面.</p>
        <p style="color:#00aa0b;"><i>博主说: </i>这个是个持续性的问题, 个人也是比较支持这种标记链接状态的属性的;</p>
    </li>
    <li>
        <strong>Non-Scannable Text(不适合浏览的文本)</strong>
        <p>满屏的文本本身绝对是交互体验的死敌. 不亲和, 无聊以及阅读起来非常痛苦...</p>
        <p>为在线阅读而写作, 而不是仅仅为了展示内容. 引导用户阅读文本, 同时支持浏览, 利用一些结构化的技巧:
            <ul>
                <li>副标题</li>
                <li>列表清单</li>
                <li><strong>高亮的关键字</strong></li>
                <li>简短的段落;</li>
                <li>倒金字塔结构;</li>
                <li>简单的写作风格, 以及尽可能避免语法错误或者信息冗余.</li>
            </ul>
        </p>
        <p style="color:#00aa0b;"><i>博主说: </i>这个是一个老生常谈的问题了, 很多类似的文章也介绍过很多方法来更好的在网上呈现内容, 究其根本还是用户读书和上网阅读的行为差异很大--一个是读, 一个是看...</p>
    </li>
    <li>
        <strong>Fixed Font Size(合适的字体大小)</strong>
        <p>css文件非常不幸的给与了网站控制其样式的能力, 它们可以覆盖掉浏览器本身的字体样式, 同时还禁止了浏览器本身的字体大小设置的按钮, 取而代之以新的字体大小. 通常是time字体, 但往往会显得过小了写, 显著得降低了很多40以上的人们的可读性.</p>
        <p>请尊重用户的偏好, 让他们自行设置字体大小. 还有, 使用相对值而不是像素绝对值来定义字体大小.</p>
        <p style="color:#00aa0b;"><i>博主说: </i>对于修改字体大小的按钮, 这个功能还是提供的 , 但是很多时候是隐性的, 目前多数浏览器应该是不会直接提供的, 个人觉得这属于一个排版型的问题, 毕竟大字会导致很多版式上的影响, 同时也是一个针对特殊人群的处理问题...</p>
    </li>
    <li>
        <strong>Page Titles With Low Search Engine Visibility(网页标题不具备很好的易搜索性)</strong>
        <p>搜索是一个用户发现网站的重要途径. 搜索本身也是用户在一个个网站之中跳转的方式. 你的页面标题是一个吸引新用户的主要方式. 通过提升在搜索结果的排位以及尽可能 的让已有的用户快速确定他们的需求.</p>
        <p>页面标题是存在与html的title标签之中. 通常会显示在搜索结果页的条目标题上, 点击后跳转到对应的网站. 搜索引擎通常会按照某种规则来阶段显示其中的部分, 比如66个字符, 所以这是一个非常微型的文本.</p>
        <p>页面标题经常还被用作浏览器书签添加后条目的标题. 对于你的首页而言, 以公司名为开始,加上简短的站点介绍. 千万不要用The, welcome to等开头, 除非你想要排序排在T或者W后...</p>
        <p>对于很多非主页的页面, 可以以本页最突出的一些信息作为关键字描述一些用户可以在页面上发现的信息. 因为页面标题是用来作为浏览器窗口的标题, 同时还用来作为浏览器下任务栏的标题(windows下), 意味着高级用户将会在多个窗口下不断的切换, 仅仅依赖于前两三个词语, 所以如果每个页面都使用同样的页面标题, 你就会显著的影响可用性.</p>
        <p style="color:#00aa0b;"><i>博主说: </i>这是比较实际的一个问题, 即便现在也是经常的遇到的...</p>
    </li>
    <li>
        <strong>Anything That Looks Like an Advertisement(任何看起来像广告的东西)</strong>
        <p>选择性注意是非常有帮助的, 而且网页用户已经学会忽略那些页面上的广告了--尤其是对于那些目标驱动型的浏览用户而言.</p>
        <p>不幸的是, 用户同时也会忽略那些正常的只是看起来比较像广告的元素. 毕竟, 当你忽略某事时, 你不需要再费力去去研究它看它究竟是啥.</p>
        <p>所以, 最简单的方法就是避免设计像广告的元素. 当然, 具体实施起来有很多的规则, 参照着现在越来越多的广告样式. 就目前来说, 有以下规则:
            <ul>
                <li>条幅忽略: 意味着用户将不会注意那些看起来像个条幅, 通栏的位置.</li>
                <li>避免动态效果: 用户会自动忽略那些闪烁的或者带着特效字体的, 比较故意吸引注意力的元素;</li>
                <li>弹出: 用户经常会在弹出页面加载完全之前就关掉了.</li>
            </ul>
        </p>
        <p style="color:#00aa0b;"><i>博主说: </i>这个确实很现实, 尤其是随着广告的样式越来越多...如何更好的区分广告和内容是个非常值得考虑的问题, 目前来说, 基本都是通过分区来划分的, 似乎大家也都知道广告的点击很低, 但总还是有人会点的...</p>
    </li>
    <li>
        <strong>Violating Design Conventions(违背设计规则)</strong>
        <p>一致性是一个最为有帮助的可用性原则: 当所有事物保持一致的时候, 用户就不需要担忧什么将会发生. 反而, 他们知道什么将会发生, 基于过往的经验. 每次你在牛顿头上放个苹果, 它就会掉在他的头上. 这就很好.</p>
        <p>越符合用户的预期, 用户就会越能感觉到掌控权, 他们就会越高兴. 然而如果总是违背用户的预期, 他们就会失去安全感. 那么你下次放开苹果, 它很有可能变成一个番茄并且飞到天上去的.</p>
        <p>Jakob's 关于用户体验的规则注明: 用户更多的时间是花费在其他网站上的.</p>
        <p>这意味着, 他们的预期是基于那些网站的共性作出的. 如果你背离了, 你的网站就会很难使用而流失用户.</p>
        <p style="color:#00aa0b;"><i>博主说: </i>Jakob's law 这是本文的最大收获了!!!</p>
    </li>
    <li>
        <strong>Opening New Browser Windows(新开窗口)</strong>
        <p>新开窗口就像一个吸尘器销售员销售前先把一堆灰尘倒在用户的前门地毯上. 不要用更多的窗口来污染我的屏幕, 非常感谢(尤其是在现在的操作系统管理窗口是如此的糟糕).</p>
        <p>设计新开窗口的重要原因是在希望能够让用户留在当前站点. 但是不顾用户自己的意愿直接接管用户的电脑是非常自欺欺人的行为, 尤其这种操作导致back按钮失效, 而这才是用户通常使用的. 用户经常没有注意到一个新窗口的打开, 尤其是他们使用的是小型的显示器且窗口本身最大化的情况下. 所以一个用户试图回到之前的页面而不能的时候会非常困惑的.</p>
        <p>链接的行为和预期不一致会破坏用户对于自己的系统的理解. 一个链接就应该是那一个见到那的超链文本, 代表着用新的内容取代当前的页面, 如果需要在新窗口打开链接, 用户可以自行选择使用浏览器提供的"新窗口打开"命令.</p>
        <p style="color:#00aa0b;"><i>博主说: </i>这个个人觉得需要针对具体情况考虑了, 网络的属性就决定了它发散的特征, 而用户又普遍有一种保留欲望: 打开总是容易的, 关闭总是困难的.</p>
    </li>
    <li>
        <strong>Not Answering Users' Questions(答非所问)</strong>
        <p>用户经常是目标驱动型的, 他们带着一定的目的来访问页面的, 甚至可能是要购买你的产品. 一个网站最大的失败就是没有提供用户寻找的信息.</p>
        <p>有时候仅仅因为没有在页面上找到答案, 你就失去了一笔订单. 因为用户会假设你的产品或者服务无法实现他的需求, 如果你不告诉他们细节的话. 另外一些时候, 这些关于产品的细节特性被淹没在众多的网站信息和庸俗的口号中. 因为用户没有时间去仔细阅读所有的信息, 所以隐藏在一堆信息中就相当于不存在.</p>
        <p>最糟糕的答非所问的例子就是: 避免展示价格. 没有那个B2C网站会犯这种错误. 但是在B2B经常会出现这种问题. 多数企业呈现的信息都让你无法分别他们是适用于100人还是10w人的...价格是用户所希望获得的最明显的信息, 而如果不提供它, 会让用户觉得迷失以及降低他们对一个产品的认知. 我们有一个长达几个小时的视频记录了客户在理发的时候问"价格表在哪里?".</p>
        <p>即便是B2C网站也经常会忘记列出价格, 比如分类页面或者搜索结果页面. 在这两种情况下, 价格也是一个重要信息. 因为它让用户区分不同的商品, 而从最相关的商品中进行挑选.</p>
        <p style="color:#00aa0b;"><i>博主说: </i>反例就是恶意SEO, 典型. 而在现在搜索引擎作为入口, 用户甚至不会记得上次上当的页面...所以也就出现了多次上当的情况....</p>
    </li>
</ol>

Other Top-10 Lists

<ul>
    <li>
        <a href="http://www.nngroup.com/articles/10-high-profit-redesign-priorities/">High-Profit Redesign Priorities </a></li>
    <li>
        <a href="http://www.nngroup.com/articles/movies-usability-top-10-bloopers/">Usability in the Movies</a> — Top 10 Bloopers</li>
    <li>
        <a href="http://www.nngroup.com/articles/most-violated-homepage-guidelines/" title="Alertbox Nov. 2003">Most violated homepage guidelines </a></li>
    <li>
        <a href="http://www.nngroup.com/articles/top-ten-guidelines-for-homepage-usability/" title="Alertbox May 2002">Top homepage usability guidelines </a></li>
    <li>
        <a href="http://www.nngroup.com/articles/ten-good-deeds-in-web-design/" title="Alertbox Oct. 1999">Good deeds in Web design </a></li>
    <li>
        <a href="http://www.nngroup.com/articles/top-ten-web-design-mistakes-of-2005/" title="Alertbox Oct. 2005">Web design mistakes</a> (2005)</li>
    <li>
        <a href="http://www.nngroup.com/articles/top-10-web-design-mistakes-of-2003/" title="Alertbox Dec. 2003">Web design mistakes</a> (2003)</li>
    <li>
        <a href="http://www.nngroup.com/articles/top-ten-web-design-mistakes-of-2002/" title="Alertbox Dec. 2002">Web design mistakes</a> (2002)<br>
        With cartoons.</li>
    <li>
        <a href="http://www.nngroup.com/articles/the-top-ten-web-design-mistakes-of-1999/" title="Alertbox May 1999">Web design mistakes</a> (1999)</li>
    <li>
        <a href="http://www.nngroup.com/articles/original-top-ten-mistakes-in-web-design/" title="Alertbox May 1996">Web design mistakes</a> (1996)<br>
        My first list. Luckily, many of these mistakes have been fixed by now.</li>
    <li>
        <a href="http://www.nngroup.com/articles/top-10-application-design-mistakes/" title="Alertbox Feb. 2008">Application design mistakes </a></li>
    <li>
        <a href="http://www.nngroup.com/articles/top-10-ia-mistakes/" title="Alertbox">Information Architecture (IA) mistakes </a></li>
</ul>

