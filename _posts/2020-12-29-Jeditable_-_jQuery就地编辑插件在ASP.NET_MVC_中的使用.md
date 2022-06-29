---
layout:     post
title:      Jeditable_-_jQuery就地编辑插件在ASP.NET_MVC_中的使用
subtitle:   
date:       2020-12-29
author:     coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- 插件
--- 
<div class="postBody">
			<div id="cnblogs_post_body" class="blogpost-body"><p>    前篇文章<a id="cb_post_title_url" class="postTitle2" href="http://www.cnblogs.com/xiaoyao2011/archive/2012/04/28/jeditable.html">Jeditable - jQuery就地编辑插件使用</a>介绍了jeditable 的使用，官方例子是PHP的。我们现在实现在ASP.NET MVC 中的使用介绍。本例是ASP.NET MVC3.</p>
<h2>效果</h2>
<p>点击前</p>
<p><img src="https://pic002.cnblogs.com/images/2012/323522/2012050314310580.png" alt="" /></p>
<p>点击一文本后</p>
<p><img src="https://pic002.cnblogs.com/images/2012/323522/2012050314321369.png" alt="" /></p>
<h2>View</h2>
<p>    我们实现jeditable的一些基本用法</p>
<div class="cnblogs_code">
<pre><span style="color:#000000;">@model JQueryEditableMVC.Models.Company
@{
    Layout = null;
}

</span><span style="color:#0000ff;">&lt;!</span><span style="color:#ff00ff;">DOCTYPE html</span><span style="color:#0000ff;">&gt;</span>
<span style="color:#0000ff;">&lt;</span><span style="color:#800000;">html</span><span style="color:#0000ff;">&gt;</span>
<span style="color:#0000ff;">&lt;</span><span style="color:#800000;">head</span><span style="color:#0000ff;">&gt;</span>
    <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">title</span><span style="color:#0000ff;">&gt;</span>Details<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">title</span><span style="color:#0000ff;">&gt;</span>
    <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">script </span><span style="color:#ff0000;">src</span><span style="color:#0000ff;">="/Scripts/jquery-1.4.4.min.js"</span><span style="color:#ff0000;"> type</span><span style="color:#0000ff;">="text/javascript"</span><span style="color:#0000ff;">&gt;&lt;/</span><span style="color:#800000;">script</span><span style="color:#0000ff;">&gt;</span>
    <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">script </span><span style="color:#ff0000;">src</span><span style="color:#0000ff;">="/Scripts/jquery.jeditable.js"</span><span style="color:#ff0000;"> type</span><span style="color:#0000ff;">="text/javascript"</span><span style="color:#0000ff;">&gt;&lt;/</span><span style="color:#800000;">script</span><span style="color:#0000ff;">&gt;</span>
    <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">script </span><span style="color:#ff0000;">type</span><span style="color:#0000ff;">="text/javascript"</span><span style="color:#0000ff;">&gt;</span><span style="background-color:#f5f5f5;color:#000000;">
        $(document).ready(</span><span style="background-color:#f5f5f5;color:#0000ff;">function</span><span style="background-color:#f5f5f5;color:#000000;"> () {

            $(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">.display-label</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">).editable(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">/Company/UpdateLabel</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">);

            $(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">.text</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">).editable(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">/Company/UpdateField</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">,
                        {
                            submitdata: {
                                CompanyId: </span><span style="background-color:#f5f5f5;color:#0000ff;">function</span><span style="background-color:#f5f5f5;color:#000000;"> () {
                                    </span><span style="background-color:#f5f5f5;color:#0000ff;">return</span><span style="background-color:#f5f5f5;color:#000000;"> $(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">#CompanyId</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">).val();
                                },
                                RecordType: </span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">COMPANY</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">
                            }
                        });

            $(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">.textarea</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">).editable(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">/Company/UpdateField</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">,
                                    {
                                        type: </span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">textarea</span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        rows: </span><span style="background-color:#f5f5f5;color:#000000;">4</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        columns: </span><span style="background-color:#f5f5f5;color:#000000;">10</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        cancel: </span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">Cancel</span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        submit: </span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">OK</span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        submitdata: {
                                            CompanyId: </span><span style="background-color:#f5f5f5;color:#0000ff;">function</span><span style="background-color:#f5f5f5;color:#000000;"> () {
                                                </span><span style="background-color:#f5f5f5;color:#0000ff;">return</span><span style="background-color:#f5f5f5;color:#000000;"> $(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">#CompanyId</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">).val();
                                            },
                                            RecordType: </span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">COMPANY</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">
                                        }
                                    });

            $(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">.select</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">).editable(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">/Company/UpdateField</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">,
                                    {
                                        type: </span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">select</span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        data: </span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">{ 'Belgrade': 'Belgrade', 'Paris': 'Paris', 'London': 'London', 'Madrid': 'Madrid' }</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        submit : </span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">OK</span><span style="background-color:#f5f5f5;color:#000000;">'</span><span style="background-color:#f5f5f5;color:#000000;">,
                                        submitdata: {
                                            CompanyId: </span><span style="background-color:#f5f5f5;color:#0000ff;">function</span><span style="background-color:#f5f5f5;color:#000000;"> () {
                                                </span><span style="background-color:#f5f5f5;color:#0000ff;">return</span><span style="background-color:#f5f5f5;color:#000000;"> $(</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">#CompanyId</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">).val();
                                            },
                                            RecordType: </span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">COMPANY</span><span style="background-color:#f5f5f5;color:#000000;">"</span><span style="background-color:#f5f5f5;color:#000000;">
                                        }
                                    });
        });
    </span><span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">script</span><span style="color:#0000ff;">&gt;</span>
