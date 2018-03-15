category: readings
description: ''
date: 2013-12-25 7:00:00
title: USING SASS–Chapter 4(全书完)
tags: [HCIBib,译系列,Sass for web designers,Sass,翻译文章]
---

<h2><strong>Sass and media queries</strong></h2>
本书最后一章.

我希望本书能一直聚焦在sass的基本应用上, 以此来证明sass不需要扰乱你本身现有的工作流. 但是在最后一章, 我还是想要讨论一些使用Sass和Media Queries部分的高级技巧, 这些技巧已经帮助我简化了很多css中非常复杂的地方.

Sass的强大超出你的想象.利用一些变量和几个mixin就能让你的生活变得简单许多. 但是它也可以做很多除以之外的部分. 在这里我希望能分享的是我是如何利用Sass来制作响应式布局以及高保真的项目的, 以及它是如何再次把附在的事情变得非常易于管理的.

<h3><strong>嵌套的Media Queries</strong></h3>

响应式布局站点的奠基石之一就是Media Queries. 通过监听浏览器的不同维度的信息, 就可以针对这些信息给予对应的样式, 这就是创建响应式布局的基础.

比如, 你可能想要在浏览器小于800px宽的时候调整其中元素的宽度, 就需要用到Meida Query:

``` css

section.main{
	float:left;
	width: 65%;
	font-size:16px;
	line-height:1.4;
}
@media screen and (max-width: 800px){
	section.main{
      float: none;
      width: auto;
  }
}

```

在Sass中, 你可以通过把media queries嵌套在原本的声明之中, 然后再编译的时候就会自动分散到对应情况下独立的声明了~NICE!

``` css

section.main{
	float:left;
	width: 65%;
	font-size:16px;
	line-height:1.4;
	
	@media screen and (max-width: 800px){
      float: none;
      width: auto;
  	}

	@media screen and (max-width:500px){
		font-size:12px;
		line-height: 1.4;
	}
}

```

以上在编译后就会成为之前分开写的时候那样了(除了500px没有以外)~(见第一个代码示例~)

嵌套media queries可以避免你在多个断点测试的时候不断的重写selector(本例中就是section.main)了.

同时media-query的声明就放在元素定义的下方, 本身也是一种极大的便利. 我已经感受到了在多个断点(就是分辨率的意思,此处)下, 如果把每个断点的media-query都写在对应元素下的极大好处了~比单独放在一个文件或者样式的最后面都要好很多.

<h5><strong>Using variables to define breakpoints</strong></h5>
Media-query bubbling是sass为响应式设计带来了极大的便利性. 但是这里依然还会有很多重复性的代码. 在每一个声明里, 我们都会定义一个断点(比如之前的800px和500px), 通常在设计中, 我会基于特定的设计来调整断点,然后观察页面的布局反应, 而不完全依赖于静态的设备尺寸~换句话说, 这些断点都是可能变化的. 而如果能够定义一次, 然后每次都在一个地方修改会好很多. Sass中的变量再次有了用武之地哈!

首先我们来试着创建三个断点. 命名的时候注意灵活而不是和某个设备绑定了~

``` css

$width-small: 500px;
$width-medium: 800px;
$width-large: 1200px;

```

通过把断点设定为Sass中的变量, 我们就可以在之后的使用中去调用这些变量. 比如:


``` css

section.main{
	float:left;
	width: 65%;
	font-size:16px;
	line-height:1.4;
	
	@media screen and (max-width: $width-large){
      float: none;
      width: auto;
  	}

	@media screen and (max-width:$width-medium){
		font-size:12px;
		line-height: 1.4;
	}
}

```

编译(略)
如果我们稍后决定修改这些断点,就可以只需要去编辑变量本身,而sass会自动把后面的所有引用修改了~ 这对于开发响应式布局的页面有着极好的帮助, 因为设计者需要根据不同的页面宽度来决定什么样的断点是合适去调整布局的~

这里甚至是支持数学计算的, 比如我们可以在断点的值上进行加减的操作.

``` css

section.main{
	float:left;
	width: 65%;
	font-size:16px;
	line-height:1.4;
	
	@media screen and (max-width: $width-large+1){
      float: none;
      width: auto;
  	}
	/* 这里最后编译后就会变成1201px; */
	@media screen and (max-width:$width-medium-1){
		font-size:12px;
		line-height: 1.4;
	}
	/* 这里最后编译后就会变成799px; */
}

```

更进一步, 你还可以把整个media query都定义成一个变量(而不只是那个数字);

