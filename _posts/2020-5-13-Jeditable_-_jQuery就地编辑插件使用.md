---
layout:     post
title:      Jeditable_-_jQuery就地编辑插件使用
subtitle:   
date:       2020-5-13
author:     coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- 用户体验
--- 
<p><span style="font-family:'Helvetica Neue', Helvetica, Arial, sans-serif;font-size:13px;line-height:19px;">
</span></p><p style="margin-left:auto;text-indent:2em;"> jeditable是一个jquery插件，它的优点是可以就地编辑，并且提交到服务器处理，是一个不可多得的就地编辑插件。<span style="color:#333300;">(注： 就地编辑，也有称即时编辑？一般的流程是这样的，当用户点击网页上的文字时，该文字就会出现在一个编辑框中，用户对文字进行修改完成后点击提交按钮，新的文本将发送到服务器上，然后表单消失，显示最新编辑的文本。</span>),你可以通过这个<a style="color:#2b8dc0;font-weight:inherit;line-height:inherit;text-decoration:none;" href="http://www.appelsiini.net/projects/jeditable/default.html">演示页面</a>来亲自体验下。</p>
<p style="margin-left:auto;text-indent:2em;">    官网:<a style="color:#2b8dc0;font-weight:inherit;line-height:inherit;text-decoration:none;" href="http://www.appelsiini.net/projects/jeditable">http://www.appelsiini.net/projects/jeditable</a></p>
<p style="margin-left:auto;text-indent:2em;">基本的使用方法如下：</p>
<p style="margin-left:auto;text-indent:2em;">首先编辑一个 html 文件，包含这么一段：</p>
<div id="highlighter_930412" class="syntaxhighlighter" style="margin-left:0px;font-size:1em;background-color:#ffffff;">
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<pre><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&lt;</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800000;">div </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#ff0000;">class</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">="edit"</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#ff0000;"> id</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">="div_1"</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&gt;</span>Dolor<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&lt;/</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800000;">div</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&gt;</span>
<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&lt;</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800000;">div </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#ff0000;">class</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">="edit_area"</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#ff0000;"> id</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">="div_2"</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&gt;</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">Lorem ipsum dolor sit amet, consectetuer 
adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore 
magna aliquam erat volutpat.</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&lt;/</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800000;">div</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">&gt;</span></pre>
</div>
</div>
<p style="margin-left:auto;text-indent:2em;">然后我们使用如下的 JS 代码来实现即时编辑（要先引入 Jeditable 插件）：</p>
<div class="cnblogs_code" style="margin-left:0px;background-color:#FFFFFF;font-family:'Courier New';font-size:12px;border:0px solid #cccccc;">
<pre>$(document).ready(<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">function</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">() {
    $(</span>'.edit').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">);
});</span></pre>
</div>
<p style="margin-left:auto;text-indent:2em;"> </p>
<p style="margin-left:auto;text-indent:2em;">实现不同内容的编辑以及更多的定制项：</p>
<div class="cnblogs_code" style="margin-left:0px;background-color:#FFFFFF;font-family:'Courier New';font-size:12px;border:0px solid #cccccc;">
<div class="cnblogs_code_toolbar"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:inherit;line-height:inherit;text-decoration:none;background-color:#f5f5f5;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
<pre>$(document).ready(<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">function</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">() {
    $(</span>'.edit').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, {
        indicator : </span>'Saving...'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        tooltip   : </span>'Click to edit...'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
    });
    $(</span>'.edit_area').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
        type      : </span>'textarea'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        cancel    : </span>'Cancel'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        submit    : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        indicator : </span>'&lt;img src="img/indicator.gif"&gt;'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        tooltip   : </span>'Click to edit...'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
    });
});</span></pre>
<div class="cnblogs_code_toolbar"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:inherit;line-height:inherit;text-decoration:none;background-color:#f5f5f5;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
</div>
<p style="margin-left:auto;text-indent:2em;">上面的定制项包括按钮的文本，提示信息以及提交时的 loading 图片显示等等。</p>
<p style="margin-left:auto;text-indent:2em;">那么当用户点击了确定按钮时，发送到服务器上的是什么数据呢？</p>
<p style="margin-left:auto;text-indent:2em;">数据内容包含了编辑框的 ID 以及新的内容：id=elements_id&amp;value=user_edited_content</p>
<p style="margin-left:auto;text-indent:2em;">你也可以使用下面的方法来修改默认的参数名：</p>
<div class="cnblogs_code" style="margin-left:0px;background-color:#FFFFFF;font-family:'Courier New';font-size:12px;border:0px solid #cccccc;">
<pre>$(document).ready(<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">function</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">() {
    $(</span>'.edit').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
        id   : </span>'elementid'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        name : </span>'newvalue'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
    });
});</span></pre>
</div>
<p style="margin-left:auto;text-indent:2em;">修改后传递的数据变成：elementid=elements_id&amp;newvalue=user_edited_content</p>
<p style="margin-left:auto;text-indent:2em;">如果单行文本框不注意满足你的要求，可以使用 textarea 多行文本编辑框：　</p>
<div class="cnblogs_code" style="margin-left:0px;background-color:#FFFFFF;font-family:'Courier New';font-size:12px;border:0px solid #cccccc;">
<div class="cnblogs_code_toolbar"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:inherit;line-height:inherit;text-decoration:none;background-color:#f5f5f5;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
<pre>$(document).ready(<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">function</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">() {
    $(</span>'.edit_area').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
        loadurl  : </span>'http://www.example.com/load.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        type    : </span>'textarea'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
        submit  : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
    });
});</span></pre>
<div class="cnblogs_code_toolbar"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:inherit;line-height:inherit;text-decoration:none;background-color:#f5f5f5;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
</div>
<div id="highlighter_552441" class="syntaxhighlighter" style="margin-left:0px;font-size:1em;background-color:#ffffff;">
<p style="margin-left:auto;text-indent:2em;">另外 Jeditable 还支持下拉选择框哦：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
    data   : </span>" {'E':'Letter E','F':'Letter F','G':'Letter G', 'selected':'F'}"<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    type   : </span>'select'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    submit : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
});</span></pre>
</div>
<p style="margin-left:auto;text-indent:2em;"> </p>
<p style="margin-left:auto;text-indent:2em;">或者你也可以从服务器获取下拉选择的数据内容：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
<pre>&lt;?<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">php
 </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#008000;">/*</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#008000;"> http://www.example.com/json.php </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#008000;">*/</span>
 <span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800080;">$array</span>['E'] =  'Letter E'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">; 
 </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800080;">$array</span>['F'] =  'Letter F'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">; 
 </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800080;">$array</span>['G'] =  'Letter G'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">; 
 </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800080;">$array</span>['selected'] =  'F'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">;
 </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">print</span> json_encode(<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#800080;">$array</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">);
