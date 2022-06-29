<p style="text-indent:50px;">Spring是一个开源框架，Spring是为了解决企业级应用开发的复杂性而创建的，使用Spring可以让简单的JavaBean实现只有EJB才能完成的简单性。简单来说<strong>Spring最根本的使命：</strong><strong>简化Java开发。Spring的目标是致力于全方位的简化Java开发。</strong>那么Spring是如何简化Java开发的呢？</p>

<p><strong>1. 基于POJO的轻量级和最小侵入性编程</strong></p>

<p><strong>2.通过依赖注入（DI）和面向接口实现松耦合</strong></p>

<p><strong>3.基于切面和惯例进行声明式编程（AOP）</strong></p>

<p><strong>4.通过切面和模板减少样板</strong></p>

<p><strong>一 、基于POJO的轻量级和最小侵入性编程，<strong>激发POJO的潜能</strong></strong></p>

<p>你或许发现（或者实际用过）很多的框架通过强迫应用继承它们的类或实现它们的接口从而导致应用于框架绑死。Spring竭力避免自身的API弄乱你的应用代码，最坏的场景是一个类或许会使用Spring的注解，但它依旧是POJO，Spring赋予POJO的魔力方式之一就是通过DI（依赖注入）来装配它们。</p>

<p><strong>二、依赖注入（目的：解耦）</strong></p>

<p>依赖注入这个词从让人望而生畏，已经演变成一项复杂的编程技巧或设计模式理念。但依赖注入并不像它听上去那么复杂。在项目中应用DI，代码会变得异常简单并且更容易理解和测试（<strong>简单，易理解，易测试</strong>）。</p>

<p>任何一个有实际意义的应用都会由两个或者更多的类组成，这些类之间相互之间进行协作来完成特定的的业务逻辑。按照传统做法，每个对象负责管理与自己相互协作的的对象（即它所依赖的对象）的引用，这将会导致高度耦合和难以测试。耦合具有两面性：一方面紧密耦合的代码难以测试，难以复用、难以理解，并且典型地表现“打地鼠”式的bug特性。另一方面一定程度的耦合又是必须的。</p>

<p><img alt="" class="has" height="224" src="https://img-blog.csdnimg.cn/20181225205250932.png" width="260" /></p>

<p>通过DI，对象的依赖关系将由系统中负责协调各对象的第三方组件在创建对象的时候进行设定。对象无需自行的创建或管理它们的依赖关系。DI带来的最大的收益是——松耦合。其次是面向接口依赖的可替换（最常用的是测试的时候使用mock实现），那么在Spring中怎么实现的？创建应用组件之间的协作方式通常称为装配（wiring)。</p>

<p><strong>XML装配（在XML中显示配置）</strong></p>

<p><img alt="" class="has" height="256" src="https://img-blog.csdn.net/20180826000439898?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="978" /></p>

<p><strong>JavaConfig装配(<strong>基于Java的配置 )</strong></strong></p>

<p><img alt="" class="has" height="369" src="https://img-blog.csdn.net/20180826000509690?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="699" /></p>

<p><strong>自动化装配，</strong>Spring从两个角度实现自动化装配<strong>：</strong></p>

<p><strong>组件扫描（component scanning） ： Spring会自动发现应用上下文中所创建的bean </strong></p>

<p><strong>自动装配（autowiring） ： Spring自动满足bean之间的依赖。</strong></p>

<p> </p>

<p><img alt="" class="has" height="236" src="https://img-blog.csdn.net/20180826000857709?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="758" /></p>

<p> </p>

<p><strong>那么装配方案我们如何选择呢？</strong></p>

<p>这方面并没有唯一答案，你所做出的选择必须要适合你和你的项目。而且，Spring的配置风格是可以互相搭配的， 所以你可以选择使用XML装配一些bean，使用Spring基于Java的配置（JavaConfig）来装配另一些bean， 而将剩余的bean让Spring去自动发现。建议是尽可能地使用自动配置的机制。 显式配置越少越好。 当你必须要显式配置bean的时候（比如，有些源码不是由你来维护的，而当你需要为这些代码配置bean的时候）， 推荐使用类型安全并且比XML更加强大JavaConfig。最后，只有当你想要使用便利的XML命名空间， 并且在JavaConfig中没有同样的实现时，才应该使用XML。</p>

<p> </p>