``` css

$mobile-first: "screen and (min-width:300px)";

@media #($mobile-first){
	#content {
		font-size: 14px;
		line-height: 1.5;
	}
}

```

注意此处的转义符号: #{},这是一个特殊的方式, 专门用来提示sass去编译包含属性名称或者selector名称的变量, 否则会当成文本来处理的.

当你把media-queries嵌套在对应的声明中后, 变量的定义会让你省去很多的重复. 但是我们可能甚至想要进一步的简化, 就需要使用@content模块了, 也是在Sass 3.2 中引入的.

<h5><strong>Combining @content blocks and mixins</strong></h5>
通过使用Sass的@content, 你可以把整个样式模块都传递给一个mixin之中, 而且sass还可以把这些模块跟随mixin一起放回到声明之中. 听起来似乎有些困惑, 但是实际上使用起来是非常简单而且便捷的.

让我们创建一个响应式模块来处理三个不同的断点,利用@content来引入我们需要引入的模块样式. 同时依然使用变量来处理断点宽度值.

``` css

$width-small: 500px;
$width-medium: 800px;
$width-large: 1200px;

@mixin responsive($width){
	@if $width == wide-screens {
		@media only screen and (max-width: $width-large){@content;}
	}
	@else if $width == medium-screens{
		@media only screen and (max-width: $width-medium){@content;}
	}
	@else if $width==small-screens{
		@media only screen and (max-width: $width-small) {@content;}
	}
}

```


注意到Sass同样支持@if,@else语句, 通过它们我们就可以来评估$width变量的大小从而使用不同的样式模块. 比如, 如果我们传进mixin的是medium-screens变量, sass就可以把media-query按照我们设定给$width-medium的变量来处理. @content允许我们更进一步的传递我们插入到media-query之中的样式模块给mixin. 利用这么一个mixin, 我们就可以在任何地方使用一个非常简洁的模式去调用它:

``` css

#content{
	float: left;
	width: 70%;
	@include responsive(wide-screens){width:80%;}
	@include responsive(medium-screens){width:50%; font-size: 14px;}
	@include responsive(small-screens){float:none;width:100%;font-size:12px;}
}

```

上述编译结果(略)

是不是觉得很神奇呢~ Sass可以把任何样式恰当的传递给media-query并且重构整个声明. 利用@content模块来补充需要填写在media-query中的内容就可以让整个响应式环节的设计更加简单---少了很多的重复.

如此再去理解一个元素是如何在不同的设备中变化适应就会非常容易了, 比如, 随着设备的不同, 同一个网站的同一个标题为什么会不一样大小呢? 其实隐藏其中的就是这么简单:

``` css

h1{
	font-size: 40px;
	@include responsive(wide-screens){font-size: 48px;}
	@include responsive(medium-screens){font-size: 32px;}
	@include responsive(small-screens){font-size:20px;}
}

```

编译略

<h5><strong>Keep the output in mind</strong></h5>

一定要指出的就是上述方法会导致最后的编译输出结果出现大量重复的media-queries. 完美的事情就是Sass可以允许我们通过嵌套queries来让结构变得更清晰, 更整合.

比如:

``` css

blockquote{
	width: 100%;
	@include responsive(wide-screens){width: 80%;}
}
figure {
	margin: 0 0 20px 0;
	@include responsive(wide-screens){margin: 0 0 30px 0;}
}

```

如此就会让编译更加高效, 因为公用的部分放进了一个media-query:

``` css

blockquote {
	width: 100%;
}
figure {
	margin: 0 0 20px 0;
}

@media only screen and (max-width: 1200px){
	blockquote{
		width:80%;
	{
	figure {
		margin: 0 0 30px 0;
	}
}

```

对于一个非常大的,因为响应式设计而包含了很多常用的media queries断点的样式文件, 就可以通过这种方式减少一些体积~

不幸的是, Sass不支持(至少目前是的)"聚合的media querry",就如同我说的, 但是对于多数项目而言, 代价也就是编译的css文件会大一些而已, 但是针对其带来的易用性和很好的整合方式都是非常值得的. 到目前来说, 这就是我们如何做的了.

<h3><strong>RETINIZING HIDPI BACKGROUND IMAGES(背景图片的高清视网膜化)</strong></h3>

