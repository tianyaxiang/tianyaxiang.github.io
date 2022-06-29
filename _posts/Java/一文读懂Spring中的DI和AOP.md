<p id="main-toc"><strong>目录</strong></p>

<p id="%E5%89%8D%E8%A8%80-toc" style="margin-left:0px;"><a href="#%E5%89%8D%E8%A8%80">前言</a></p>

<p id="%E4%B8%80%C2%A0DI-toc" style="margin-left:0px;"><a href="#%E4%B8%80%C2%A0DI">一 DI</a></p>

<p id="DI%EF%BC%88%E4%BE%9D%E8%B5%96%E6%B3%A8%E5%85%A5%EF%BC%89%E5%AE%9A%E4%B9%89-toc" style="margin-left:40px;"><a href="#DI%EF%BC%88%E4%BE%9D%E8%B5%96%E6%B3%A8%E5%85%A5%EF%BC%89%E5%AE%9A%E4%B9%89">DI（依赖注入）定义</a></p>

<p id="%E8%83%8C%E6%99%AF%E5%92%8C%E9%97%AE%E9%A2%98-toc" style="margin-left:40px;"><a href="#%E8%83%8C%E6%99%AF%E5%92%8C%E9%97%AE%E9%A2%98">背景和问题</a></p>

<p id="%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88-toc" style="margin-left:40px;"><a href="#%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88">解决方案</a></p>

<p id="Spring%C2%A0%E7%9A%84%E8%A3%85%E9%85%8D%E6%96%B9%E5%BC%8F-toc" style="margin-left:40px;"><a href="#Spring%C2%A0%E7%9A%84%E8%A3%85%E9%85%8D%E6%96%B9%E5%BC%8F">Spring 的装配方式</a></p>

<p id="XML%E8%A3%85%E9%85%8D%EF%BC%88%E5%9C%A8XML%E4%B8%AD%E6%98%BE%E7%A4%BA%E9%85%8D%E7%BD%AE%EF%BC%89-toc" style="margin-left:80px;"><a href="#XML%E8%A3%85%E9%85%8D%EF%BC%88%E5%9C%A8XML%E4%B8%AD%E6%98%BE%E7%A4%BA%E9%85%8D%E7%BD%AE%EF%BC%89">XML装配（在XML中显示配置）</a></p>

<p id="JavaConfig%E8%A3%85%E9%85%8D(%E5%9F%BA%E4%BA%8EJava%E7%9A%84%E9%85%8D%E7%BD%AE%C2%A0)-toc" style="margin-left:80px;"><a href="#JavaConfig%E8%A3%85%E9%85%8D(%E5%9F%BA%E4%BA%8EJava%E7%9A%84%E9%85%8D%E7%BD%AE%C2%A0)">JavaConfig装配(基于Java的配置 )</a></p>

<p id="%E8%87%AA%E5%8A%A8%E5%8C%96%E8%A3%85%E9%85%8D-toc" style="margin-left:80px;"><a href="#%E8%87%AA%E5%8A%A8%E5%8C%96%E8%A3%85%E9%85%8D">自动化装配</a></p>

<p id="Spring%E4%BB%8E%E4%B8%A4%E4%B8%AA%E8%A7%92%E5%BA%A6%E5%AE%9E%E7%8E%B0%E8%87%AA%E5%8A%A8%E5%8C%96%E8%A3%85%E9%85%8D%EF%BC%9A-toc" style="margin-left:80px;"><a href="#Spring%E4%BB%8E%E4%B8%A4%E4%B8%AA%E8%A7%92%E5%BA%A6%E5%AE%9E%E7%8E%B0%E8%87%AA%E5%8A%A8%E5%8C%96%E8%A3%85%E9%85%8D%EF%BC%9A">Spring从两个角度实现自动化装配：</a></p>

<p id="%E4%BA%8C%E3%80%81AOP-toc" style="margin-left:0px;"><a href="#%E4%BA%8C%E3%80%81AOP">二、AOP</a></p>

<p id="AOP%E7%9A%84%E5%AE%9A%E4%B9%89-toc" style="margin-left:40px;"><a href="#AOP%E7%9A%84%E5%AE%9A%E4%B9%89">AOP的定义</a></p>

