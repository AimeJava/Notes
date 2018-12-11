SiteMesh 是一个网页布局和修饰的框架，利用它可以将网页的内容和页面结构分离，以达到页面结构共享的目的。

Sitemesh是由一个基于Web页面布局、装饰以及与现存Web应用整合的框架。

- SiteMesh是一个网页布局和装饰框架以及Web应用程序集成框架，用于帮助创建由需要一致外观，导航和布局方案的页面组成的网站。
- SiteMesh拦截对通过Web服务器请求的任何静态或动态生成的HTML页面的请求，处理内容，然后将其与一个或多个装饰器合并以构建最终结果。
- SiteMesh还可用于构成较大页面和布局的大页面。
- SiteMesh很快。真的很快
- SiteMesh可用于基于Java的Web应用程序，也可作为脱机作业应用于内容。
- SiteMesh是可扩展的。

## 工作原理 ##
SiteMesh是基于Servlet的filter的，即过滤流。它是通过截取response，并进行装饰后再交付给客户。

其中涉及到两个名词： 装饰页面(decorator page)和 被装饰页面(Content page), 即 SiteMesh通过对Content Page的装饰，最终得到页面布局和外观一致的页面，并返回给客户。

运行SiteMesh3至少需要：

JDK 1.5
一个Servlet 2.5兼容容器
SiteMesh运行时库