仿佛是觉得事情还不够麻烦, 随着高分辨率屏幕的诞生, 网页设计师们又遇到了一个新的挑战. 比如,苹果公司推出的非常华丽的视网膜屏幕, 就把像素数目再一次的翻倍了...这意味着我们会拥有更加清晰好看的图像,同时还可以对那些模糊的像素们说再见了! 但是这一切的前提都是你要花时间去创作这种高质量的图片.

对于img元素, 这也意味着可以通过调整width而实现在展现2倍大小的图片而只占用一半的大小. 更甚者, 还可以用media-query和js来处理图像的展示方式(模糊到清晰的渐变).

再次分享一个HiDPI的图片示例, Sasquatch Records 的logo, 是133x121px的大小. 对于支持更大分辨率的设备, 我们需要创建第二个版本, 是这一版本的两倍大(266x242px)同时需要把它压缩到133px来让它更加清晰.

对于背景图片, 我们只需要简单的使用CSS media queries(在现在的支持mediaquery的浏览器中)就可以决定是否使用HiDPI的方式来渲染图片尺寸. 在我们的示例网站中, 比如, 我们需要一组社交网站的连接, 侧边栏的位置上. 每一个连接的icon都有一个特定的背景图片. 在dribbble的链接上, CSS把一个正常的分辨率的图片放置在文字的左侧:

``` css

ul.follow li.dribbble a{
	padding-left: 30px;
	background-repeat: no-repeat;
	background-position: 0 50%;
	background-image: url(../img/icon-dribbble.png);
}

```

而对于那些HiDPI的显示器, 我们需要重置这一图片,换用另一个两倍大的图标,然后压缩到这么大~ 首先为了检测是否是支持HiDPI的显示器, 我们需要使用media query中的min-device-pixel-ratio属性.

``` css

@media (-webkit-min-device-pixel-ratio: 1.5),(min--moz-device-pixel-ratio:1.5),(-o-min-device-pixel-ratio:3/2),(min-device-pixel-ratio:1.5),(min-resolution:1.5dppx){
	ul.follow li.dribbble a{
		padding-left: 30px;
		background-repeat: no-repeat;
		background-position: 0 50%;
		background-image: url(../img/icon-dribbble-2x.png);
		-webkit-background-size: 24px 24px;
		-moz-background-size: 24px 24px;
		background-size: 24px 24px;
	}
}

```

本质上, 我们认为如果显示器的分辨率在1.5倍与通常的分辨率,我们就是用一个更大的图标, 然后压缩这一图标来达到更清晰的目的.

区别在于, 当在一个HiDPI的显示器上展示时, 会非常的清晰. 所有模糊的边际都会消失不见的.

如你想象的那样, 要想让你的界面视网膜化, 你需要一堆的重复工作...每次都需要在media query中引用做好的第二张大图片, 以覆盖普通分辨率下的图片. 如下是sass是如何让这一过程简单化的.

我们可以创建一个sass的mixin来处理所有的麻烦事, 在创建图片的时候就把两个文件名设置的有些关联~方便的找到普适的规律:

如下是我在日常工作中使用的retinize mixin:

``` css

@mixin retinize{$file,$type,$width,$height){
	background_image: url('../img/'+$file + '.'+$type);
	
	@media (-webkit-min-device-pixel-ratio: 1.5),(min--moz-device-pixel-ratio:1.5),(-o-min-device-pixel-ratio:3/2),(min-device-pixel-ratio:1.5),(min-resolution:1.5dppx){
	&amp; {
		background-image: url('../img/'+$file+'-2x.'+$type);
			-webkit-background-size: $width $height;
			-moz-background-size: $width $height;
			background-size: $width $height;
		}
	}
}

```

第一行中设置了4个参数,是我们需要用来传递给他的图片信息:
<ul>
  	<li>文件名称;</li>
	<li>文件类型, 即图片的格式;</li>
	<li>图片展示的宽度;</li>
	<li>图片展示的高度;</li>
</ul>
在实际使用中,按照顺序填上对应的参数即可调用此mixin了~比如:

``` css

li.dribbble a{
	@include retinize('icon-dribbble','png',24px,24px);
}

```

回归mixin本身, 第二行则形成了一个常规分辨率下背景图片的规则~

Sass支持信息的连接~

``` css

background-image: url('../img/'+$file+'.'+$type);

```

通过添加文件的路径,然后加上文件名以及文件类型,就可以形成完整的一个路径信息,然后就可以和正常的信息一样使用了~

放置好了常规分辨率的图片后, 我们可以添加media query来处理那些需要double的图片的设备. 首先是需要包含所有的浏览器属性(-webkit,-o等)以保证所有的浏览器都可以生效...


