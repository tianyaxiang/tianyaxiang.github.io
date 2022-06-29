---
layout:     post
title:      jquery获取text,areatext,radio,checkbox,select值（转）
subtitle:   
date:       2020-10-2
author:     coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- 网页设计
--- 
<div class="postBody">
			<div id="cnblogs_post_body" class="blogpost-body"><div>jquery radio取值，checkbox取值，select取值，radio选中，checkbox选中，select选中，及其相关 <br />获取一组radio被选中项的值 <br />var item = $('input[@name=items][@checked]').val(); </div>
<div>
<p>Jquery 1.3以后的版本<br />var_name = $(“input[name='radio_name']:checked”).val();</p>
<p>区别是老版本有个@.</p>
<br />获取select被选中项的文本 <br />var item = $("select[@name=items] option[@selected]").text(); <br />select下拉框的第二个元素为当前选中值 <br />$('#select_id')[0].selectedIndex = 1; <br />radio单选组的第二个元素为当前选中值 <br />$('input[@name=items]').get(1).checked = true; <br /><br />获取值： <br /><br />文本框，文本区域：$("#txt").attr("value")； <br />多选框checkbox：$("#checkbox_id").attr("value")； <br />单选组radio：   $("input[@type=radio][@checked]").val(); <br />下拉框select： $('#sel').val(); <br /><br />控制表单元素： <br />文本框，文本区域：$("#txt").attr("value",'');//清空内容 <br />                 $("#txt").attr("value",'11');//填充内容 <br /><br />多选框checkbox： $("#chk1").attr("checked",'');//不打勾 <br />                 $("#chk2").attr("checked",true);//打勾 <br />                 if($("#chk1").attr('checked')==undefined) //判断是否已经打勾 <br /><br />单选组radio：    $("input[@type=radio]").attr("checked",'2');//设置value=2的项目为当前选中项 <br />下拉框select：   $("#sel").attr("value",'-sel3');//设置value=-sel3的项目为当前选中项 <br />                $("&lt;option value='1'&gt;1111&lt;/option&gt;&lt;option value='2'&gt;2222&lt;/option&gt;").appendTo("#sel")//添加下拉框的option <br />                $("#sel").empty()；//清空下拉框</div>
<p>----------------------------------------------------------------------------------------------------</p>
<p> </p>
<p>//遍历option和添加、移除option<br />function changeShipMethod(shipping){<br />var len = $("select[@name=ISHIPTYPE] option").length<br />if(shipping.value != "CA"){<br />$("select[@name=ISHIPTYPE] option").each(function(){<br />if($(this).val() == 111){<br />$(this).remove();<br />}<br />});<br />}else{<br />$("&lt;option value='111'&gt;UPS Ground&lt;/option&gt;").appendTo($("select[@name=ISHIPTYPE]"));<br />}<br />}</p>
<p><br />//取得下拉選單的選取值</p>
<p>$(#testSelect option:selected').text();<br />或$("#testSelect").find('option:selected').text();<br />或$("#testSelect").val();<br />//////////////////////////////////////////////////////////////////<br />记性不好的可以收藏下：<br />1,下拉框:</p>
<p>var cc1 = $(".formc select[@name='country'] option[@selected]").text(); //得到下拉菜单的选中项的文本(注意中间有空格)<br />var cc2 = $('.formc select[@name="country"]').val(); //得到下拉菜单的选中项的值<br />var cc3 = $('.formc select[@name="country"]').attr("id"); //得到下拉菜单的选中项的ID属性值<br />$("#select").empty();//清空下拉框//$("#select").html('');<br />$("&lt;option value='1'&gt;1111&lt;/option&gt;").appendTo("#select")//添加下拉框的option</p>
<p>稍微解释一下:<br />1.select[@name='country'] option[@selected] 表示具有name 属性，<br />并且该属性值为'country' 的select元素 里面的具有selected 属性的option 元素；<br />可以看出有@开头的就表示后面跟的是属性。</p>
<p>2,单选框:<br />$("input[@type=radio][@checked]").val(); //得到单选框的选中项的值(注意中间没有空格)<br />$("input[@type=radio][@value=2]").attr("checked",'checked'); //设置单选框value=2的为选中状态.(注意中间没有空格)</p>
<p>3,复选框:<br />$("input[@type=checkbox][@checked]").val(); //得到复选框的选中的第一项的值<br />$("input[@type=checkbox][@checked]").each(function(){ //由于复选框一般选中的是多个,所以可以循环输出<br />alert($(this).val());<br />});</p>
<p>$("#chk1").attr("checked",'');//不打勾<br />$("#chk2").attr("checked",true);//打勾<br />if($("#chk1").attr('checked')==undefined){} //判断是否已经打勾</p>
<p><br />当然jquery的选择器是强大的. 还有很多方法.</p>
<p>&lt;script src="jquery-1.2.1.js" type="text/javascript"&gt;&lt;/script&gt;<br />&lt;script language="javascript" type="text/javascript"&gt;<br />$(document).ready(function(){<br />$("#selectTest").change(function()<br />{<br />//alert("Hello");<br />//alert($("#selectTest").attr("name"));<br />//$("a").attr("href","xx.html");<br />//window.location.href="xx.html";<br />//alert($("#selectTest").val());<br />alert($("#selectTest option[@selected]").text());<br />$("#selectTest").attr("value", "2");</p>
<p>});<br />});<br />&lt;/script&gt;</p>
<p><br />&lt;a href="#"&gt;aaass&lt;/a&gt;</p>
<p>&lt;!--下拉框--&gt;<br />&lt;select id="selectTest" name="selectTest"&gt;<br />&lt;option value="1"&gt;11&lt;/option&gt;<br />&lt;option value="2"&gt;22&lt;/option&gt;<br />&lt;option value="3"&gt;33&lt;/option&gt;<br />&lt;option value="4"&gt;44&lt;/option&gt;<br />&lt;option value="5"&gt;55&lt;/option&gt;<br />&lt;option value="6"&gt;66&lt;/option&gt;<br />&lt;/select&gt;<br />jquery radio取值，checkbox取值，select取值，radio选中，checkbox选中，select选中，及其相关获取一组radio被选中项的值<br />var item = $('input[@name=items][@checked]').val();<br />获取select被选中项的文本<br />var item = $("select[@name=items] option[@selected]").text();<br />select下拉框的第二个元素为当前选中值<br />$('#select_id')[0].selectedIndex = 1;<br />radio单选组的第二个元素为当前选中值<br />$('input[@name=items]').get(1).checked = true;<br />获取值：<br />文本框，文本区域：$("#txt").attr("value")；<br />多选框checkbox：$("#checkbox_id").attr("value")；<br />单选组radio： $("input[@type=radio][@checked]").val();<br />下拉框select： $('#sel').val();<br />控制表单元素：<br />文本框，文本区域：$("#txt").attr("value",'');//清空内容<br />$("#txt").attr("value",'11');//填充内容<br />多选框checkbox： $("#chk1").attr("checked",'');//不打勾<br />$("#chk2").attr("checked",true);//打勾<br />if($("#chk1").attr('checked')==undefined) //判断是否已经打勾<br />单选组radio： $("input[@type=radio]").attr("checked",'2');//设置value=2的项目为当前选中项<br />下拉框select： $("#sel").attr("value",'-sel3');//设置value=-sel3的项目为当前选中项<br />$("&lt;optionvalue='1'&gt;1111&lt;/option&gt;&lt;optionvalue='2'&gt;2222&lt;/option&gt;").appendTo("#sel")//添加下拉框的option<br />$("#sel").empty()；//清空下拉框</p>
<p>获取一组radio被选中项的值<br />var item = $('input[@name=items][@checked]').val();<br />获取select被选中项的文本<br />var item = $("select[@name=items] option[@selected]").text();<br />select下拉框的第二个元素为当前选中值<br />$('#select_id')[0].selectedIndex = 1;<br />radio单选组的第二个元素为当前选中值<br />$('input[@name=items]').get(1).checked = true;<br />获取值：<br />文本框，文本区域：$("#txt").attr("value")；<br />多选框checkbox：$("#checkbox_id").attr("value")；<br />单选组radio： $("input[@type=radio][@checked]").val();<br />下拉框select： $('#sel').val();<br />控制表单元素：<br />文本框，文本区域：$("#txt").attr("value",'');//清空内容<br />$("#txt").attr("value",'11');//填充内容<br />多选框checkbox： $("#chk1").attr("checked",'');//不打勾<br />$("#chk2").attr("checked",true);//打勾<br />if($("#chk1").attr('checked')==undefined) //判断是否已经打勾<br />单选组radio： $("input[@type=radio]").attr("checked",'2');//设置value=2的项目为当前选中项<br />下拉框select： $("#sel").attr("value",'-sel3');//设置value=-sel3的项目为当前选中项<br />$("&lt;option value='1'&gt;1111&lt;/option&gt;&lt;option value='2'&gt;2222&lt;/option&gt;").appendTo("#sel")//添加下拉框的option<br />$("#sel").empty()；//清空下拉框</p></div><div id="MySignature"></div>
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