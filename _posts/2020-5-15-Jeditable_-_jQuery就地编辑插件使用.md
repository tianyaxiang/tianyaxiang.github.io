---
layout:     post
title:      Jeditable_-_jQuery就地编辑插件使用
subtitle:   
date:       2020-5-15
author:     Coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- 网页设计
--- 
<div class="postBody">
			<div id="cnblogs_post_body" class="blogpost-body"><p>    jeditable是一个jquery插件，它的优点是可以就地编辑，并且提交到服务器处理，是一个不可多得的就地编辑插件。<span style="color:#333300;">(注： 就地编辑，也有称即时编辑？一般的流程是这样的，当用户点击网页上的文字时，该文字就会出现在一个编辑框中，用户对文字进行修改完成后点击提交按钮，新的文本将发送到服务器上，然后表单消失，显示最新编辑的文本。</span>),你可以通过这个<a href="http://www.appelsiini.net/projects/jeditable/default.html">演示页面</a>来亲自体验下。</p>
<p>    官网:<a href="http://www.appelsiini.net/projects/jeditable">http://www.appelsiini.net/projects/jeditable</a></p>
<p>基本的使用方法如下：</p>
<p>首先编辑一个 html 文件，包含这么一段：</p>
<div id="highlighter_930412" class="syntaxhighlighter">
<div class="cnblogs_code">
<pre><span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="edit"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="div_1"</span><span style="color:#0000ff;">&gt;</span>Dolor<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
<span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="edit_area"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="div_2"</span><span style="color:#0000ff;">&gt;</span><span style="color:#000000;">Lorem ipsum dolor sit amet, consectetuer 
adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore 
magna aliquam erat volutpat.</span><span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span></pre>
</div>
</div>
<p>然后我们使用如下的 JS 代码来实现即时编辑（要先引入 Jeditable 插件）：</p>
<div class="cnblogs_code">
<pre>$(document).ready(<span style="color:#0000ff;">function</span><span style="color:#000000;">() {
    $(</span>'.edit').editable('http://www.example.com/save.php'<span style="color:#000000;">);
});</span></pre>
</div>
<p> </p>
<p>实现不同内容的编辑以及更多的定制项：</p>
<div class="cnblogs_code">
<pre>$(document).ready(<span style="color:#0000ff;">function</span><span style="color:#000000;">() {
    $(</span>'.edit').editable('http://www.example.com/save.php'<span style="color:#000000;">, {
        indicator : </span>'Saving...'<span style="color:#000000;">,
        tooltip   : </span>'Click to edit...'<span style="color:#000000;">
    });
    $(</span>'.edit_area').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
        type      : </span>'textarea'<span style="color:#000000;">,
        cancel    : </span>'Cancel'<span style="color:#000000;">,
        submit    : </span>'OK'<span style="color:#000000;">,
        indicator : </span>'&lt;img src="img/indicator.gif"&gt;'<span style="color:#000000;">,
        tooltip   : </span>'Click to edit...'<span style="color:#000000;">
    });
});</span></pre>
</div>
<p>上面的定制项包括按钮的文本，提示信息以及提交时的 loading 图片显示等等。</p>
<p>那么当用户点击了确定按钮时，发送到服务器上的是什么数据呢？</p>
<p>数据内容包含了编辑框的 ID 以及新的内容：id=elements_id&amp;value=user_edited_content</p>
<p>你也可以使用下面的方法来修改默认的参数名：</p>
<div class="cnblogs_code">
<pre>$(document).ready(<span style="color:#0000ff;">function</span><span style="color:#000000;">() {
    $(</span>'.edit').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
        id   : </span>'elementid'<span style="color:#000000;">,
        name : </span>'newvalue'<span style="color:#000000;">
    });
});</span></pre>
</div>
<p>修改后传递的数据变成：elementid=elements_id&amp;newvalue=user_edited_content</p>
<p>如果单行文本框不注意满足你的要求，可以使用 textarea 多行文本编辑框：　</p>
<div class="cnblogs_code">
<pre>$(document).ready(<span style="color:#0000ff;">function</span><span style="color:#000000;">() {
    $(</span>'.edit_area').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
        loadurl  : </span>'http://www.example.com/load.php'<span style="color:#000000;">,
        type    : </span>'textarea'<span style="color:#000000;">,
        submit  : </span>'OK'<span style="color:#000000;">
    });
});</span></pre>
</div>
<div id="highlighter_552441" class="syntaxhighlighter">
<p>另外 Jeditable 还支持下拉选择框哦：</p>
<div class="cnblogs_code">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
    data   : </span>" {'E':'Letter E','F':'Letter F','G':'Letter G', 'selected':'F'}"<span style="color:#000000;">,
    type   : </span>'select'<span style="color:#000000;">,
    submit : </span>'OK'<span style="color:#000000;">
});</span></pre>
</div>
<p> </p>
<p>或者你也可以从服务器获取下拉选择的数据内容：</p>
<div class="cnblogs_code">
<pre>&lt;?<span style="color:#000000;">php
 </span><span style="color:#008000;">/*</span><span style="color:#008000;"> http://www.example.com/json.php </span><span style="color:#008000;">*/</span>
 <span style="color:#800080;">$array</span>['E'] =  'Letter E'<span style="color:#000000;">; 
 </span><span style="color:#800080;">$array</span>['F'] =  'Letter F'<span style="color:#000000;">; 
 </span><span style="color:#800080;">$array</span>['G'] =  'Letter G'<span style="color:#000000;">; 
 </span><span style="color:#800080;">$array</span>['selected'] =  'F'<span style="color:#000000;">;
 </span><span style="color:#0000ff;">print</span> json_encode(<span style="color:#800080;">$array</span><span style="color:#000000;">);