``` css

@mixin retinize{$file,$type,$width,$height){
	background_image: url('../img/'+$file + '.'+$type);
	
	@media (-webkit-min-device-pixel-ratio: 1.5),(min--moz-device-pixel-ratio:1.5),(-o-min-device-pixel-ratio:3/2),(min-device-pixel-ratio:1.5),(min-resolution:1.5dppx){
	&amp; {
		background-image: url('../img/'+$file+'-2x.'+$type);
		}
	}
}

```

然后通过&amp;来指代调用此mixin的selector(前文中说到过).
注意到我们同样使用了sass的连接功能来添加-2x这个后缀到每个文件名来指代那些翻倍的图片文件. 用这种非常规律的命名方式来给你的图片命名是非常有利于sass的整合的~
比如:
<ul>
  	<li>常规的图片名称: file-name.png;</li>
	<li>@2x 代表高质量的图片: file-name-2x.png;</li>
</ul>
你当然不是一定要用-2x来代表高分辨率下的图片, 你完全可以按照你自己的喜好来选择合适的文件名称~但是我觉得2x最为简单刚好~

这个mixin的最后一部分就是background-size属性~当然也包含浏览器的前缀~
如此就形成了最后完整的mixin~

这就是一个科重复使用的,服务于高保真图片的mixin, 你可以方便的在任意一个selector中调用它~只需要非常简单的一行代码即可~

``` css

li.dribbble a{
	@include retinize('icon-dribbble','png',24px,24px);
}

```


<h5><strong>mixins inside mixins</strong></h5>
mixin中完全可以包含其他的mixin, 构成一个mixin集合~不要担心,宇宙不会爆炸的...实际上, 我们可以一步步的实践DRY原则, 手续爱你可以把浏览器前缀等规则转移到变量之中~然后把这些属性嵌入到对应的mixin中. 再把那些可以重复使用的部分都摘出来整合到mixins中. 而把你所有的浏览器前缀属性都设置到一起的好处就是我们可以在需要的时候方便的修改和调整他们~当然包括删除它们~~

首先, 我们需要替换pixel-ratio, 把它作为一个变量, 方便后面的重复使用~ 如本章之前提到的那样, 注意在mixin之中的变量一定要加上#{}的符号~来告诉sass这里可能有变量~之后我们就可以把一大推的pixel-ratio定义为变量, 这些在之后的样式中也会经常使用~

``` css

$is-hidpi:
"(-webkit-min-device-pixel-ratio: 1.5),(min--moz-device-pixel-ratio:1.5),(-o-min-device-pixel-ratio:3/2),(min-device-pixel-ratio:1.5),(min-resolution:1.5dppx)";

```

接下来, 则是为background-size创建一个mixin~接受width和height两个参数~同时包含所有相关的浏览器前缀属性以及没有前缀的属性...(这不是废话吗...译者注)


``` css

	@mixin background-size($width,$height){
			-webkit-background-size: $width $height;
			-moz-background-size: $width $height;
			background-size: $width $height;
		}

```


最核心的时候到了~我们可以在retinize的mixin中调用background-size这个mixin~如下:

``` css

@mixin retinize{$file,$type,$width,$height){
	background_image: url('../img/'+$file + '.'+$type);
	
	@media #{$is-hidpi}{
	&amp; {
		background-image: url('../img/'+$file+'-2x.'+$type);
		@include background-size($width,$height);
		}
	}
}

```

如此就是如何在mixin中嵌套mixin了~我们重构了最初的retinize mixin~如此会进一步的减少很多重复的代码~同时还可以把共享的代码段放在尽可能少的地方,以便于之后的更新和维护.

<h3><strong>Wrapping up</strong></h3>

我希望这本小书能够帮助你开始你的Sass之旅, 同时能让你对Sass的核心功能特点有所了解. 我同样希望它能够消除一些关于sass承受的部分曲解:
<ul>
  	<li>你需要先学ruby;</li>
	<li>你需要完全变更自己的css方式;</li>
  	<li>你需要成为一个命令行专家;</li>
</ul>
正如我们讨论的那样, 真实情况是更为简单的. 但是Sass可以称为你所想要的那么强大, 至少, 他是一个非常棒的工具, 而且可以非常友好的结合到你的系统和工作流程中去, 而不需要打乱你本身的css风格和习惯.

现在是用Sass来简化你的样式的时候了~节省自己的时间,最重要的是,做最酷的事情!

==============全书完!=============================
