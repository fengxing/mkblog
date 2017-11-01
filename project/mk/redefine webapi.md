## 做正确的事之redefine webapi

本文由四个部分组成 
1. webapi是什么,怎么样
2. 我们需要什么样的webapi
3. 按照我们的目标重新定义webapi
4. 重新定义的webapi特性总结和分享 


### 第一部分
说到webapi,就不得不说mvc，导致很多人问这样的问题：
<a href="https://www.zhihu.com/question/46369458" target="_blank">WebApi和MVC有什么区别？</a>
<br/>
答案很有意思：
1. webapi和mvc有关系,且webapi在功能上约等于mvc.
2. mvc主要用于建站，webapi主要用于构建http服务

但是在我看来，webapi和mvc一脉相承，但是异于mvc。
1. webapi是一个基于http的通信框架，而mvc是基于http通信协议上的一种后端架构模式
2. webapi和html没有任何耦合关系，webapi不考虑任何视图的事情.而mvc恰恰有一个Razor引擎。
3. webapi传输数据更方便,框架更轻量。


### 第二部分
与其说我们需要什么样的webapi,还不如说我们需要什么样的东西更恰当。
<br/>webapi、mvc、更早期的ashx等等都是微软给你的,人家撂挑子不干了,你也没辙。
<br/>用下来各种被抛弃、难受。
<br/>面对自己的内心,问自己一句凭什么,然后怎么办!!!
<br/>很简单，说到底你不是规则的制定者，永远都是使用者,因为你从来没有深入思考过！！！
<br/>现在我们需要干嘛???
1. 思考怎么正确的制定规则
2. 实现规则,未来干正确的事情
3. 持续思考，不断循环这样的过程。


### 第三部分上---有什么功能
webapi有什么功能或者说大家如何使用? 整理下大概如下:
1. Http verb,GET, POST, PUT, DELETE的CRUD
2. Http Status Code表达不同含义
3. 客户端可以通过Accept header来与服务器协商格式(Json Xml)
4. 支持OData
5. 支持Self-host或者IIS host
6. 支持大多数MVC功能
7. 过滤器-异常处理,授权等
8. 一种获取数据的载体(特别适合移动端),前后端分离等。 支持跨域
9. 特别魔性的webapi使用<br/>
<a href="http://www.cnblogs.com/lenic/p/4129096.html" target="_blank">WebApi 插件式构建方案（服务化方案）</a><br/>
<a href="http://www.cnblogs.com/1zhk/p/5418694.html" target="_blank">ABP中动态WebAPI原理解析</a><br/>
<a href="http://www.cnblogs.com/ideacore/p/6434294.html" target="_blank">Web API 接口版本控制 SDammann.WebApi.Versioning</a><br/>
<a href="http://www.cnblogs.com/yanweidie/p/5709113.html" target="_blank">webapi文档描述-swagger</a><br/>

### 第三部分中---一些想法
#### 如何分析特性,用什么原则?
核心：基于复杂的事实并找一个较好的可实现的点。
#### 基于数据库模式的CURD来定义Http的操作真的好吗?
数据库的虽然只有增删查改操作，但是我们是这样做的
1. 新增Add
2. 更新Update
3. 删除Delete
4. 查询Query
5. 新增/更新AddUpdate
6. 混合Mixed(add update addupdate delete)
#### Http Status Code表达不同含义 
<a href="https://baike.baidu.com/item/HTTP%E7%8A%B6%E6%80%81%E7%A0%81/5053660" target="_blank">HTTP状态码文档</a>
这样的code太多了,太复杂了,描述可能正确，但是不具备实现性。
#### 客户端可以通过Accept header来与服务器协商格式(Json Xml)
Json的性能超过xml很多倍,功能价值很低,除非特定情况
#### 支持OData
数据非常冗余,需要传递数据格式,数据包超级大,至今也没怎么火<br/>
数据的定义和数据内容一起传输对大多人来说不是好事情。
<img src="images/odata.png"/>
#### 版本控制和文档
利用api去做版本,最后得到的功能一定很弱,毕竟升级不是那么简单的事情。<br/>
文档的想法很好,但是产品最后不是那么理想,思想可以借鉴，但是使用还是悠着点。

### 第三部分下---总结
1. 只使用HttpPost,数据操作通过其他的特性去做定义
2. 重新定义HttpCode,以用户的纬度去做事情,具体定义参考这里<a href="Http接口消息定义文档.html" target="_blank">>重新定义HTTP状态码文档</a>
3. 大格局支持json格式和纯text模式
4. webapi特有的全局异常处理


### 第四部分总结和分享 
分享要结束了，以上的总结只是大方向的总结，未来还有更多对webapi的定义。<br/>
文章写的很艰难,前后考虑2个月才写下这些心得~。<br/>
最后,未来webapi也许会在微软手下有更多的演进,但是核心思想还是那样,基于那简单的原则.<br/>