</span>?&gt;</pre>
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
</div>
<p style="margin-left:auto;text-indent:2em;">然后通过 loadurl 指定这个服务器输出数据的 URL 地址：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
    loadurl : </span>'http://www.example.com/json.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    type   : </span>'select'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    submit : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
});</span></pre>
</div>
<p style="margin-left:auto;text-indent:2em;"> </p>
<p style="margin-left:auto;text-indent:2em;">如果你希望给组件设定不同的样式，可以这样：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
    cssclass : </span>'someclass'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
});

$(</span>'.editable').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
    loadurl : </span>'http://www.example.com/json.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    type    : </span>'select'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    submit  : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    style   : </span>'display: inline'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
});　　</span></pre>
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
</div>
<p style="margin-left:auto;text-indent:2em;">或者：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
    loadurl : </span>'http://www.example.com/json.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    type    : </span>'select'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    submit  : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    style   : </span>'inherit'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">
});</span></pre>
</div>
<p style="margin-left:auto;text-indent:2em;">最后来点高级的内容，如果你希望使用一个 JS 函数而不是 URL 来处理提交，可以这样：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
<pre>$('.editable').editable(<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">function</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">(value, settings) { 
    console.log(</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">this</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">);
    console.log(value);
    console.log(settings);
    </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">return</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">(value);
 }, { 
    type    : </span>'textarea'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    submit  : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
});</span></pre>
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
</div>
<p style="margin-left:auto;text-indent:2em;">处理回调：　</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
<pre>$('.editable').editable('http://www.example.com/save.php'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">, { 
    type     : </span>'textarea'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    submit   : </span>'OK'<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">,
    callback : </span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">function</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">(value, settings) {
        console.log(</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#0000ff;">this</span><span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">);
        console.log(value);
        console.log(settings);
    }
});</span></pre>
<div class="cnblogs_code_toolbar" style="background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;font-size:12px;"><span class="cnblogs_code_copy" style="font-family:'Courier New';font-size:12px;line-height:1.5;"><a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;background-color:#f5f5f5;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" title="复制代码" href="https://www.leti.ltd/archive/2012/04/28/jeditable.html"></a></span></div>
</div>
<p style="margin-left:auto;text-indent:2em;">使用附加参数：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<pre>$(".editable").editable("http://www.example.com/save.php"<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">;, {
   submitdata : {foo: </span>"bar"<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">};
});</span></pre>
</div>
<div id="highlighter_561480" class="syntaxhighlighter" style="font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-weight:normal;font-style:normal;"> </div>
<p style="margin-left:auto;text-indent:2em;">直接从URL获取显示内容：</p>
<div class="cnblogs_code" style="font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-size:12px;background-image:none;line-height:2em;text-align:left;vertical-align:baseline;font-weight:normal;font-style:normal;border:0px solid #cccccc;">
<pre>$(".editable").editable("http://www.example.com/save.php"<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">;, {
    loadurl : </span>"http://www.example.com/load.php"<span style="font-family:'Courier New';font-size:12px;line-height:1.5;color:#000000;">

});</span></pre>
</div>
<p style="margin-left:auto;text-indent:2em;">英文原文：<a style="color:#2b8dc0;font-weight:normal;line-height:2em;text-decoration:none;background-image:none;text-align:left;vertical-align:baseline;font-family:'Courier New', Consolas, 'Bitstream Vera Sans Mono', Courier, monospace;font-style:normal;font-size:12px;" href="http://www.appelsiini.net/projects/jeditable">http://www.appelsiini.net/projects/jeditable</a></p>
</div>
