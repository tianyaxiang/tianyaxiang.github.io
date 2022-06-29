---
layout:     post
title:      CSS:_清除浮动－使用:Overflow
subtitle:   
date:       2020-11-18
author:     coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- java
--- 
<div class="postBody">
			<div id="cnblogs_post_body" class="blogpost-body"><p><span class="Apple-style-span" style="color:#60493e;font-family:Georgia, 'Times New Roman', Times, serif;font-size:16px;line-height:24px;"><span><span>     <span class="Apple-style-span" style="color:#60493e;font-family:Georgia, 'Times New Roman', Times, serif;font-size:16px;line-height:24px;">在使用Div+Css布局的时候</span>我们所面临的共同问题之一是，包装容器不扩到子元素的浮动元素的高度。</span></span><span><span>你也可以使用overflow属性来解决这个问题 ？</span><span>这不是一个新的CSS技巧。</span></span><span><span>今天，我想重新</span></span></span><span class="Apple-style-span" style="color:#60493e;font-family:Georgia, 'Times New Roman', Times, serif;font-size:16px;line-height:24px;">拾</span><span class="Apple-style-span" style="color:#60493e;font-family:Georgia, 'Times New Roman', Times, serif;font-size:16px;line-height:24px;">起这几个技巧的话题。</span></p>
<p><span class="Apple-style-span" style="color:#60493e;font-family:Georgia, 'Times New Roman', Times, serif;font-size:16px;line-height:24px;">演示地址：</span><a href="http://webdesignerwall.com/demo/clear-float/">http://webdesignerwall.com/demo/clear-float/</a></p>
<p style="margin-left:0px;"><span><span> 演示1：</span></span></p>
<p style="margin-left:0px;"><span><span>     下面的演示中显示的浮动子元素在父容器高度不自动适应的问题 。</span><span>为了解决这个问题，您可以简单地添加CSS属性overflow:auto (or overflow:hidden)的包装容器。</span><span>这也许是最简单的方法来清除浮动。</span></span></p>
<p class="image" style="margin-left:0px;"><a href="http://webdesignerwall.com/demo/clear-float/" style="text-decoration:none;color:#834202;background-color:transparent;border-bottom-style:none;"><img src="http://www.webdesignerwall.com/wp-content/uploads/2011/02/overflow-auto.png" alt="溢出汽车" style="border-top-width:0px;border-right-width:0px;border-bottom-width:1px;border-left-width:0px;background-color:#ffffff;border-bottom-style:solid;border-bottom-color:#c4c2b7;" /></a></p>
<p class="image" style="margin-left:0px;"></p>
<div class="cnblogs_code">
<pre><span style="color:#800000;">.container </span>{<span style="color:#ff0000;"><br />    overflow</span>:<span style="color:#0000ff;"> auto</span>;<span style="color:#ff0000;"><br /></span>}</pre>
</div>
<p class="image" style="margin-left:0px;"><span style="color:#585535;font-family:Consolata, monospace;font-size:x-small;"><span class="Apple-style-span" style="line-height:18px;word-spacing:-3px;"><br /><span class="Apple-style-span" style="color:#60493e;font-family:Georgia, 'Times New Roman', Times, serif;font-size:15px;line-height:22px;word-spacing:0px;"></span></span></span></p>
<h3 style="margin-left:0px;font-family:Arial, Helvetica, sans-serif;line-height:27px;font-weight:bold;color:#453630;font-size:21px;letter-spacing:-.04em;"><span><span>演示2：</span></span></h3>
<p class="image" style="margin-left:0px;"></p>
<p style="margin-left:0px;"><span><span>Overflow:auto 也可以用来防止从周围的浮动元素包装的内容。</span><span>比方说，你正在设计一个评论列表。</span><span>您将最有可能，有一个头像，浮于左，评论在右。</span><span>要防止的头像周围环绕的评论，只需添加 overflow:hidden 的评论容器。</span><span>使用overflow这里的优点是，我没有给评论容器设置一个float or width。</span><span>容器自动校准浮动的头像图片。</span></span></p>
<p class="image" style="margin-left:0px;"></p>
<p class="image" style="margin-left:0px;"><a href="http://webdesignerwall.com/demo/clear-float/demo2.html" style="text-decoration:none;color:#57320e;background-color:transparent;border-bottom-style:none;border-top-color:#d1cb7d;border-right-color:#d1cb7d;border-left-color:#d1cb7d;"><img src="http://www.webdesignerwall.com/wp-content/uploads/2011/02/overflow-auto-2.png" alt="溢出汽车" style="border-top-width:0px;border-right-width:0px;border-bottom-width:1px;border-left-width:0px;background-color:#ffffff;border-bottom-style:solid;border-bottom-color:#c4c2b7;" /></a></p>
<p class="image" style="margin-left:0px;"></p>
<div class="cnblogs_code">
<pre><span style="color:#800000;">.image </span>{<span style="color:#ff0000;"><br />    float</span>:<span style="color:#0000ff;"> left</span>;<span style="color:#ff0000;"><br /></span>}<span style="color:#800000;"><br /><br />.text </span>{<span style="color:#ff0000;"><br />    overflow</span>:<span style="color:#0000ff;"> hidden</span>;<span style="color:#ff0000;"><br /></span>}</pre>
</div>
<h3 style="margin-left:0px;font-family:Arial, Helvetica, sans-serif;line-height:27px;font-weight:bold;color:#453630;font-size:21px;letter-spacing:-.04em;"><span><span>缺点（参见</span></span><a href="http://webdesignerwall.com/demo/clear-float/drawbacks.html" style="text-decoration:none;color:#834202;border-bottom-style:solid;border-bottom-width:1px;border-bottom-color:#cfcebe;"><span><span>演示</span></span></a><span><span>）</span></span></h3>
<p style="margin-left:0px;"><span><span><span style="color:#60493e;">虽然它是一个很好的的技巧，也</span><span style="color:#834202;">有</span></span></span><span style="color:#60493e;"><span>一些弊端：</span></span></p>
<ul style="color:#60493e;margin-left:24px;line-height:22px;"><li style="margin-left:0px;"><span><span>使用 overflow:auto，会造成一个滚动条，如果您的内容是延长了容器的边界。</span><span>例如，如果你有一个长unbreaking的文本（即长的URL文本）或一个较大的图像，是更大的，则容器滚动显示。</span></span></li>
<li style="margin-left:0px;"><span><span>为了避免一个滚动显示你应该使用overflow:hidden。</span><span>然而，<span>这种方法</span><span>也</span><span>有一个</span><span>缺点</span>。</span><span>使用overflow:hidden隐藏任何超出容器的边界的内容。</span></span></li>
</ul><h3 style="margin-left:0px;font-family:Arial, Helvetica, sans-serif;line-height:27px;font-weight:bold;color:#453630;font-size:21px;letter-spacing:-.04em;">Word-wrap</h3>
<p style="margin-left:0px;"><span><span>为了解决大文本问题，只需添加 word-wrap:break-word 到容器，这将迫使文本换行到一个新的行。</span></span></p>
<div class="cnblogs_code">
<pre><span style="color:#800000;">.container </span>{<span style="color:#ff0000;"><br />    word-wrap</span>:<span style="color:#0000ff;"> break-word</span>;<span style="color:#ff0000;"><br /></span>}</pre>
</div>
<h3 style="margin-left:0px;font-family:Arial, Helvetica, sans-serif;line-height:27px;font-weight:bold;color:#453630;font-size:21px;letter-spacing:-.04em;">Max-width</h3>
<p style="margin-left:0px;"><span><span>为了防止图像扩大超出容器边界，添加的max-width:100%，它会调整图像的大小符合容器的最大宽度。</span></span></p>
<div class="cnblogs_code">
<pre><span style="color:#800000;">.container img </span>{<span style="color:#ff0000;"><br />    max-width</span>:<span style="color:#0000ff;"> 100%</span>;<span style="color:#ff0000;"><br />    height</span>:<span style="color:#0000ff;"> auto</span>;<span style="color:#ff0000;"><br /></span>}</pre>
</div>
<p>