<p><strong>注入方式：构造函数注入和属性（Setter)方法注入</strong></p>

<p>个人倾向于构造函数注入，依赖的确定性，从而减少注入的遗漏</p>

<p> </p>

<h2><strong>高级装配</strong></h2>

<h3><strong>profile</strong></h3>

<p>不同环境去切换配置</p>

<p>一种方式就是在单独的配置类（或XML文件）配置Bean,然后在构建阶段（Maven 的profiles)确定要将哪一个配置编译到可部署的应用中。这种方式的问题在于要为每种环境重新构建应用。当开发阶段迁移到QA阶段，重新构建也许算不上什么大问题。但是从QA阶段到生产阶段时，重新构建可能会引入bug并且会在QA团队的成员中带来不安情绪。</p>

<p>Spring提供的方案不需要重新构建，在Spring3.1中，Spring引入了bean Profile功能。首先要将所有不同的bean定义整理到一个或多个profile之中，在将应用部署到每个环境时，要确保对应的profile处于激活（active)的状态。以下是代码演示；</p>

<p> </p>

<h3>代码中配置</h3>

<p><img alt="" class="has" height="591" src="https://img-blog.csdn.net/20180826000926308?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="949" /></p>

<p> </p>

<p><img alt="" class="has" height="387" src="https://img-blog.csdn.net/20180826000939362?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="770" /></p>

<p><img alt="" class="has" height="399" src="https://img-blog.csdn.net/20180826000950961?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="763" /></p>

<p> </p>

<h3>Xml配置</h3>

<p><img alt="" class="has" height="267" src="https://img-blog.csdn.net/2018082600100880?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="766" /></p>

<p>激活profile,Spring在确定哪个profile处于激活状态时，需要依赖两个独立的属性:spring.profiles.active 和spring.profiles.default。如果设置了spring.profiles.active属性的话，那么它的值就会用来确定哪个是激活的。如果没有设置，则会查找spring.profiles.default。如果都未设置，那就没有激活的profile。有多种方法来设置这两个属性：</p>

<ul><li>
	<p>作为DispatcherServlet的初始化参数；</p>
	</li>
	<li>
	<p>作为Web应用的上下文参数</p>
	</li>
	<li>
	<p>作为JNDI条目</p>
	</li>
	<li>
	<p>作为环境变量；</p>
	</li>
	<li>
	<p>作为JVM的系统属性；</p>
	</li>
	<li>
	<p>在集成测试类上，使用@ActiveProfiles注解设置、</p>
	</li>
</ul><p> </p>

<h3><strong>条件化的Bean</strong></h3>

<p>一个或多个bean只有在应用的类路径下包含特定的库是才创建。或者某个bean只有当另外一个bean也声明后才会创建。或者 某一个特定的环境变量设置之后，才会创建某个bean。Spring4引入了一个新的@Conditional注解，它可以用到带有@Bean注解的方法上。如果给定的条件计算结果为true，就会创建这个bean，否则的话就个bean就会忽略。</p>

<p> </p>

<h3><strong>处理自动装配的歧义性</strong></h3>

<p>标识首选的bean @Primary</p>

<p> </p>

<p><img alt="" class="has" height="67" src="https://img-blog.csdn.net/20180826001022768?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="736" /></p>

<p> 限定自动装配的bean @Qualfier</p>

<p><img alt="" class="has" height="92" src="https://img-blog.csdn.net/20180826001038296?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="734" /></p>

<p>创建自定义的限定符号</p>

<p>  为bean设置自己的限定符，而不是依赖于将bean ID 作为限定符，在bean声明上添加 @Qualifler注解；如下图</p>

<p><img alt="" class="has" height="75" src="https://img-blog.csdn.net/20180826002145584?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="741" /></p>

<h2>bean的作用域</h2>

<p>单例（Singleton，默认的作用域）：在整个应用中，只创建bean的一个实例</p>

<p>原型（Prototype)：每次注入或者通过Spring应用上下文获取的时候，都会创建一个新的bean实例</p>

<p>会话（Session)：在Web应用中，为每个会话创建一个bean实例</p>

<p>请求（Request)：在Web应用中，为每个请求创建一个实例。</p>

<p>本文首发于个人微信公众号：webguan ；欢迎您的关注</p>

<p><img alt="" class="has" src="https://img-blog.csdn.net/20180825235533667?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" /></p>