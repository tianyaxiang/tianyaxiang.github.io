<p id="main-toc"><strong>目录</strong></p>

<p id="-toc" style="margin-left:0px;"> </p>

<p id="%E4%BB%80%E4%B9%88%E6%98%AF%20MyBatis%20%EF%BC%9F-toc" style="margin-left:0px;"><a href="#%E4%BB%80%E4%B9%88%E6%98%AF%20MyBatis%20%EF%BC%9F">什么是 MyBatis ？</a></p>

<p id="%E6%98%A0%E5%B0%84%E5%99%A8%EF%BC%88mappers%EF%BC%89-toc" style="margin-left:0px;"><a href="#%E6%98%A0%E5%B0%84%E5%99%A8%EF%BC%88mappers%EF%BC%89">映射器（mappers）</a></p>

<p id="typeAliases%C2%A0%E7%B1%BB%E5%9E%8B%E5%88%AB%E5%90%8D%E5%87%8F%E5%B0%91%E7%B1%BB%E5%AE%8C%E5%85%A8%E9%99%90%E5%88%B6%E5%90%8D%E7%9A%84%E5%86%97%E4%BD%99-toc" style="margin-left:0px;"><a href="#typeAliases%C2%A0%E7%B1%BB%E5%9E%8B%E5%88%AB%E5%90%8D%E5%87%8F%E5%B0%91%E7%B1%BB%E5%AE%8C%E5%85%A8%E9%99%90%E5%88%B6%E5%90%8D%E7%9A%84%E5%86%97%E4%BD%99">typeAliases 类型别名减少类完全限制名的冗余</a></p>

<p id="%E5%A4%84%E7%90%86%E6%9E%9A%E4%B8%BE%E7%B1%BB%E5%9E%8B-toc" style="margin-left:0px;"><a href="#%E5%A4%84%E7%90%86%E6%9E%9A%E4%B8%BE%E7%B1%BB%E5%9E%8B">处理枚举类型</a></p>

<p id="%E5%A4%9A%E8%A1%8C%E6%8F%92%E5%85%A5-toc" style="margin-left:0px;"><a href="#%E5%A4%9A%E8%A1%8C%E6%8F%92%E5%85%A5">多行插入</a></p>

<p id="%E9%87%8D%E7%94%A8%C2%A0SQL%20%E4%BB%A3%E7%A0%81%E6%AE%B5%EF%BC%8C%E6%B6%88%E9%99%A4%E9%87%8D%E5%A4%8D-toc" style="margin-left:0px;"><a href="#%E9%87%8D%E7%94%A8%C2%A0SQL%20%E4%BB%A3%E7%A0%81%E6%AE%B5%EF%BC%8C%E6%B6%88%E9%99%A4%E9%87%8D%E5%A4%8D">重用 SQL 代码段，消除重复</a></p>

<p id="%E5%AD%97%E7%AC%A6%E4%B8%B2%E6%9B%BF%E6%8D%A2%23%7B%7D%E5%92%8C%24%7B%7D%E7%9A%84%E5%8C%BA%E5%88%AB-toc" style="margin-left:0px;"><a href="#%E5%AD%97%E7%AC%A6%E4%B8%B2%E6%9B%BF%E6%8D%A2%23%7B%7D%E5%92%8C%24%7B%7D%E7%9A%84%E5%8C%BA%E5%88%AB">字符串替换#{}和${}的区别</a></p>

<p id="Result%20Maps%EF%BC%8C%E8%A1%A8%E7%9A%84%E5%88%97%E5%90%8D%E5%92%8C%E7%B1%BB%E7%9A%84%E5%B1%9E%E6%80%A7%E5%90%8D%E4%B8%8D%E5%AF%B9%E5%BA%94%E6%80%8E%E4%B9%88%E5%A4%84%E7%90%86%EF%BC%9F-toc" style="margin-left:0px;"><a href="#Result%20Maps%EF%BC%8C%E8%A1%A8%E7%9A%84%E5%88%97%E5%90%8D%E5%92%8C%E7%B1%BB%E7%9A%84%E5%B1%9E%E6%80%A7%E5%90%8D%E4%B8%8D%E5%AF%B9%E5%BA%94%E6%80%8E%E4%B9%88%E5%A4%84%E7%90%86%EF%BC%9F">Result Maps，表的列名和类的属性名不对应怎么处理？</a></p>

