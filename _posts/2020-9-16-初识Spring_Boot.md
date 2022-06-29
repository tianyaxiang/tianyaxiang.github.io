---
layout:     post
title:      初识Spring_Boot
subtitle:   
date:       2020-9-16
author:     coderidea
header-style: text
catalog: true
tags:
- 程序人生
- 网站设计
- 用户体验
--- 
<p><strong>Spring Boot是什么？</strong></p>

<p>Spring Boot 基于Spring，为了解决Spring框架时配置繁多、部署流程复杂、开发效率低等问题。如果说Spring 目标是简化Java开发，那么可以认为Spring Boot 框架的目标是简化Spring的开发。 Spring Boot 可以创建独立程序，内嵌了tomcat、jetty等，可以直接启动应用程序而不需要外部的容器。同时，Spring boot 可以自动配置Spring应用，并且将一些框架的依赖包整合起来，如开发web程序只需要引入web的starter，极大的简化了包引用。从Spring创建以来，Spring Boot大概是Spring领域中最令人兴奋的事情了。它在Spring之上构建了全新的开发模型，移除了开发Spring应用中乏味的内容。</p>

<p>Spring Boot提供了Spring Boot Starter、自动配置、命令行接口、Actuator四个主要特性，改变了开发Spring 应用程式的方式。</p>

<p><strong>Spring Boot Starter</strong>：它将常用的<strong>依赖分组</strong>进行了<strong>整合</strong>，将其<strong>合并</strong>到一个依赖中，这样就可以一次性添加到项目的Maven或Gradle的构建中；</p>

<p><strong>自动配置</strong>：Spring Boot的自动配置特性利用了Spring 4 对条件化配置的支持，合理的推测应用所需的bean自动化的配置它们。</p>

<p><strong>命令行接口</strong>（Commond-line interface,CLI)：Spring 的CLI发挥了Groovy编程语言的优势，并结合自动配置进一步简化Spring应用的开发；</p>

<p><strong>Actuator</strong>：它为Spring Boot应用添加了一定的管理特性。</p>

<p><strong>Spring Boot Starter（依赖的传递性）</strong></p>

<p>Spring boot Satarter将应用所需的各种依赖聚合成一项依赖。它的<strong>工作方式</strong>使<strong>用了Maven和Gradle的依赖传递方案</strong>，Starter在自己的Pom.xml文件中声明了多个依赖。当我们将某一个Starter依赖添加到Maven或Gradle构建中的时候，Starter的依赖将会自动地传递性解析。这些依赖可能会也有其他依赖。一个Starter可能会传递性地引入几十个依赖。下表列出了可用Starter</p>

<p><img alt="" class="has" height="848" src="https://img-blog.csdn.net/20180826001631883?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="572" /></p>

<p><img alt="" class="has" height="639" src="https://img-blog.csdn.net/20180826001650779?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="587" /></p>

<p> </p>

<h3><strong>自动配置</strong></h3>

<p>自动配置功能消减了Spring配置的数量，使用了约定优于配置的理念，大大的减少了Spring中的一些配置。它在实现时会考虑应用中的其他因素并推断出你所需要的Spring配置。</p>

<p>场景1：将Thymeleaf模板作为Spring MVC的视图，至少需要三个bean:ThymeleafView-Resolver,  SpringTemplateEngine,TemplateResolver。但是使用Spring Boot自动配置的话，我们需要做的仅仅是将Thymeleaf添加项目的类路径中。如果Spring Boot探测Thymeleaf位于类路径中，它将会推断出我们需要使用Thyemeleaf实现Spring Mvc的视图功能，并自动配置这些bean.</p>

<p>场景2：Spring boot Starter也会触发自动配置。在Spring Boot应用中，如果我们想要使用Spring MVC的话，所需要做的仅仅是将Web Starter作为依赖放到构建之中。将Web Starter作为依赖放到构建中以后，它会自动添加Spring MVC依赖（前面提到的依赖传递性）。如果Spring Boot 的Web 自动配置探测到Spring MVC 位于类路径下，它将会自动配置支持Spring MVC的多个bean，包括视图解析器、资源处理器以及消息 转换器等等。我们接下来需要做的就是编写处理请求的控制器。如果你之前从头配置过一个Spring MVC 项目，你会理解这带来的效率。</p>

<h3><strong>Spring Boot CLI</strong></h3>

<p>spring Boot CLI充分使用了Spring Boot Starter和自动配置的魔力，并添加一些Groovy的功能，它简化了Spring 的开发流程，通过CLI，我们能运行一个或多个Groovy脚本，并查看它是如何运行的。在应用运行过程中，CLI能够自动导入Spring类型并解析依赖。</p>

<p>有一种实践，单元测试代码通过Groovy编写，带来效率的提升。</p>

<h3><strong>Actuator</strong></h3>

<p>Spring Boot Actuator 为Spring Boot项目带来了很多有用的特性，包括</p>

<ul><li>
	<p>管理端点</p>
	</li>
	<li>
	<p>合理的异常处理以及默认的“/error"映射端点</p>
	</li>
	<li>
	<p>获取应用的”/info"端点</p>
	</li>
	<li>
	<p>当启用Spring Security时会有一个审计事件框架</p>
	</li>
</ul><p>这些特性很有用的，但Actuator最有用和最有意思的是管理端点，它开启了一扇窗，能够让我们洞悉内部的应用运行状况。</p>

<p>以上是Spring Boot的主要四个特性介绍，Spring Boot 的Starter减少了依赖列表的长度，自动配置功能则消减了Spring配置的数量。Spring Boot CLI 通过与Groovy结合带来了开发测试效率的提升。Spring Boot Actuator 则提供了一个我们能监控应用内部的运行状况的窗口。内嵌tomcat、jetty等容器，可直接启动应用程序而不需要外部的容器这些特性又为开发、调试运行和项目部署时带来巨大的便利和效率上的提升，Spring Boot 为开发，测试，部署，运维等层面带来了巨大变化，大大的简化了这些方面的复杂性，带来了效率的大幅提升，也为后面的微服务提供了基础。</p>

<p>本文首发于个人微信公众号：webguan ；欢迎您的关注</p>

<p><img alt="" class="has" src="https://img-blog.csdn.net/20180825235533667?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" /></p>