</span>?&gt;</pre>
</div>
<p>然后通过 loadurl 指定这个服务器输出数据的 URL 地址：</p>
<div class="cnblogs_code">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
    loadurl : </span>'http://www.example.com/json.php'<span style="color:#000000;">,
    type   : </span>'select'<span style="color:#000000;">,
    submit : </span>'OK'<span style="color:#000000;">
});</span></pre>
</div>
<p> </p>
<p>如果你希望给组件设定不同的样式，可以这样：</p>
<div class="cnblogs_code">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
    cssclass : </span>'someclass'<span style="color:#000000;">
});

$(</span>'.editable').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
    loadurl : </span>'http://www.example.com/json.php'<span style="color:#000000;">,
    type    : </span>'select'<span style="color:#000000;">,
    submit  : </span>'OK'<span style="color:#000000;">,
    style   : </span>'display: inline'<span style="color:#000000;">
});　　</span></pre>
</div>
<p>或者：</p>
<div class="cnblogs_code">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
    loadurl : </span>'http://www.example.com/json.php'<span style="color:#000000;">,
    type    : </span>'select'<span style="color:#000000;">,
    submit  : </span>'OK'<span style="color:#000000;">,
    style   : </span>'inherit'<span style="color:#000000;">
});</span></pre>
</div>
<p>最后来点高级的内容，如果你希望使用一个 JS 函数而不是 URL 来处理提交，可以这样：</p>
<div class="cnblogs_code">
<pre>$('.editable').editable(<span style="color:#0000ff;">function</span><span style="color:#000000;">(value, settings) { 
    console.log(</span><span style="color:#0000ff;">this</span><span style="color:#000000;">);
    console.log(value);
    console.log(settings);
    </span><span style="color:#0000ff;">return</span><span style="color:#000000;">(value);
 }, { 
    type    : </span>'textarea'<span style="color:#000000;">,
    submit  : </span>'OK'<span style="color:#000000;">,
});</span></pre>
</div>
<p>处理回调：　</p>
<div class="cnblogs_code">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="color:#000000;">, { 
    type     : </span>'textarea'<span style="color:#000000;">,
    submit   : </span>'OK'<span style="color:#000000;">,
    callback : </span><span style="color:#0000ff;">function</span><span style="color:#000000;">(value, settings) {
        console.log(</span><span style="color:#0000ff;">this</span><span style="color:#000000;">);
        console.log(value);
        console.log(settings);
    }
});</span></pre>
</div>
<p>使用附加参数：</p>
<div class="cnblogs_code">
<pre>$(".editable").editable("http://www.example.com/save.php"<span style="color:#000000;">;, {
   submitdata : {foo: </span>"bar"<span style="color:#000000;">};
});</span></pre>
</div>
<div id="highlighter_561480" class="syntaxhighlighter"> </div>
<p>直接从URL获取显示内容：</p>
<div class="cnblogs_code">
<pre>$(".editable").editable("http://www.example.com/save.php"<span style="color:#000000;">;, {
    loadurl : </span>"http://www.example.com/load.php"<span style="color:#000000;">

});</span></pre>
</div>
<p>英文原文：<a href="http://www.appelsiini.net/projects/jeditable">http://www.appelsiini.net/projects/jeditable</a></p>
<div id="ckepop"> </div>
<div>
<p id="PSignature" style="line-height:20px;background:#FFFAEA no-repeat 2% 50%;font-size:12px;border:#e0e0e0 1px dashed;"><img title="web馆" src="/img/wx.gif" alt="" width="113" height="113" /><br />  欢迎扫描此二维码关注web馆公众号  <br />  作者：<a href="http://www.webguan.com/">web馆</a>  <br />  出处：<a href="http://www.webguan.com/">http://www.webguan.com/</a> <br />  欢迎任何形式的转载，但请务必注明出处。<br /><br /><br /></p>



</div>


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