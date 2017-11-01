# webapi中的类库到底是什么

1. Antlr3.Runtime.dll 
   1. Antlr的程序集。Antlr（ANother Tool for Language Recognition）是一个工具。
   2. 它为我们构造自己的识别器（recognizers）、编译器（compiler）和转换器（translators）提供了一个基础。
   3. 通过定义自己的语言规则，Antlr可以为我们生成相应的语言解析器，这样便可以省却了自己全手工打造的劳苦。
   4. 扩展：<a style="color:red;" href="https://stackoverflow.com/questions/7177606/when-do-we-use-antlr" target="_blank">When do we use ANTLR</a>
      1. You would need these dll's if you are parsing any text at runtime using an antlr grammar
      2. Typically there are two steps.
      3.  run the java antlr parser over your .g files to generate a C# lexer, C# grammar and possibly C# tree walkers.
      4. Build those files into your application. Those files will work in conjunction with the antlr.runtime dll, or antlr3.runtime dll if you're using ANTLR version 3.
      5. Your C# program can now parse text files using the grammar that you compiled in step 1.


1. Microsoft.AI.Agent.Intercept.dll                不清楚，怀疑和microsoft ai有关 


2. Microsoft.AI.DependencyCollector.dll


3. Microsoft.AI.PerfCounterCollector.dll


4. Microsoft.AI.ServerTelemetryChannel.dll


5. Microsoft.AI.Web.dll

6. Microsoft.AI.WindowsServer.dll                  同上


7. Microsoft.ApplicationInsights.dll                  
   1. 应用程序监控
   2. 第一次知道，只有深入去整理才能发现，要么去看理论书
   3. 相关文章：采用 Application Insights 进行新一代开发


1. Microsoft.CodeDom.Providers.DotNetCompilerPlatform.dll    
   1. CodeDom是一种动态代码生成的技术
   2. 对象可以是多种语言  还有个同类技术T4 估计不少人知道
   3. 这个类库明显是用于DoNet编译


1. Microsoft.CSharp
   1. C#必备类库 
   2. 运行时编译类库 和dymanic等配合使用
   3. Microsoft.Web.Infrastructure.dll
   4. 官方给予了解释
   5. This package contains the Microsoft.Web.Infrastructure assembly that lets you dynamically register HTTP modules at run time.
   6. 在运行时动态注册Http modules


1. Newtonsoft.Json.dll
   1. json序列化类库
1. System
   1. 系统类库 不解释


1. System.ComponentModel.DataAnnotations.dll
   1. 为实体类定义元数据的特性类 
   2. StringLengthAttribute等
   3. System.Configuration.dll
   4. 多用于读取web/app.config


1. System.Core                                  
2. System.Data.dll                              
3. System.Data.DataSetExtensions 
4. System.Drawing                            
   1. 绘图，顺带上面的类库不解释


1. System.Net.Http.dll                        
   1. 为HTTP 应用程序提供一种编程接口
1. System.Net.Http.Formatting.dll
   1. 采用基于所请求媒体类型的格式来序列化和反序列化 HTTP 消息正文


1. System.Net.Http.WebRequest 
   1. Provides desktop-specific features not available to Windows Store apps or other environments
   2. 微软提供了中文注解：提供了特定于桌面的功能不可用的 Windows 应用商店应用程序或其他环境
   3. 不理解 唯一可以知道的这个类库下只有一个类 ：System.Net.Http.WebRequestHandler 
   4. 命名空间居然是System.Net.Http，后续有必要调查下为什么微软独立一个这样的类库,也许真如描述那样：specific


1. System.Runtime.Serialization.dll 
   1. 对象序列化和反序列化的类


