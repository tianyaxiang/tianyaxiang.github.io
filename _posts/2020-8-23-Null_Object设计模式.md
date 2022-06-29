---
layout:     post
title:      Null_Object设计模式
subtitle:   
date:       2020-8-23
author:     Coderidea
header-style: text
catalog: true
tags:
- 设计模式
--- 
<div class="postBody">
			<div id="cnblogs_post_body" class="blogpost-body"><p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">       在设计实现中，很多地方都用到了<strong>Null Object设计模式</strong>。<strong>Null Object模式</strong>的含义在于，提供一个对象给指定的类型，用以代替这个对象为空的情况。<strong> Null Object</strong>提供了“什么也不做”的行为,隐藏来自它的合作者的细节。</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　对于如何理解和应用该模式，通过一个实例就能很好的进行说明。这一节我们在讨论消息分派器，消息分派器使用了前述的日志记录器，并且通过属性来注入具体的日志记录器对象。</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　private IEsfLogger esfLogger;</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　public IEsfLogger EsfLogger{</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　set{</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　this.esfLogger = value;</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　}</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　}</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　现在假设，我们在消息分派器内部的多个地方使用日志记录器来进行日志记录，我们总要写这样的语句：</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　if (this.esfLogger != null){</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　this.esfLogger.Log(); //记录日志</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　}</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　也就是说，在使用之前，我们都要判断一下日志记录器的引用是否为空，如果不为空才可以调用其Log方法。如果调用日志记录器进行日志记录的地方很多，那么每个地方都会充斥着这种判断其引用是否为空的代码。有没有办法来避免这所有的判断语句了，有！那就是使用Null Object设计模式。</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　为每种必要的组件都提供了对应的<strong>Null Object</strong>类型，这些类型的名字以“Empty”作为前缀。比如IEsfLogger对应的Null Object类型就是EmptyEsfLogger，EmptyEsfLogger实现的Log方法什么也不用做：</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　public void Log(string errorType ,string msg, string location, ErrorLevel level){</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　//Do Nothing !</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　}</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　有了EmptyEsfLogger，我们就可以象这样来设计消息分派器的日志记录器属性：</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　private IEsfLogger esfLogger = new EmptyEsfLogger();</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　public IEsfLogger EsfLogger{</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　set{</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　if (value != null){</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　this.esfLogger = value ?? new EmptyEsfLogger();</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　}</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　}</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　}</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　首先，将esfLogger字段的默认值设为一个Null Object。其次，当调用者每次试图将EsfLogger属性设置为null时，也将一个Null Object赋值给该字段。</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　如此一来，在消息分配器内部，我们就可以非常方便的直接使用日志记录器，而不用再判断其引用是否为空，因为无论如何，它总是指向一个有效的对象，即使这个对象是Null Object。</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　除了常见的组件装配可以使用Null Object模式外，还有一个非常适合使用<strong>Null Object模式</strong>的场合，那就是“事件”。你是否还记得，我们每次触发事件时都需要判断其是否为空，这也是非常琐碎的事情，我们仍然可以通过Null Object模式来简化它。比如某个类中定义了一个事件：</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　public event CbSimple SomeOneConnected;</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　在类的构造函数中，可以使用Null Object来初始化它：</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　this.SomeOneConnected += delegate { };</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　这样，在每次触发事件时就不用再判断其是否为null了：</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　this.SomeOneConnected(); //不用再判断是否为null，直接触发事件</span></span></p>
<div style="line-height:14px;font-size:12px;" class="spctrl"></div>
<p><span style="color:#000000;text-transform:none;text-indent:0px;letter-spacing:normal;word-spacing:0px;border-collapse:separate;" class="Apple-style-span"><span style="line-height:24px;font-family:arial, '宋体', sans-serif;font-size:14px;" class="Apple-style-span">　　灵活地使用<strong>Null Object设计模式</strong>，可以使得我们的代码更加简洁和精炼。



</span></span></p></div><div id="MySignature"></div>
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