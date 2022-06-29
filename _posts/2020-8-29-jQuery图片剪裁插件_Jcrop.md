---
layout:     post
title:      jQuery图片剪裁插件_Jcrop
subtitle:   
date:       2020-8-29
author:     Coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- 工具
--- 
<p>
</p>
<p style="margin-left:auto;text-indent:2em;font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:18px;text-align:left;"><strong>Jcrop</strong>是一个jQuery插件，它能为你的WEB应用程序快速简单地提供图片裁剪的功能。</p>
<p style="margin-left:auto;text-indent:2em;font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:18px;text-align:left;"><strong>特点：</strong></p>
<ul style="margin-left:45px;font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:18px;text-align:left;"><li style="margin-left:0px;">对所有图片均unobtrusively（无侵入的，保持DOM简洁）</li>
<li style="margin-left:0px;">支持宽高比例锁定</li>
<li style="margin-left:0px;"><span>支持 minSize / maxSize设置</span></li>
<li style="margin-left:0px;"><span>支持改变选区或移 动选区时的回调（Callback）</span></li>
<li style="margin-left:0px;"><span>支持用键盘微调选 区</span></li>
<li style="margin-left:0px;"><span>通过API创建互 动，比如动画效果</span></li>
<li style="margin-left:0px;"><span>支持CSS样式</span></li>
</ul><p style="margin-left:auto;text-indent:2em;font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:18px;text-align:left;"><img style="margin-left:0px;background-color:#ededed;clear:both;" src="http://www.oschina.net/uploads/img/200912/27222435_xd9N.png" alt="" /></p>
<p style="margin-left:auto;text-indent:2em;font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:18px;text-align:left;"><strong>入门</strong><br /><span>•</span><a style="color:#2b8dc0;line-height:inherit;text-decoration:none;" href="http://www.open-open.com/home/link.php?url=http://deepliquid.com%2Fcontent%2FJcrop_Download.html">下载当前版本</a><span> </span><br /><span>•放到页面相应的位置</span><br /><span>•同时也需要加载jquery</span><br /><br /><strong>加载顺序</strong><br /><span>•jQuery.js</span><br /><span>•Jcrop.js</span><br /><span>•Jcrop CSS样式</span><br /><span>如：</span><br /><span>&lt;script src="js/jquery.pack.js"&gt;&lt;/script&gt;</span><br /><span>&lt;script src="js/jquery.Jcrop.pack.js"&gt;&lt;/script&gt;</span><br /><span>&lt;link rel="stylesheet" href="css/jquery.Jcrop.css" type="text/css" /&gt;</span><br /><span>注意:你也可以调整成其他的位置</span><br /><br /><strong>调用 <br /></strong><span>假如：&lt;img src="flowers.jpg" id="cropbox" /&gt;</span><br /><span>编写以下脚本</span><br /><span>&lt;script language="Javascript"&gt;</span><br /><span>jQuery(function() {</span><br /><span>jQuery('#cropbox').Jcrop();</span><br /><span>});</span><br /><span>&lt;/script&gt;</span><br /><span>Jcrop就可以激活了</span><br /><br /><strong>事件处理</strong><br /><span>Jcrop有2个主要的事件处理程序 onChange 和 onSelect.</span><br /><span>onSelect callback 选择完成后调用 </span><br /><span>onChange callback 选框移动（或者说改变）时调用</span><br /><span>定义一个事件出来函数</span><br /><span>&lt;script language="Javascript"&gt;</span><br /><span>function showCoords(c)</span><br /><span>{</span><br /><span>// variables can be accessed here as</span><br /><span>// c.x, c.y, c.x2, c.y2, c.w, c.h</span><br /><span>};</span><br /><span>&lt;/script&gt;</span><br /><span>然后附加上去</span><br /><span>&lt;script language="Javascript"&gt;</span><br /><span>jQuery(function() {</span><br /><span>jQuery('#cropbox').Jcrop({</span><br /><span>onSelect: showCoords,</span><br /><span>onChange: showCoords</span><br /><span>});</span><br /><span>});</span><br /><span>&lt;/script&gt;</span><br /><span>这是一个标准的jquery语法，注意最好一个属性后面没有逗号</span><br /><br /><strong>设置选项</strong><br /><span>参数名称 类型 描述 默认 </span><br /><span>aspectRatio decimal 设定宽高比 n/a </span><br /><span>minSize array [ w, h ] 设置最小尺寸 n/a </span><br /><span>maxSize array [ w, h ] 设置最大尺寸 n/a </span><br /><span>setSelect array [ x, y, x2, y2 ] 设置一个初选框的位置 n/a </span><br /><span>bgColor color value 设置背景容器颜色 'black' </span><br /><span>bgOpacity decimal 0 - 1 设置当图像被裁剪选框外的透明度 .6</span><br /><span>如：</span></p>
<div class="cnblogs_code" style="margin-left:0px;background-color:#FFFFFF;font-family:'Courier New';text-align:left;border:0px solid #cccccc;">
<div class="cnblogs_code_toolbar"><span class="cnblogs_code_copy" style="line-height:1.5;"><a style="color:#2b8dc0;line-height:inherit;text-decoration:none;background-color:#f5f5f5;" title="复制代码" href="https://www.leti.ltd/archive/2012/06/29/Jcrop.html"></a></span></div>
<pre>&lt;script language=<span style="font-size:12px;line-height:1.5;color:#800000;">"</span><span style="font-size:12px;line-height:1.5;color:#800000;">Javascript</span><span style="font-size:12px;line-height:1.5;color:#800000;">"</span>&gt;<span style="font-size:12px;line-height:1.5;">
jQuery(function() {
jQuery(</span><span style="font-size:12px;line-height:1.5;color:#800000;">'</span><span style="font-size:12px;line-height:1.5;color:#800000;">#cropbox</span><span style="font-size:12px;line-height:1.5;color:#800000;">'</span><span style="font-size:12px;line-height:1.5;">).Jcrop({
onSelect: showCoords,
bgColor: </span><span style="font-size:12px;line-height:1.5;color:#800000;">'</span><span style="font-size:12px;line-height:1.5;color:#800000;">black</span><span style="font-size:12px;line-height:1.5;color:#800000;">'</span><span style="font-size:12px;line-height:1.5;">,
bgOpacity: .</span><span style="font-size:12px;line-height:1.5;color:#800080;">4</span><span style="font-size:12px;line-height:1.5;">,
setSelect: [ </span><span style="font-size:12px;line-height:1.5;color:#800080;">100</span>, <span style="font-size:12px;line-height:1.5;color:#800080;">100</span>, <span style="font-size:12px;line-height:1.5;color:#800080;">50</span>, <span style="font-size:12px;line-height:1.5;color:#800080;">50</span><span style="font-size:12px;line-height:1.5;"> ],
aspectRatio: </span><span style="font-size:12px;line-height:1.5;color:#800080;">16</span> / <span style="font-size:12px;line-height:1.5;color:#800080;">9</span><span style="font-size:12px;line-height:1.5;">
});
});
</span>&lt;/script&gt;</pre>
<div class="cnblogs_code_toolbar"><span class="cnblogs_code_copy" style="line-height:1.5;"><a style="color:#2b8dc0;line-height:inherit;text-decoration:none;background-color:#f5f5f5;" title="复制代码" href="https://www.leti.ltd/archive/2012/06/29/Jcrop.html"></a></span></div>
</div>
<p style="margin-left:auto;text-indent:2em;font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:18px;text-align:left;"> </p>
<div class="uchome-message-pic" style="font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:18px;text-align:left;"><img style="margin-left:0px;background-color:#ededed;clear:both;" src="http://www.open-open.com/home/attachment/201010/30/361_1288445105hzs8.jpg" alt="" /></div>
