---
layout:     post
title:      C＃中的参数传递：值类型（value_type）和引用类型（reference_type）
subtitle:   
date:       2020-3-21
author:     coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- 工具
--- 
<div class="postBody">
			<div id="cnblogs_post_body" class="blogpost-body"><p><span class="Apple-style-span" style="color:#542d24;font-family:Arial;font-size:14px;line-height:normal;">摘要：<br style="line-height:normal;" />由于在.NET中存在两种类型，分别是值类型（value type）和引用类型（reference type），所以很多关于C#中<strong style="line-height:normal;">参数</strong><strong style="line-height:normal;">传递</strong>的混淆就因此而生。本文首先从值类型和引用类型的辨析入手，然后解释了在C#中的<strong style="line-height:normal;">参数</strong><strong style="line-height:normal;">传递</strong>的四种形式：值<strong style="line-height:normal;">传递</strong>（默认形式）、ref<strong style="line-height:normal;">传递</strong>、out<strong style="line-height:normal;">传递</strong>、params<strong style="line-height:normal;">传递</strong>。</span></p>
<div style="font-family:Arial;font-size:14px;line-height:normal;">
<p style="line-height:normal;">首先要弄清楚的是：值类型是分配在栈（stack）上面，而引用类型分配在堆（heap）上面。栈是一种先进后出，并且由系统自动操作的存储空间。而堆（在.NET上准确的说是托管堆 Managed Heap）是一种自由储存区（Free Memory），在该区域中，必须明确的为对象申请存储空间（一般在Java和<strong style="line-height:normal;">C</strong>＃中都是使用的new关键字），并可以在使用完以后释放申请的存储空间（Java和<strong style="line-height:normal;">C</strong>＃都使用垃圾回收机制 Garbage Collector自动释放对象空间）</p>
<p style="line-height:normal;"><strong style="line-height:normal;">引用类型（reference type）：它存放的值是指向数据的引用（reference），而不是数据本身。</strong>示例：</p>
<p style="line-height:normal;">System.Text.StringBuilder sb = new StringBuilder();</p>
<p style="line-height:normal;">这里，我们声明一个变量sb，并通过new StringBuilder()创建了一个StringBuilder（与Java中StringBuffer类似）对象，再将对象的引用 （reference）赋值给变量sb，即变量sb中保存的是StringBuilder对象的引用，而非对象本身。</p>
<p align="left" style="line-height:normal;">System.Text.StringBuilder first = new StringBuilder();</p>
<p align="left" style="line-height:normal;">System.Text.StringBuilder second = first;</p>
<p style="line-height:normal;">这里，我们将变量first的值（对一个StringBuilder对象的引用）赋值给变量second，即first和second都指向同一个StringBuilder对象。对StringBuilder对象的任何修改都会影响到first和second变量。</p>
<p align="left" style="line-height:normal;">System.Text.StringBuilder first = new StringBuilder();</p>
<p align="left" style="line-height:normal;">System.Text.StringBuilder second = first;</p>
<p align="left" style="line-height:normal;">first.Append("hello");</p>
<p align="left" style="line-height:normal;">first = null;</p>
<p align="left" style="line-height:normal;">Console.WriteLine(second);</p>
<p style="line-height:normal;"></p>
<p style="line-height:normal;">这里，输出的结果是 hello。由于first和second都含有对同一StringBuilder对象的引用。然后通过first的引用调用StringBuilder 对象的Append方法，将对象进行修改，即添加字符串“hello”，然后又将first赋值为null，表示让first不引用任何对象。最后通过 second的引用隐式调用StringBuilder对象的ToString方法输出“hello”。由此可见，first的值改变了（被赋值为 null），而它所引用的对象并不会发生改变，second照样引用到StringBuilder对象。</p>
<p style="line-height:normal;"></p>
<p style="line-height:normal;"><strong style="line-height:normal;"><span style="line-height:normal;text-decoration:underline;">class类型，interface类型，delegate类型和array类型都是引用类型。</span></strong></p>
<p style="line-height:normal;"></p>
<p style="line-height:normal;">值类型（value type）：引用类型中变量和实际数据之间还隔了一间接层，而值类型就完全不存在，<strong style="line-height:normal;"><span style="line-height:normal;text-decoration:underline;">值类型的变量直接保存的就是数据。</span></strong></p>
<p style="line-height:normal;"></p>
<p align="left" style="line-height:normal;">struct IntHolder</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">public int i;</p>
<p style="line-height:normal;">}</p>
<p style="line-height:normal;">这里，结构是值类型，IntHolder是一个结构：</p>
<p align="left" style="line-height:normal;">IntHolder first = new IntHolder();</p>
<p align="left" style="line-height:normal;">first.i = 5;</p>
<p align="left" style="line-height:normal;">IntHolder second = first;</p>
<p align="left" style="line-height:normal;">first.i = 6;</p>
<p style="line-height:normal;">Console.WriteLine(second.i);</p>
<p style="line-height:normal;">输出结果为5。这里second ＝ first 以后second保存的是first的值拷贝，即second.i = 5；而后来的first.i发生了改变并不会影响second.i。所以输出值为5。</p>
<p style="line-height:normal;"><span style="line-height:normal;text-decoration:underline;"><strong style="line-height:normal;">简单类型（比如int,double,char），enum类型，struct类型都是值类型。</strong></span></p>
<p style="line-height:normal;"><span style="line-height:normal;text-decoration:underline;"><strong style="line-height:normal;">注意：有一些类型（比如string类型）的行为看起来像值类 型，但实际上是引用类型。这些类型被称为immutable类型，也就是说这种类型的实例只要被构造好就不会改变。比 如，string.Replace()并不会改变调用它的字符串对象，而是返回含有新数据的新的字符串对象。</strong></span></p>
<p style="line-height:normal;">一、值<strong style="line-height:normal;">参数</strong>（Value parameters）：</p>
<p style="line-height:normal;"><span style="line-height:normal;text-decoration:underline;"><strong style="line-height:normal;">默认情况下，参数都是值参数。</strong></span></p>
<p align="left" style="line-height:normal;">void Foo (StringBuilder x)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">x = null;</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">...</p>
<p align="left" style="line-height:normal;">StringBuilder y = new StringBuilder();</p>
<p align="left" style="line-height:normal;">y.Append ("hello");</p>
<p align="left" style="line-height:normal;">Foo (y);</p>
<p style="line-height:normal;">Console.WriteLine (y==null);</p>
<p style="line-height:normal;">输出结果为False。这里由于是值<strong style="line-height:normal;">传递</strong>形式，所以尽管x被设置为null，但是y的值不会改变。但要注意的是，<span style="line-height:normal;text-decoration:underline;"><strong style="line-height:normal;">引用类型变量保存的是引用，如果两个引用类型变量引用到相同的对象，那么对对象进行修改势必影响到两个引用类型变量</strong></span>，如下：</p>
<p align="left" style="line-height:normal;">void Foo (StringBuilder x)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">x.Append (" world");</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">...</p>
<p align="left" style="line-height:normal;">StringBuilder y = new StringBuilder();</p>
<p align="left" style="line-height:normal;">y.Append ("hello");</p>
<p align="left" style="line-height:normal;">Foo (y);</p>
<p style="line-height:normal;">Console.WriteLine (y);</p>
<p style="line-height:normal;">输出结果为hello world。因为在调用Foo方法以后，y所引用到的StringBuilder对象的内容被修改为“hello world”了，这是通过Foo方法中的x引用调用Append方法添加“ world”实现的。</p>
<p style="line-height:normal;">现在考虑一下通过值类型做值<strong style="line-height:normal;">参数</strong>的情况：</p>
<p align="left" style="line-height:normal;">void Foo (IntHolder x)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">x.i=10;</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">...</p>
<p align="left" style="line-height:normal;">IntHolder y = new IntHolder();</p>
<p align="left" style="line-height:normal;">y.i=5;</p>
<p align="left" style="line-height:normal;">Foo (y);</p>
<p align="left" style="line-height:normal;">Console.WriteLine (y.i);</p>
<p style="line-height:normal;">输出结果为5。如果将IntHolder的struct类型改为class类型，则输出结果变为10。这好理解，<span style="line-height:normal;text-decoration:underline;"><strong style="line-height:normal;">前者struct是值类型，传递的是值本身；后者class是引用类型，以传值形式传递的object reference（对象引用）</strong></span>。</p>
<p style="line-height:normal;">二、引用<strong style="line-height:normal;">参数</strong>（Reference parameters）：</p>
<p style="line-height:normal;">引用<strong style="line-height:normal;">参数</strong>不<strong style="line-height:normal;">传递</strong>在函数成员调用中的变量的值，而是<span style="line-height:normal;text-decoration:underline;"><strong style="line-height:normal;">传递变量本身</strong></span>。这就意味着它并不会为函数成员声明中的变量分配新的内存空间，而是使用与实参相同的存储空间，所以实参和形参的值无论什么时候都是一样的。要在C#中使用引用<strong style="line-height:normal;">参数</strong>，必须在函数声明以及函数调用中都明确地使用关键字ref，这样一看代码就很清楚知道是使用引用<strong style="line-height:normal;">参数</strong>了。</p>
<p align="left" style="line-height:normal;">void Foo (ref StringBuilder x)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">x = null;</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">...</p>
<p align="left" style="line-height:normal;">StringBuilder y = new StringBuilder();</p>
<p align="left" style="line-height:normal;">y.Append ("hello");</p>
<p align="left" style="line-height:normal;">Foo (ref y);</p>
<p align="left" style="line-height:normal;">Console.WriteLine (y==null);</p>
<p style="line-height:normal;">输出结果为True。这里使用引用<strong style="line-height:normal;">参数</strong>，<strong style="line-height:normal;">传递</strong>的是对y的引用（reference），而不是y中的值（object reference）。所以形参x值的改变马上就反映到y上。在Foo方法调用以后，y的值也为null。</p>
<p style="line-height:normal;">考虑一下使用struct值类型的情况：</p>
<p align="left" style="line-height:normal;">void Foo (ref IntHolder x)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">x.i=10;</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">...</p>
<p align="left" style="line-height:normal;">IntHolder y = new IntHolder();</p>
<p align="left" style="line-height:normal;">y.i=5;</p>
<p align="left" style="line-height:normal;">Foo (ref y);</p>
<p style="line-height:normal;">Console.WriteLine (y.i);</p>
<p style="line-height:normal;">输出结果为10。其中两个变量都共享的是同一个存储空间，对x的改变同样影响到y。</p>
<p style="line-height:normal;">三、输出<strong style="line-height:normal;">参数</strong>（Output parameters）：</p>
<p style="line-height:normal;">输出<strong style="line-height:normal;">参数</strong>与引用<strong style="line-height:normal;">参数</strong>非常相似，除了使用关键字out以外，它们的不同点在于ref修饰的形式<strong style="line-height:normal;">参数</strong>可以不被赋值，而out修饰的形式<strong style="line-height:normal;">参数</strong>必须被赋值。因此，使用输出<strong style="line-height:normal;">参数</strong>的实参可以在调用之前不被初始化。</p>
<p align="left" style="line-height:normal;">void Foo (out int x)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">// Can't read x here - it's considered unassigned</p>
<p align="left" style="line-height:normal;">// Assignment - this must happen before the method can complete normally</p>
<p align="left" style="line-height:normal;">x = 10;</p>
<p align="left" style="line-height:normal;">// The value of x can now be read:</p>
<p align="left" style="line-height:normal;">int a = x;</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">...</p>
<p align="left" style="line-height:normal;">// Declare a variable but don't assign a value to it</p>
<p align="left" style="line-height:normal;">int y;</p>
<p align="left" style="line-height:normal;">// Pass it in as an output parameter, even though its value is unassigned</p>
<p align="left" style="line-height:normal;">Foo (out y);</p>
<p align="left" style="line-height:normal;">// It's now assigned a value, so we can write it out:</p>
<p align="left" style="line-height:normal;">Console.WriteLine (y);</p>
<p style="line-height:normal;"></p>
<p style="line-height:normal;"></p>
<p style="line-height:normal;">四、<strong style="line-height:normal;">参数</strong>数组（Parameter arrays）：</p>
<p style="line-height:normal;">用params修饰的一维数组为<strong style="line-height:normal;">参数</strong>数组。它可以接收可变数目的实参。<strong style="line-height:normal;">C</strong>/C++程序员可以认为params等同于类型安全的stdarg.h头文件中varargs宏。</p>
<p align="left" style="line-height:normal;">void ShowNumbers (params int[] numbers)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">foreach (int x in numbers)</p>
<p align="left" style="line-height:normal;">{</p>
<p align="left" style="line-height:normal;">Console.Write (x+" ");</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">Console.WriteLine();</p>
<p align="left" style="line-height:normal;">}</p>
<p align="left" style="line-height:normal;">...</p>
<p align="left" style="line-height:normal;">int[] x = {1, 2, 3};</p>
<p align="left" style="line-height:normal;">ShowNumbers (x);</p>
<p style="line-height:normal;">ShowNumbers (4, 5);</p>
<p style="line-height:normal;">输出结果为：</p>
<p style="line-height:normal;">1 2 3</p>
<p style="line-height:normal;">4 5</p>
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