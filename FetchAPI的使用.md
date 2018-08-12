Fetch API提供了一个用于获取资源的接口（包括整个网络）。对于使用过的人来说XMLHttpRequest，这似乎很熟悉，但新API提供了更强大，更灵活的功能集。

##概念和用法
取提供了一个通用的定义
Request和Response对象（涉及网络请求其他的东西）。这将允许它们在将来需要的任何地方使用，无论是服务工作者，Cache API以及处理或修改请求和响应的其他类似事物，还是可能需要您生成自己的响应的任何用例编程。

它还提供了相关概念的定义，例如CORS和HTTP原始头语义，在其他地方取代它们的单独定义。

要发出请求并获取资源，请使用该GlobalFetch.fetch方法。它在多个接口实现的，特别是Window和WorkerGlobalScope。这使得它几乎可以在您可能想要获取资源的任何上下文中使用。

该  fetch() 方法采用一个必需参数，即要获取的资源的路径。无论是否成功，它都会返回一个Promise解析Response为该请求的内容。您还可以选择传入initoptions对象作为第二个参数（请参阅参考资料Request）。

一旦Response检索到a，就可以使用许多方法来定义正文内容以及如何处理它（参见参考资料Body）。

您可以使用Request()和Response()构造函数直接创建请求和响应，但不太可能直接执行此操作。相反，这些更有可能被创建为其他API操作的结果（例如，FetchEvent.respondWith来自服务工作者）。

注意：了解有关在使用Fetch中使用Fetch API功能的更多信息，并学习Fetch基本概念中的概念。

##中止取消
浏览器已开始为这些AbortController和AbortSignal接口（又名为Abort API）添加实验性支持，如果尚未完成，则允许中止Fetch和XHR等操作。有关详细信息，请参阅界面页面。

##获取接口
fetch()  
fetch()用于获取资源的方法。  

Headers  
表示响应/请求标头，允许您查询它们并根据结果采取不同的操作。 
 
Request  
表示资源请求。  

Response  
表示对请求的响应。  

##取混合
Body
提供与响应/请求正文相关的方法，允许您声明其内容类型以及应如何处理。