<p style="margin-left:40px;"><a href="#%E8%83%8C%E6%99%AF%E5%92%8C%E9%97%AE%E9%A2%98">背景和问题</a></p>

<p style="margin-left:40px;"><a href="#%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88">解决方案</a></p>

<p id="AOP%E6%9C%AF%E8%AF%AD-toc" style="margin-left:40px;"><a href="#AOP%E6%9C%AF%E8%AF%AD">AOP术语</a></p>

<p id="%E9%80%9A%E7%9F%A5%EF%BC%88advice)-toc" style="margin-left:80px;"><a href="#%E9%80%9A%E7%9F%A5%EF%BC%88advice)">通知（advice)</a></p>

<p id="Spring%C2%A0%E5%AF%B9AOP%E7%9A%84%E6%94%AF%E6%8C%81-toc" style="margin-left:80px;"><a href="#Spring%C2%A0%E5%AF%B9AOP%E7%9A%84%E6%94%AF%E6%8C%81">Spring 对AOP的支持</a></p>

<p id="%E6%80%BB%E7%BB%93-toc" style="margin-left:0px;"><a href="#%E6%80%BB%E7%BB%93">总结</a></p>

<hr id="hr-toc" /><h1 id="%E5%89%8D%E8%A8%80">前言</h1>

<p>Spring框架通过POJO最小侵入性编程、DI、AOP、<strong>模板代码手段来</strong>简化了Java 开发，简化了企业应用的开发。POJO和模板代码相对来说好理解，本篇重点解读下DI和AOP。</p>

<h1 id="%E4%B8%80%C2%A0DI"><strong>一 DI</strong></h1>

<h2 id="DI%EF%BC%88%E4%BE%9D%E8%B5%96%E6%B3%A8%E5%85%A5%EF%BC%89%E5%AE%9A%E4%B9%89"><strong>DI（依赖注入）定义</strong></h2>

<p>对象的依赖关系将由系统中负责协调各对象的第三方组件在创建对象的时候进行设定。对象无需自行的创建或管理它们的依赖关系。</p>

<h2 id="%E8%83%8C%E6%99%AF%E5%92%8C%E9%97%AE%E9%A2%98"><strong>背景和问题</strong></h2>

<p>我们行来假设没有Spring 来管理注入依赖关系，我们是怎么来实现依赖关系管理的，直接在对象内部通过new进行创建对象，每个对象负责管理与自己相互协作的的对象（即它所依赖的对象）的引用，是程序主动去创建依赖对象。下面的一段代码是在没有用Spring 来实现DI的情况下，我们是怎么做的，这样做的问题在哪？</p>

<p>1.高度的耦合，RecognitionServiceImpl 和ContractRepository 两者耦合在一起。</p>

<p>2.难以测试，如果我们想测试RecognitionService，在不改代码下很难来测试。</p>

<pre>
<code class="language-java">public class RecognitionServiceImpl implements RecognitionService {
    ContractRepository contractRepository = new ContractRepository();
}
</code></pre>

<h2 id="%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88"><strong>解决方案</strong></h2>

<p>通过DI，对象的依赖关系将由系统中负责协调各对象的第三方组件在创建对象的时候进行设定。对象无需自行的创建或管理它们的依赖关系。DI带来的最大的收益是——松耦合。其次是面向接口依赖的可替换（常用的是测试的时候使用mock实现）</p>

<p>在Spring 框架中怎么来实现DI呢？</p>

<p>在Spring中创建应用组件之间的协作方式通常称为装配（wiring)。它提供了三种装配实现方式，分别是XML装配、JavaConfig装配、自动装配。</p>

<h2 id="Spring%C2%A0%E7%9A%84%E8%A3%85%E9%85%8D%E6%96%B9%E5%BC%8F">Spring 的装配方式</h2>

<h3 id="XML%E8%A3%85%E9%85%8D%EF%BC%88%E5%9C%A8XML%E4%B8%AD%E6%98%BE%E7%A4%BA%E9%85%8D%E7%BD%AE%EF%BC%89"><strong>XML装配（在XML中显示配置）</strong></h3>