<p id="MyBatis%E5%85%B3%E8%81%94%E7%9A%84%E5%B5%8C%E5%A5%97%E6%9F%A5%E8%AF%A2-toc" style="margin-left:0px;"><a href="#MyBatis%E5%85%B3%E8%81%94%E7%9A%84%E5%B5%8C%E5%A5%97%E6%9F%A5%E8%AF%A2">MyBatis关联的嵌套查询</a></p>

<p id="MyBatis%E9%9B%86%E5%90%88%E7%9A%84%E5%B5%8C%E5%A5%97%E6%9F%A5%E8%AF%A2-toc" style="margin-left:0px;"><a href="#MyBatis%E9%9B%86%E5%90%88%E7%9A%84%E5%B5%8C%E5%A5%97%E6%9F%A5%E8%AF%A2">MyBatis集合的嵌套查询</a></p>

<p id="%E5%8A%A8%E6%80%81%20SQL%EF%BC%8C%E5%A6%82%E4%BD%95%E4%BC%98%E9%9B%85%E7%9A%84%E6%9E%84%E5%BB%BA%E5%8A%A8%E6%80%81Sql-toc" style="margin-left:0px;"><a href="#%E5%8A%A8%E6%80%81%20SQL%EF%BC%8C%E5%A6%82%E4%BD%95%E4%BC%98%E9%9B%85%E7%9A%84%E6%9E%84%E5%BB%BA%E5%8A%A8%E6%80%81Sql">动态 SQL，如何优雅的构建动态Sql</a></p>

<p id="Where-toc" style="margin-left:40px;"><a href="#Where">Where 构建动态查询条件</a></p>

<p id="choose%2C%20when%2C%20otherwise-toc" style="margin-left:40px;"><a href="#choose%2C%20when%2C%20otherwise">choose, when, otherwise 从条件中选其一项</a></p>

<p id="set-toc" style="margin-left:40px;"><a href="#set">set 动态包含需要更新的列</a></p>

<p id="foreach-toc" style="margin-left:40px;"><a href="#foreach">foreach 构建 IN 条件语句</a></p>

<p id="bind-toc" style="margin-left:40px;"><a href="#bind">bind 构建like 查询</a></p>

<hr id="hr-toc" /><h1 id="%E4%BB%80%E4%B9%88%E6%98%AF%20MyBatis%20%EF%BC%9F">什么是 MyBatis ？</h1>

<p>MyBatis 是一款优秀的持久层框架，它支持定制化 SQL、存储过程以及高级映射。MyBatis 避免了几乎所有的 JDBC 代码和手动设置参数以及获取结果集。MyBatis 可以使用简单的 XML 或注解来配置和映射原生信息，将接口和 Java 的 POJOs(Plain Old Java Objects,普通的 Java对象)映射成数据库中的记录。</p>

<h1 id="%E6%98%A0%E5%B0%84%E5%99%A8%EF%BC%88mappers%EF%BC%89">映射器（mappers）</h1>

<p>你需要告诉 MyBatis 到哪里去找映射文件。你可以使用相对于类路径的资源引用， 或完全限定资源定位符（包括 file:/// 的 URL），或类名和包名等。</p>

<pre class="has">
<code>&lt;!-- 使用相对于类路径的资源引用 --&gt;
&lt;mappers&gt;
  &lt;mapper resource="org/mybatis/builder/AuthorMapper.xml"/&gt;
  &lt;mapper resource="org/mybatis/builder/BlogMapper.xml"/&gt;
  &lt;mapper resource="org/mybatis/builder/PostMapper.xml"/&gt;
&lt;/mappers&gt;

&lt;!-- 使用映射器接口实现类的完全限定类名  --&gt;
&lt;mappers&gt;
  &lt;mapper class="org.mybatis.builder.AuthorMapper"/&gt;
  &lt;mapper class="org.mybatis.builder.BlogMapper"/&gt;
  &lt;mapper class="org.mybatis.builder.PostMapper"/&gt;
&lt;/mappers&gt;

&lt;!-- 将包内的映射器接口实现全部注册为映射器 --&gt;
&lt;mappers&gt;
  &lt;package name="org.mybatis.builder"/&gt;