<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">head</span><span style="color:#0000ff;">&gt;</span>
<span style="color:#0000ff;">&lt;</span><span style="color:#800000;">body</span><span style="color:#0000ff;">&gt;</span>
    <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
        <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">h2</span><span style="color:#0000ff;">&gt;</span>Details<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">h2</span><span style="color:#0000ff;">&gt;</span>
        <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">fieldset</span><span style="color:#0000ff;">&gt;</span>
            <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">legend</span><span style="color:#0000ff;">&gt;</span>Company<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">legend</span><span style="color:#0000ff;">&gt;</span>
            <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">input </span><span style="color:#ff0000;">type</span><span style="color:#0000ff;">="hidden"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="CompanyId"</span><span style="color:#ff0000;"> value</span><span style="color:#0000ff;">="@Model.ID"</span> <span style="color:#0000ff;">/&gt;</span>
            <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="field"</span><span style="color:#0000ff;">&gt;</span>
                <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="display-label"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="lblName"</span><span style="color:#0000ff;">&gt;</span>Name<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
                <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="display-field text"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="Name"</span><span style="color:#0000ff;">&gt;</span>@Model.Name<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
            <span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>

            <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="field"</span><span style="color:#0000ff;">&gt;</span>
                <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="display-label"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="lblAddress"</span><span style="color:#0000ff;">&gt;</span>Address<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
                <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="display-field textarea"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="Address"</span><span style="color:#0000ff;">&gt;</span>@Model.Address<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
            <span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
            <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="field"</span><span style="color:#0000ff;">&gt;</span>
                <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="display-label"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="lblTown"</span><span style="color:#0000ff;">&gt;</span>Town<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
                <span style="color:#0000ff;">&lt;</span><span style="color:#800000;">div </span><span style="color:#ff0000;">class</span><span style="color:#0000ff;">="display-field select"</span><span style="color:#ff0000;"> id</span><span style="color:#0000ff;">="Country"</span><span style="color:#0000ff;">&gt;</span>@Model.Town<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
            <span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
        <span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">fieldset</span><span style="color:#0000ff;">&gt;</span>
    <span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">div</span><span style="color:#0000ff;">&gt;</span>
<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">body</span><span style="color:#0000ff;">&gt;</span>
<span style="color:#0000ff;">&lt;/</span><span style="color:#800000;">html</span><span style="color:#0000ff;">&gt;<br /></span></pre>
</div>
<h2>Model</h2>
<p>   一个简单的model</p>
<div class="cnblogs_code">
<pre><span style="color:#0000ff;">using</span><span style="color:#000000;"> System;