1. System.Web.dll 
   1. 官方描述：
   2. This namespace includes the HttpRequest class, 
   3. which provides extensive information about the current HTTP request; 
   4. the HttpResponse class, which manages HTTP output to the client; 
   5. and the HttpServerUtility class, which provides access to server-side utilities and processes.
   6. System.Web 命名空间提供类和接口，使浏览器 / 服务器通信
   7. 此命名空间包括 HttpRequest 类，该类提供当前 HTTP 请求
   8. 有关的大量信息 HttpResponse 类，该类管理 HTTP 输出到客户端，
   9. 则与 HttpServerUtility 类，该类提供对服务器端实用程序和进程的访问
   10. System.Web 此外包括用于 cookie 管理、 文件传输、 异常信息和输出缓存控制类。


1. System.Web.Abstractions.dll 
   1. 神坑  ^_^ 所以这是一个空的类库，但是似乎还不能脱离 ，考虑下为什么？
   2. 此程序集中的类型已移动到 ASP.NET 4 的 System.Web.dll 中。
   3. 还有一个同样的类库：System.Web.Routing.dll
   4. 相关文章
   5. System.Web.ApplicationServices
   6. The System.Web.ApplicationServices namespace provides classes that 
   7. enable you to access ASP.NET forms authentication, roles, 
   8. and profiles application services as Windows Communication Foundation (WCF) services.
   9. ASP.NET  技术的权限验证等等。 


1. System.Web.Entity 
   1. 对实体框架的核心功能的访问的类
   2. 说穿了就是支持EntityFramework的东西


1. System.Web.Helpers.dll
早期asp.net留下来的一些帮助类 
   1. 涉及恶意脚本，javascript 数组对象，邮件发送，缓存 等等。


1. System.Web.Http.dll
   1. System.Web.Http 命名空间包含 HTTP 特性的类。
   2. 说穿了都是定义一些Http有关的类，他们继承自Attribute
   3. HttpPostAttribute 眼熟不？  [HttpPost] 这样呢？

1. System.Web.Http.WebHost.dll
   1. 包含与 Web 托管相关的类。
   2. 指运行程序的容器有关的类（IIS就是一种容器）


1. System.Web.Mvc.dll
   1. System.Web.Mvc 命名空间包含一些类和接口，它们支持用于创建 Web 应用程序的 ASP.NET 模型视图控制器 (MVC) 框架。 
   2. 该命名空间包含表示控制器、控制器工厂、操作结果、视图、分部视图以及模型联编程序等的类。


1. System.Web.Optimization.dll
   1. 优化js和css文件 主要做压缩


1. System.Web.Razor.dll
   1. razor语法相关


1. System.Web.Routing.dll
   1. 上面已经解释

1. System.Web.WebPages.Deployment.dll
   1. Web 应用程序部署的类 
   2. 为预启动代码提供注册点  <a style="color:red;" href="https://msdn.microsoft.com/zh-cn/library/system.web.webpages.deployment.preapplicationstartcode(v=vs.111).aspx" target="_blank">PreApplicationStartCode</a>


1. System.Web.WebPages.dll
   1. 呈现和执行使用 ASP.NET Web Pages with Razor Syntax 构建的页


2. System.Web.WebPages.Razor.dll
   1. 仅供内部使用，不能在代码中直接调用的类。 厉害了 


1. System.Xml
2. System.Xml.Linq


3. WebGrease.dll
   1. WebGrease is a suite of tools for optimizing javascript, css files and images.
   2. 作用很明显，压缩js css 图片文件。 配和上面的一些类库一起使用的。
   3. 网站： http://webgrease.codeplex.com/
   4. 题外话： codeplex 要shutting down 了，从2006年到现在都已经十年了，2017年12月15号就要关了。
   5. WebGrease的源代码也就1.0的，从nuget上可以看到经历了1.0，1.1，1.3，1.5.2，1.6相关版本
   6. WebGrease保存了一份代码，以后观摩。 当然知道我有代码的小伙伴，关服后可以找我要。

> 以上类库基于VS2017 项目选择的是 webapi项目 （默认自带mvc 和api）