</p>
<p style="margin-left:0px;">英文原稿：<a href="http://webdesignerwall.com/tutorials/css-clearing-floats-with-overflow" style="color:#3975ce;text-decoration:none;">CCSS: Clearing Floats with Overflow| WebDesignerWall</a></p>
<p style="margin-left:0px;"><a href="http://www.webdesignerwall.com/tutorials/css3-dropdown-menu/" style="color:#3975ce;text-decoration:none;"></a>翻译整理：<span style="color:#3975ce;"><a href="http://www.cnblogs.com/xiaoyao2011/archive/2011/10/10/2205353.html" style="color:#3975ce;text-decoration:none;">CSS: 清除浮动－使用:Overflow</a> | <a href="http://www.cnblogs.com/xiaoyao2011/" style="color:#3975ce;text-decoration:none;">孟晨</a></span></p>
<div id="ckepop">
<div></div>
<div style="clear:both;"></div>
</div>
<div>
<p id="PSignature" style="line-height:20px;background:#FFFAEA no-repeat 2% 50%;font-size:12px;border:#e0e0e0 1px dashed;">作者：<a href="http://www.cnblogs.com/xiaoyao2011/">孟晨</a> <br /> 出处：<a href="http://www.cnblogs.com/xiaoyao2011/">http://www.cnblogs.com/xiaoyao2011/</a> <br />欢迎任何形式的转载，但请务必注明出处。</p>
</div></div><div id="MySignature"></div>
<div class="clear"></div>
<div id="blog_post_info_block">
<div id="BlogPostCategory"></div>
<div id="EntryTag"></div>
<div id="blog_post_info">
</div>
<div class="clear"></div>
<div id="post_next_prev"></div>
</div>


		</div>