&lt;/mappers&gt;</code></pre>

<h1 id="typeAliases%C2%A0%E7%B1%BB%E5%9E%8B%E5%88%AB%E5%90%8D%E5%87%8F%E5%B0%91%E7%B1%BB%E5%AE%8C%E5%85%A8%E9%99%90%E5%88%B6%E5%90%8D%E7%9A%84%E5%86%97%E4%BD%99">typeAliases 类型别名减少类完全限制名的冗余</h1>

<p>类型别名是为 Java 类型设置一个短的名字。它只和 XML 配置有关，<strong>存在的意义仅在于用来减少类完全限定名的冗余</strong>。例如:</p>

<pre class="has">
<code>&lt;typeAliases&gt;
  &lt;typeAlias alias="Author" type="domain.blog.Author"/&gt;
  &lt;typeAlias alias="Blog" type="domain.blog.Blog"/&gt;
  &lt;typeAlias alias="Comment" type="domain.blog.Comment"/&gt;
  &lt;typeAlias alias="Post" type="domain.blog.Post"/&gt;
  &lt;typeAlias alias="Section" type="domain.blog.Section"/&gt;
  &lt;typeAlias alias="Tag" type="domain.blog.Tag"/&gt;
&lt;/typeAliases&gt;</code></pre>

<p>当这样配置时，Blog可以用在任何使用domain.blog.Blog的地方。</p>

<p>也可以指定一个包名，MyBatis 会在包名下面搜索需要的 Java Bean，比如:</p>

<pre class="has">
<code>&lt;typeAliases&gt;
  &lt;package name="domain.blog"/&gt;
&lt;/typeAliases&gt;</code></pre>

<h1 id="%E5%A4%84%E7%90%86%E6%9E%9A%E4%B8%BE%E7%B1%BB%E5%9E%8B">处理枚举类型</h1>

<p>若想映射枚举类型 Enum，则需要从 EnumTypeHandler 或者 EnumOrdinalTypeHandler 中选一个来使用。</p>

<p>比如说我们想存储取近似值时用到的舍入模式。默认情况下，MyBatis 会利用 EnumTypeHandler 来把 Enum 值转换成对应的名字。</p>

<p><strong>注意 EnumTypeHandler 在某种意义上来说是比较特别的，其他的处理器只针对某个特定的类，而它不同，它会处理任意继承了 Enum 的类。</strong></p>

<p>不过，我们可能不想存储名字，相反我们的 DBA 会坚持使用整形值代码。那也一样轻而易举： 在配置文件中<strong>把 EnumOrdinalTypeHandler 加到 typeHandlers 中即可， 这样每个 RoundingMode 将通过他们的序数值来映射成对应的整形</strong>。</p>

<pre class="has">
<code>&lt;!-- mybatis-config.xml --&gt;
&lt;typeHandlers&gt;
  &lt;typeHandler handler="org.apache.ibatis.type.EnumOrdinalTypeHandler" javaType="java.math.RoundingMode"/&gt;
&lt;/typeHandlers&gt;</code></pre>

<h1 id="%E5%A4%9A%E8%A1%8C%E6%8F%92%E5%85%A5">多行插入</h1>

<p> 可以传入一个Authors数组或集合，并返回自动生成的主键。</p>