<p><img alt="" class="has" height="256" src="https://img-blog.csdn.net/20180826000439898?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="978" /></p>

<h3 id="JavaConfig%E8%A3%85%E9%85%8D(%E5%9F%BA%E4%BA%8EJava%E7%9A%84%E9%85%8D%E7%BD%AE%C2%A0)"><strong>JavaConfig装配(<strong>基于Java的配置 )</strong></strong></h3>

<p><img alt="" class="has" height="369" src="https://img-blog.csdn.net/20180826000509690?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="699" /></p>

<h3 id="%E8%87%AA%E5%8A%A8%E5%8C%96%E8%A3%85%E9%85%8D"><strong>自动化装配</strong></h3>

<h3 id="Spring%E4%BB%8E%E4%B8%A4%E4%B8%AA%E8%A7%92%E5%BA%A6%E5%AE%9E%E7%8E%B0%E8%87%AA%E5%8A%A8%E5%8C%96%E8%A3%85%E9%85%8D%EF%BC%9A">Spring从两个角度实现自动化装配<strong>：</strong></h3>

<p><strong>组件扫描（component scanning） ： Spring会自动发现应用上下文中所创建的bean </strong></p>

<p><strong>自动装配（autowiring） ： Spring自动满足bean之间的依赖。</strong></p>

<p> </p>

<p><img alt="" class="has" height="236" src="https://img-blog.csdn.net/20180826000857709?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3RpYW55YXhpYW5n/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" width="758" /></p>

<p><strong>简单来说，DI目的只有一个就是解耦，实现代码的松散耦合。高耦合的代码不易测试、不易复用。</strong></p>

<p> </p>

<h1 id="%E4%BA%8C%E3%80%81AOP"><strong>二、AOP</strong></h1>

<h2 id="AOP%E7%9A%84%E5%AE%9A%E4%B9%89"><strong>AOP的定义</strong></h2>

<p>AOP，面向切面编程，通过预编译方式和运行期间动态代理实现程序功能的统一维护的一种技术。AOP是OOP的延续，是Spring框架中的一个重要内容，是函数式编程的一种衍生范型。利用AOP可以对业务逻辑外的各个部分进行隔离，从而使得业务逻辑各部分之间的耦合度降低，提高程序的可重用性，同时提高了开发的效率。是不是有点不太好理解。我们先有个概念上的认识，就是面向切面编程。所谓切面，横切关注点模块化为特殊的类，这些类被称为切面。</p>

<h2><strong>背景和问题</strong></h2>

<p>理解AOP最关键的点是先理解<strong>横切关注点</strong>，所谓的横切关注点是指散布于应用中的多处功能。最典型的横切关注点有日志记录、性能统计、安全控制、事务处理、异常处理、缓存等。这些横切的关注点从概念上与应用的业务逻辑相分离的（但是往往会直接嵌入到应用的业务逻辑中去）。没有AOP，我们往往会把这些横切的关注点来直接嵌入到业务逻辑中去，这样做的一个问题是什么？一是分散在多处，就是这类的代码分散在多处代码中，重复出现。二是 与业务代码耦合在一起。<strong>把这些横切关注点与业务逻辑相分离，解耦是面向切面编程（AOP）要解决的问题。</strong></p>

<h2><strong>解决方案</strong></h2>

<p>通过AOP 来解决横切关注点与业务逻辑相分离解耦。横切关注点要以描述为影响多处的功能，例如：安全就是一个横切关注点，应用中的许多方法都会涉及到安全规则，事务也是一个横切关注点，应用在很多方法中。</p>

<p>横切关注点可以被模块化为特殊的类，这些类被成为切面（aspect）。切面有两个好处，一是每个关注点都集中于一个地方，二服务模块更加的简洁，只需主要关注于业务逻辑，像安全，事务等次要的关注点被转移到了切面中。</p>

<h2 id="AOP%E6%9C%AF%E8%AF%AD">AOP术语</h2>

<p>AOP已经有了自己的一些术语。描述切面的常用术语有通知（advice）、切点（point)、和连接点。</p>

