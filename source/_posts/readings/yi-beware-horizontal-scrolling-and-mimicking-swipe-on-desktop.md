category: readings
description: ''
date: 2014-05-03 0:00:00
title: Beware Horizontal Scrolling and Mimicking Swipe on Desktop
tags: [关于HCI,HCIBib,UX,译系列,翻译文章,Carousel,Horizontal]
---

摘要: 即便现在越来越多的站点开始模仿滑动手势以及在PC上非常不适合的横向滑动设计, 用户依然非常不适应这种浏览方式的.
多年一来, 我们一直都知道横向滚动本身对于桌面电脑而言都是难言的痛点. 即便是随着移动设备的普及, 用户逐渐接受了触摸手势是用来浏览内容的, 但是用户在桌面电脑上访问网站时, 依然不会习惯横向滚动的. 本文主要描述了当前触屏交互方式应用到桌面电脑上的一些问题所在, 以及提供了一些备选和建议, 关于如何帮助用户形成这种习惯. 很明显, 你在非触摸屏下是不能使用触摸手势操作的; 所以本文中会以"滑动"(加引号)来表示在桌面电脑上的这一操作.

<h3>横向滚动的诱惑</h3>

在桌面电脑上, 长篇内容型网站的通常交互形式都是纵向的滚动. 鼠标和滚轮本身的上下操作也让这种滚动方式非常简单, 这也就强化了这一行为模式.

那些试图打破这一习惯, 调整网页布局为左右形式的网站, 通常是因为一下几个原因:
<ul>
    <li>
        <strong>Consistency across devices(跨平台的统一性).</strong>
        <p>在移动设备的研究表明横向的滚动模式更为常见, 且用户本身也比较享受这种通过滑动手势来切换的交互形式. 同时那些响应式或者移动优先的站点更是把横向滑动推向了全平台, 当然包含了桌面电脑, 因为一个设计贯穿全平台更能节省成本, 更容易实现而且能够传递一种始终如一的体验一致性. 但是, 因为横向滚动在桌面电脑上并不那么的通用, 用户通常不知道他们可以通过"滑动"来浏览更多的内容. 随着人们区别对待移动设备和桌面设备, 这种"一变应万变"的方法的问题也逐渐暴露了. 关键点在于用户认为的一致性, 是他们在当前设备上浏览网站的各个部分时, 其风格是一致的, 他们很难记住这一习惯或者某个网站的某一交互形式然后带到不同的设备同一网站之中去. </p>
    </li>
    <li>
        <strong>Browsing through nonessential content(浏览那些不重要的信息).</strong>
        <p>并不是所有的信息都是非常关键的. 对于很多辅助信息, 比如说一个图册, 横向滚动本身可以在给用户一个初步的了解的同时提供让用户快速的"滑动"来点击更多内容的可能. 对于一些内容, 用户即便整个过程中都不滚动也是没有问题的. 只要你确认你没有把核心的内容放到一个横向滚动条中, 因为那样的话, 有些人是不会看到的.</p>
    </li>
    <li>
        <strong>Saving vertical screen space(节省纵向的空间)</strong>
        <p>为了不让因为整个内容展现而产生一个个长长的页面, 横向布局把信息分成了一个个部分, 每次用户只需要看一部分. 同时布局本身也足够灵活, 易扩展, 因为内容既可以横向添加也可以纵向添加(译者: 让我想起来以前很流行的一种交互: 上下左右翻的那个cube设计)</p>
        <img src="http://s3.amazonaws.com/media.nngroup.com/media/editor/2014/04/23/hulu-stacked-filmstrips.png" alt="">
        <i>Hulu.com: 影片按照分类堆叠, 这样用户既能在一个分类下通过"滑动"看到更多的内容, 又能上下滚动查看不同的分类. 这种两维的应用可以帮助用户看到更多的选择而不需要访问不同的页面.</i>
    </li>
    <li>
        <strong>Showcasing a distinctive design(为了展示与众不同)</strong>
        <p>很多站点, 尤其是那些艺术家的或者数字广告公司, 通常会利用横向滚动来让自己的站点能够在众多的网站中脱颖而出, 同时秀一下自己的设计水平. 但同时, 对于多数主流网站, 为了不同而不同就是一个非常不糟糕的设计方式了.</p>
    </li>