<pre class="has">
<code>&lt;insert id="insertAuthor" useGeneratedKeys="true"
    keyProperty="id"&gt;
  insert into Author (username, password, email, bio) values
  &lt;foreach item="item" collection="list" separator=","&gt;
    (#{item.username}, #{item.password}, #{item.email}, #{item.bio})
  &lt;/foreach&gt;
&lt;/insert&gt;</code></pre>

<h1 id="%E9%87%8D%E7%94%A8%C2%A0SQL%20%E4%BB%A3%E7%A0%81%E6%AE%B5%EF%BC%8C%E6%B6%88%E9%99%A4%E9%87%8D%E5%A4%8D">重用 SQL 代码段，消除重复</h1>

<p>sql这个元素可以被用来定义可重用的 SQL 代码段，可以包含在其他语句中。它可以被静态地(在加载参数) 参数化. 不同的属性值通过包含的实例变化. 比如：</p>

<pre class="has">
<code>&lt;sql id="userColumns"&gt; ${alias}.id,${alias}.username,${alias}.password &lt;/sql&gt;
</code></pre>

<p>这个 SQL 片段可以被包含在其他语句中，例如：</p>

<pre class="has">
<code>&lt;select id="selectUsers" resultType="map"&gt;
  select
    &lt;include refid="userColumns"&gt;&lt;property name="alias" value="t1"/&gt;&lt;/include&gt;,
    &lt;include refid="userColumns"&gt;&lt;property name="alias" value="t2"/&gt;&lt;/include&gt;
  from some_table t1
    cross join some_table t2
&lt;/select&gt;
</code></pre>

<h1 id="%E5%AD%97%E7%AC%A6%E4%B8%B2%E6%9B%BF%E6%8D%A2%23%7B%7D%E5%92%8C%24%7B%7D%E7%9A%84%E5%8C%BA%E5%88%AB">字符串替换#{}和${}的区别</h1>

<p>默认情况下,使用 #{} 格式的语法会导致 MyBatis 创建 PreparedStatement 参数并安全地设置参数（就像使用 ? 一样，会有''）。这样做更安全，更迅速，通常也是首选做法。<strong>#{id}，它</strong>告诉 MyBatis 创建一个预处理语句参数，通过 JDBC，这样的一个参数在 SQL 中会由一个“?”来标识，并被传递到一个新的预处理语句中，就像这样：</p>

<pre class="has">
<code class="language-java">// Similar JDBC code, NOT MyBatis…
String selectPerson = "SELECT * FROM PERSON WHERE ID=?";
PreparedStatement ps = conn.prepareStatement(selectPerson);
ps.setInt(1,id);</code></pre>

<p>不过有时你就是想直接在 SQL 语句中插入一个不转义的字符串。比如，像 ORDER BY，你可以这样来使用：</p>

<pre class="has">
<code>ORDER BY ${columnName}
</code></pre>

<p>这里用${} MyBatis 不会修改或转义字符串。</p>

<p><span style="color:#f33b45;"><strong>NOTE: 用这种方式接受用户的输入，并将其用于语句中的参数是不安全的，会导致潜在的 SQL 注入攻击，因此要么不允许用户输入这些字段，要么自行转义并检验。</strong></span></p>

<h1 id="Result%20Maps%EF%BC%8C%E8%A1%A8%E7%9A%84%E5%88%97%E5%90%8D%E5%92%8C%E7%B1%BB%E7%9A%84%E5%B1%9E%E6%80%A7%E5%90%8D%E4%B8%8D%E5%AF%B9%E5%BA%94%E6%80%8E%E4%B9%88%E5%A4%84%E7%90%86%EF%BC%9F"><strong>Result Maps，表的</strong>列名和类的属性名不对应怎么处理？</h1>

<p>MyBatis 会在幕后自动创建一个 ResultMap，再基于属性名来映射列到 JavaBean 的属性上。如果列名和属性名没有精确匹配，可以在 SELECT 语句中对列使用别名（这是一个 基本的 SQL 特性）来匹配标签。比如：</p>

<p>方法一：</p>

<pre class="has">
<code>&lt;select id="selectUsers" resultType="User"&gt;
  select
    user_id             as "id",
    user_name           as "userName",
    hashed_password     as "hashedPassword"
  from some_table
  where id = #{id}
&lt;/select&gt;</code></pre>

<p>ResultMap 最优秀的地方在于，虽然你已经对它相当了解了，但是根本就不需要显式地用到他们。 上面这些简单的示例根本不需要下面这些繁琐的配置。 出于示范的原因，让我们来看看最后一个示例中，如果使用外部的 resultMap 会怎样，这也是解决列名不匹配的另外一种方式。方法二：</p>

<pre class="has">
<code>&lt;resultMap id="userResultMap" type="User"&gt;
  &lt;id property="id" column="user_id" /&gt;
  &lt;result property="username" column="user_name"/&gt;
  &lt;result property="password" column="hashed_password"/&gt;
&lt;/resultMap&gt;

&lt;select id="selectUsers" resultMap="userResultMap"&gt;
  select user_id, user_name, hashed_password
  from some_table
  where id = #{id}
&lt;/select&gt;</code></pre>

<h1 id="MyBatis%E5%85%B3%E8%81%94%E7%9A%84%E5%B5%8C%E5%A5%97%E6%9F%A5%E8%AF%A2">MyBatis关联的嵌套查询</h1>

<pre class="has">
<code>&lt;resultMap id="blogResult" type="Blog"&gt;
  &lt;id property="id" column="blog_id" /&gt;
  &lt;result property="title" column="blog_title"/&gt;
  &lt;association property="author" column="blog_author_id" javaType="Author" resultMap="authorResult"/&gt;
&lt;/resultMap&gt;

&lt;resultMap id="authorResult" type="Author"&gt;
  &lt;id property="id" column="author_id"/&gt;
  &lt;result property="username" column="author_username"/&gt;
  &lt;result property="password" column="author_password"/&gt;
  &lt;result property="email" column="author_email"/&gt;
  &lt;result property="bio" column="author_bio"/&gt;
&lt;/resultMap&gt;

&lt;select id="selectBlog" resultMap="blogResult"&gt;
  select
    B.id            as blog_id,
    B.title         as blog_title,
    B.author_id     as blog_author_id,
    A.id            as author_id,
    A.username      as author_username,
    A.password      as author_password,
    A.email         as author_email,
    A.bio           as author_bio
  from Blog B left outer join Author A on B.author_id = A.id
  where B.id = #{id}
&lt;/select&gt;</code></pre>

<p>在上面的示例中你可以看到博客的作者关联代表着“authorResult”结果映射来加载作 者实例。</p>

<p><strong><span style="color:#f33b45;">非常重要: </span>id元素在嵌套结果映射中扮演着非 常重要的角色。你应该总是指定一个或多个可以唯一标识结果的属性。实际上如果你不指定它的话, MyBatis仍然可以工作,但是会有严重的性能问题。在可以唯一标识结果的情况下, 尽可能少的选择属性。主键是一个显而易见的选择（即使是复合主键）。</strong></p>

<h1 id="MyBatis%E9%9B%86%E5%90%88%E7%9A%84%E5%B5%8C%E5%A5%97%E6%9F%A5%E8%AF%A2">MyBatis集合的嵌套查询</h1>

<p>继续上面的示例,一个博客只有一个作者。但是博客有很多文章。在博客类中, 这可以由下面这样的写法来表示:</p>

<pre class="has">
<code class="language-java">private List&lt;Post&gt; posts;
</code></pre>

<p>它和关联完全相同,<strong>除了它应用了一个“ofType”属性</strong></p>

<pre class="has">
<code>&lt;resultMap id="blogResult" type="Blog"&gt;
  &lt;id property="id" column="blog_id" /&gt;
  &lt;result property="title" column="blog_title"/&gt;
  &lt;collection property="posts" ofType="Post"&gt;
    &lt;id property="id" column="post_id"/&gt;
    &lt;result property="subject" column="post_subject"/&gt;
    &lt;result property="body" column="post_body"/&gt;
  &lt;/collection&gt;
&lt;/resultMap&gt;

&lt;select id="selectBlog" resultMap="blogResult"&gt;
  select
  B.id as blog_id,
  B.title as blog_title,
  B.author_id as blog_author_id,
  P.id as post_id,
  P.subject as post_subject,
  P.body as post_body,
  from Blog B
  left outer join Post P on B.id = P.blog_id
  where B.id = #{id}
&lt;/select&gt;</code></pre>

<h1 id="%E5%8A%A8%E6%80%81%20SQL%EF%BC%8C%E5%A6%82%E4%BD%95%E4%BC%98%E9%9B%85%E7%9A%84%E6%9E%84%E5%BB%BA%E5%8A%A8%E6%80%81Sql">动态 SQL，如何优雅的构建动态Sql</h1>

<p>MyBatis 的强大特性之一便是它的动态 SQL。如果你有使用 JDBC 或其它类似框架的经验，你就能体会到根据不同条件拼接 SQL 语句的痛苦。例如拼接时要确保不能忘记添加必要的空格，还要注意去掉列表最后一个列名的逗号。利用动态 SQL 这一特性可以彻底摆脱这种痛苦。</p>

<h2 id="Where">Where 构建动态查询条件</h2>

<p><em>where</em> 元素只会在至少有一个子元素的条件返回 SQL 子句的情况下才去插入“WHERE”子句。而且，若语句的开头为“AND”或“OR”，<em>where</em> 元素也会将它们去除。</p>

<pre class="has">
<code>&lt;select id="findActiveBlogLike"
     resultType="Blog"&gt;
  SELECT * FROM BLOG 
  &lt;where&gt; 
    &lt;if test="state != null"&gt;
         state = #{state}
    &lt;/if&gt; 
    &lt;if test="title != null"&gt;
        AND title like #{title}
    &lt;/if&gt;
    &lt;if test="author != null and author.name != null"&gt;
        AND author_name like #{author.name}
    &lt;/if&gt;
  &lt;/where&gt;
&lt;/select&gt;</code></pre>

<p>如果 <em>where</em> 元素没有按正常套路出牌，我们可以通过自定义 trim 元素来定制 <em>where</em> 元素的功能。比如，和 <em>where</em> 元素等价的自定义 trim 元素为下面代码：（prefixOverrides 属性会忽略通过管道分隔的文本序列（注意此例中的空格也是必要的）。它的作用是移除所有指定在 prefixOverrides 属性中的内容，并且插入 prefix 属性中指定的内容。）</p>

<pre class="has">
<code>&lt;trim prefix="WHERE" prefixOverrides="AND |OR "&gt;
  ... 
&lt;/trim&gt;
</code></pre>

<h2>choose, when, otherwise 从条件中选其一项</h2>

<p>有时我们不想应用到所有的条件语句，而只想从中择其一项。针对这种情况，MyBatis 提供了 choose 元素，它有点像 Java 中的 switch 语句。例如：提供了“title”就按“title”查找，提供了“author”就按“author”查找的情形，若两者都没有提供，就返回所有符合条件的 BLOG（实际情况可能是由管理员按一定策略选出 BLOG 列表，而不是返回大量无意义的随机结果）。</p>

<pre class="has">
<code>&lt;select id="findActiveBlogLike"
     resultType="Blog"&gt;
  SELECT * FROM BLOG WHERE state = ‘ACTIVE’
  &lt;choose&gt;
    &lt;when test="title != null"&gt;
      AND title like #{title}
    &lt;/when&gt;
    &lt;when test="author != null and author.name != null"&gt;
      AND author_name like #{author.name}
    &lt;/when&gt;
    &lt;otherwise&gt;
      AND featured = 1
    &lt;/otherwise&gt;
  &lt;/choose&gt;
&lt;/select&gt;</code></pre>

<h2 id="set">set 动态包含需要更新的列</h2>

<p><em>set</em> 元素可以用于动态包含需要更新的列，而舍去其它的。比如：</p>

<pre class="has">
<code>&lt;update id="updateAuthorIfNecessary"&gt;
  update Author
    &lt;set&gt;
      &lt;if test="username != null"&gt;username=#{username},&lt;/if&gt;
      &lt;if test="password != null"&gt;password=#{password},&lt;/if&gt;
      &lt;if test="email != null"&gt;email=#{email},&lt;/if&gt;
      &lt;if test="bio != null"&gt;bio=#{bio}&lt;/if&gt;
    &lt;/set&gt;
  where id=#{id}
&lt;/update&gt;</code></pre>

<h2 id="foreach">foreach 构建 IN 条件语句</h2>

<p>动态 SQL 的另外一个常用的操作需求是对一个集合进行遍历，通常是在构建 IN 条件语句的时候。比如：</p>

<pre class="has">
<code>&lt;select id="selectPostIn" resultType="domain.blog.Post"&gt;
  SELECT *
  FROM POST P
  WHERE ID in
  &lt;foreach item="item" index="index" collection="list"
      open="(" separator="," close=")"&gt;
        #{item}
  &lt;/foreach&gt;
&lt;/select&gt;</code></pre>

<h2 id="bind">bind 构建like 查询</h2>

<p>bind 元素可以从 OGNL 表达式中创建一个变量并将其绑定到上下文。比如：</p>

<pre class="has">
<code>&lt;select id="selectBlogsLike" resultType="Blog"&gt;
  &lt;bind name="pattern" value="'%' + _parameter.getTitle() + '%'" /&gt;
  SELECT * FROM BLOG
  WHERE title LIKE #{pattern}
&lt;/select&gt;</code></pre>