<h3 id="%E9%80%9A%E7%9F%A5%EF%BC%88advice)">通知（advice)</h3>

<p>在aop 术语中，切面的工作被成为通知。通知定义了切面是什么以及何时使用。通知有两个功能，一个是描述切面要做什么？另一个是何时做。简单来说是在某个方法被调用之前执行，还是之后执行，还是之前之后都要执行，还是只在方法抛出异常是执行。</p>

<p><strong>Spring 切面可以应用5种类型的通知。</strong></p>

<ol><li>前置通知（Before):在目标方法被调用之前调用通知功能。</li>
	<li>后置通知（After):在目标方法完成之后调用通知，此时不关心方法的输出是什么。</li>
	<li>返回通知（After-returning)：在目标方法成功执行之后调用通知。</li>
	<li>异常通知（After-throwing)：在目标方法抛出异常后调用。</li>
	<li>环境通知（Around）：通知包裹了被通知的方法，在被通知的方法调用之前和调用之后执行自定义的行为。</li>
</ol><p><strong>连接点（Join Point)</strong></p>

<p>应用有很多的时机去应用（调用通知），这些时机被称为连接点。连接点是应用执行过程中能够插入切面的一个点。这个点可以是调用方法时，抛出异常时，甚至是修改一个字段时。切面代码可以利用这些点插入到应用的正常流程之中，并添加新的行为。</p>

<p><strong>切点（Poincut)</strong></p>

<p>如果通知定义了切面的”什么（what)“和”何时（when)" 的话，那么切点就定义了“何出（where)"。切点的定义会匹配要织入的一个或多个连接点。通常使用明确的类和方法名称，或者是利用正则表达式来定义所匹配的类和方法名来指定切点。</p>

<p><strong>切面（Aspect)</strong></p>

<p><strong>切面是通知和切点的结合，通知和切点来定义了切面的全部内容，它是什么，在何时何处完成其功能。</strong></p>

<p><strong>引入（Introduction)</strong></p>

<p>引入允许向现有的类添加新方法和属性。</p>

<p><strong>织入（Weaving)</strong></p>

<p><strong>织入是把切面应用到目标对象并创建新的代理对象的过程。</strong>切面在指定的连接点被织入到目标对象中。在目标对象的生命周期中有多个点可以织入。编译期（AspectJ)，类加载期(AspectJ5 支持），运行期（Spring Aop 以这种方式织入切面的）。</p>

<p><strong>总结一下：通知包含了需要应用多个应用对象的横切行为；连接点是程序执行过程中能够应用通知的所有点；切点定义了通知被应用的具体位置(即哪些连接点）。简而言之：<span style="color:#f33b45;">切点定义了哪些连接点会得到通知。</span></strong></p>

<h3 id="Spring%C2%A0%E5%AF%B9AOP%E7%9A%84%E6%94%AF%E6%8C%81">Spring 对AOP的支持</h3>

<p>创建切点来定义切面所织入的连接点是AOP框架的基本功能。</p>

<p>Spring 提供了4种AOP的支持。</p>

<ol><li>基于代理的经典Spring Aop</li>
	<li>纯POJO切面</li>
	<li>@AspectJ 注解驱动的切面</li>
	<li>注入式AspectJ 切面（适用于Spring 各版本）</li>
</ol><p>前三种都是Spring Aop 的变体，<span style="color:#f33b45;"><strong>SpringAop 构建在动态代理基础之上（即基于动态代理），</strong></span><strong>Spring对AOP的支持局限于方法拦截。</strong></p>

<p>理解了这些概念后如何应用Spring AOP就相对而言来说简单的多了。</p>

<h1 id="%E6%80%BB%E7%BB%93"><strong>总结</strong></h1>

<p><strong>DI目的只有一个就是解耦，实现代码的松散耦合。解决高耦合的代码带来的不易测试、不易复用的问题。</strong></p>

<p><strong>AOP解决的问题是如何把应用中横切关注点与业务逻辑相分离，解耦。把之前分散在应用各处的行为放入可重用的模块中，有效减少了代码冗余，并让类更关注于自身的主要功能和业务逻辑。</strong></p>