</ul>
<h3>The Risks of Horizontal Scrolling on the Desktop(在桌面电脑上使用横向滚动的风险)</h3>
虽然横向滚动多数情况下也能勉强接受, 但是应用的时候也请谨慎使用. 要注意: 横向滚动是桌面电脑中少数的几种能够始终让用户生负面反馈的交互形式之一.(有趣的是. 因为对它的蔑视非常的广泛, 我经常利用它来向不熟悉用户体验领域的人阐述用户体验是什么. 我会问他们能够想象一个网站是横向滚动的, 他们通常会抱怨自己讨厌这种方式, 然后我就会解释我们是如何看到这个事情以及我们是如何试图让它变好的. 通常他们会回答: "太赞了, 你这样的人越多越好啊").

虽然"滑动"本身在desktop上不会像横向滚动条一样产生同等的负面效应, 但是它同样面临类似的风险. 我们来看下3个为什么横向滚动和"滑动"在desktop上会出现为问题的原因:
<ol>
    <li>
        <strong>The traditional horizontal scrollbar burdens the user by requiring constant attention and greater physical effort to maintain the dragging.(传统的横向滚动条会加重用户的负担, 因为它们需要持续的注意力以及为维持拖拽动作需要更多的物理消耗)</strong>
        <p>多数人是利用滚动条来滚动的, 而不是箭头. 然而, 在这么狭小的一个槽中移动鼠标是个非常困难的操作, 因为它要操作者更加的细心, 来操作鼠标. (这可以算是steering law[ 用户在一个槽中移动鼠标的时间取决于槽的宽度和长度: 槽越长越细, 用户从一端到另一端所花费的时间就越长.]的一个范例, steering law是从Fitt's law[我们在HCI课程中讨论过]中衍生的.) 因此, 利用滚动条在desktop上是一个非常高成本的交互行为, 而且很容易降低用户的浏览速度. 在最近的一个用户测试中, 一个参与者在滚动浏览一个产品列表时非常的郁闷, 他抱怨道"这个滚动条仿佛要话费我一生的时间去滚动一样...".</p>
    </li>
    <li>
        <strong>Users may ignore content accessible through horizontal scrolling or "swiping" as they don’t expect content there.(用户可能会忽略滚动或者"滑动"出现的内容, 因为他们对这些没有预期.)</strong>
        <p>我们的研究发现即便是很强的引导, 比如箭头, 也经常会被忽视. 人们对于更多内容的展现, 通常期待的都是纵向的滚动操作, 而不是横向. 横向滚动违反了他们长期形成的网页浏览模式.</p>
        <img src="http://s3.amazonaws.com/media.nngroup.com/media/editor/2014/04/23/apple-filmstrip-heatmap.png" alt="Eyetracking heatmap of filmstrip">
        <p>Apple.com: 这个视觉热图显示的是一个用户是如何查看一个产品图片的影集的, 他们连看都没看箭头一眼, 这样也就导致他们永远不会看到影集中的其他图片.</p>
    </li>
    <li>
        <strong>Even obvious cues for horizontal scrolling have weak information scent.(即便是再清晰的横向滚动引导依然缺乏有效的信息)</strong>
        <p>即便用户注意到了横向滚动的引导, 他们也不一定会冒着不知道加载什么东西的预期来去点击的. 横向滚动隐藏的内容处于一个非常劣势的位置, 因为即便是在醒目的视觉引导也不能提供足够的信息: 用户通常很难猜测他们点击后会获得什么. 而对于那种整个页面都"滑动"到新的内容, 就更不用说这种失望的风险就更高了: 用户可能需要等待整个页面加在完全才知道新页面对于他的需求而言没有任何意义...</p>
        <img src="http://s3.amazonaws.com/media.nngroup.com/media/editor/2014/04/23/usatoday-slider-arrow.png" alt="">
        <p>USAToday.com: 用户会忽视页面上的箭头, 因为完全不知道点击后会发生什么? 当被问道用户这些箭头的事情时, 一个用户说"我不会点的 , 我只想看那些我想看的东西".</p>
    </li>
</ol>
<h3>Recommendations for Implementing Horizontal Scrolling or "Swiping" on the Desktop(对于想要在desktop上应用横向滚动和"滑动"操作的建议)</h3>
如果你正在考虑在desktop上模拟滑动手势或者使用横向滚动时, 请遵循以下的建议来让你的用户更容易注意到以及获取到你的内容.
<ol>
    <li>
        <strong>Don’t make "swiping" the primary navigation on your site.(不要把"滑动"作为你站点的主要导航)</strong>
        <p>不要强迫用户"滑动"浏览你的内容: 一些人可能会, 一些人可能不会, 他们会直接离开的. 允许一些备选的方式: 比如给用户一些选项, 允许他们可以可以根据导航菜单来浏览. 菜单会告诉用户你的站点上都有什么, 并且帮助他们找到他们想要的信息. 用户一来他们去深入了解你的站点以及在不同的分类下切换. 没有全局导航的话, 用户就很难浏览来发现更多的内容了.</p>
        <img src="http://s3.amazonaws.com/media.nngroup.com/media/editor/2014/04/23/dennys-global-nav-and-swipe.png" alt="">
        <p>Dennys.com:  这个设计中就提供了非常清晰的全局导航, 弥补了只有箭头的不足. 在测试这个站点时, 一个用户从来没有使用过箭头来切换不同的页面, 他完全只用全局导航来操作, 而且也完成了所有的任务. 同样注意的是: 左右两边保留部分可见内容给用户了一定的预期, 这样当切换的时候内容切换就不会觉得那么的突兀了.</p>
    </li>
    <li>
        <strong>Don’t make users guess how much content is left.(不要让用户去猜测还有多少内容)</strong>
        <p>利用滚动条或者翻页导航来显示用户还有多少内容. 最好的是时刻告诉用户他在哪, 这样他就能更好的指引他自己. 告诉用户还剩多少, 他们就可以决定他们还要看多少, 或者, 对于一个循环来说, 用户需要在他们回到起点的时候知道他们回来了.</p>
        <img src="http://s3.amazonaws.com/media.nngroup.com/media/editor/2014/04/23/amazon-filmstrip-pagination.png" alt="">
        <p>Amazon.com: 页码以及回到初始的链接都提供了非常有用的情景来告诉用户他们还剩多少以及如何快速回到初始.</p>
    </li>
    <li>
        <strong>Create obvious, visible cues for horizontal swiping.(给与明显的, 可见的横向滚动引导)</strong>
        <p>让用户可以利用点击和键盘浏览网页. 如果箭头只有在hover的时候才出现(比如Netflix的例子中[见下]), 用户可能甚至都不会发现这还有更多的内容. 无论对于但页面还是carousel, 都应该突出那些点击区域, 方便用户点击获取更多内容.</p>
        <img src="http://s3.amazonaws.com/media.nngroup.com/media/editor/2014/04/23/netflix-no-arrow-until-hover.png" alt="">
        <p>Netflix.com: 在netflix页面的常态中, 完全看不到任何提示有更多内容的线索(图上位置). 箭头只有在hover后才会显示出来(图下). 另外, 为了看一个分类下的更多影片, 用户必须得hover到箭头上, 一旦他们这么做了,  这个分类就会自动开始滚动, 如果用户想要看到更多, 就必须得一直hover在箭头区域. 这个交互不仅需要花费更多的精力和注意力, 同时还很慢而且很容易产生眼花撩轮的感觉... 而不是觉得有趣... 即便是点击一下然后滑动都比这个好一些...</p>
    </li>
</ol>
<h3>Conclusion(结论)</h3>
<p>滚动和横向"滑动"在desktop上和手机或平板上是完全不同的两种体验. 这也是一个很好的例子去了解为什么用户会区别对待他们的手机, 平板和desktop, 以及为什么要根据不同的使用场景来优化设计会很有好处. 避免为了突出而破坏习俗, 或者为了解决多平台的问题就放弃习惯. 你应该评估一下自己的用户到底适不适合横向滚动, 这样你才能确定你的设计能够提升他们的体验而不是降低这一点. </p>
<p>你可以通过我们的<a href="http://www.nngroup.com/courses/web-page-design/">Web Page Design 课程</a>来了解更多横向滚动, carousel以及胶卷式设计的相关知识, 以及如何应用这些知识.</p>

<strong>Links: </strong>
<li><a href="http://www.nngroup.com/articles/horizontal-scrolling/">原文地址: Beware Horizontal Scrolling and Mimicking Swipe on Desktop</a></li>
<li><a href="http://callmet.zzgary.info/2014/05/03/yi-why-users-arent-clicking-your-home-page-carousel/">Carousel相关的一篇文章, 印证了本文的一些观点.</a></li>