</span><span style="color:#0000ff;">namespace</span><span style="color:#000000;"> JQueryEditableMVC.Models
{
    </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">class</span><span style="color:#000000;"> Company
    {
        </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">int</span> ID { <span style="color:#0000ff;">get</span>; <span style="color:#0000ff;">set</span><span style="color:#000000;">; }
        </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">string</span> Name { <span style="color:#0000ff;">get</span>; <span style="color:#0000ff;">set</span><span style="color:#000000;">; }
        </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">string</span> Address { <span style="color:#0000ff;">get</span>; <span style="color:#0000ff;">set</span><span style="color:#000000;">; }
        </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">string</span> Town { <span style="color:#0000ff;">get</span>; <span style="color:#0000ff;">set</span><span style="color:#000000;">; }
    }
}</span></pre>
</div>
<h2><span>Controller</span></h2>
<div class="cnblogs_code">
<pre><span style="color:#0000ff;">using</span><span style="color:#000000;"> System;
</span><span style="color:#0000ff;">using</span><span style="color:#000000;"> System.Collections.Generic;
</span><span style="color:#0000ff;">using</span><span style="color:#000000;"> System.Linq;
</span><span style="color:#0000ff;">using</span><span style="color:#000000;"> System.Web;
</span><span style="color:#0000ff;">using</span><span style="color:#000000;"> System.Web.Mvc;
</span><span style="color:#0000ff;">using</span><span style="color:#000000;"> JQueryEditableMVC.Models;

</span><span style="color:#0000ff;">namespace</span><span style="color:#000000;"> JQueryEditableMVC.Controllers
{
    </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">class</span><span style="color:#000000;"> CompanyController : Controller
    {
        </span><span style="color:#008000;">//</span>
        <span style="color:#008000;">//</span><span style="color:#008000;"> GET: /Company/</span>

        <span style="color:#0000ff;">public</span><span style="color:#000000;"> ActionResult Details()
        {
            </span><span style="color:#0000ff;">return</span> View(<span style="color:#0000ff;">new</span><span style="color:#000000;"> Company()   {
                                            ID </span>= <span style="color:#800080;">17</span><span style="color:#000000;">,
                                            Name </span>= <span style="color:#800000;">"</span><span style="color:#800000;">Gowi</span><span style="color:#800000;">"</span><span style="color:#000000;">,
                                            Address </span>= <span style="color:#800000;">"</span><span style="color:#800000;">Maxima Gorkog 2</span><span style="color:#800000;">"</span><span style="color:#000000;">,
                                            Town </span>= <span style="color:#800000;">"</span><span style="color:#800000;">Belgrade</span><span style="color:#800000;">"</span><span style="color:#000000;">
                                        });
        }

        </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">string</span> UpdateLabel(<span style="color:#0000ff;">string</span> id, <span style="color:#0000ff;">string</span><span style="color:#000000;"> value)
        {
            </span><span style="color:#0000ff;">return</span><span style="color:#000000;"> value;
        }

        </span><span style="color:#0000ff;">public</span> <span style="color:#0000ff;">string</span> UpdateField(<span style="color:#0000ff;">string</span> id, <span style="color:#0000ff;">string</span> value, <span style="color:#0000ff;">int</span> CompanyId, <span style="color:#0000ff;">string</span><span style="color:#000000;"> RecordType)
        {
            </span><span style="color:#0000ff;">return</span><span style="color:#000000;"> value;
        }

    }
}</span></pre>
</div>


<div id="ckepop"> </div>
<div>
<p id="PSignature" style="line-height:20px;background:#FFFAEA no-repeat 2% 50%;font-size:12px;border:#e0e0e0 1px dashed;">作   者：<a href="http://www.cnblogs.com/xiaoyao2011/">孟晨</a> <br /> 出   处：<a href="http://www.cnblogs.com/xiaoyao2011/">http://www.cnblogs.com/xiaoyao2011/</a> <br />个人站:  <a href="http://www.coderidea.com/">http://www.coderidea.com/</a><br />欢迎任何形式的转载，但请务必注明出处。</p>


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