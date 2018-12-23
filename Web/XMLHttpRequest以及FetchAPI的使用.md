##什么是 XMLHttpRequest 对象？
XMLHttpRequest 对象用于在后台与服务器交换数据。

* 在不重新加载页面的情况下更新网页
* 在页面已加载后从服务器请求数据
* 在页面已加载后从服务器接收数据
* 在后台向服务器发送数据

所有现代的浏览器都支持 XMLHttpRequest 对象。

##创建 XMLHttpRequest 对象
所有现代浏览器 (IE7+、Firefox、Chrome、Safari 以及 Opera) 都内建了 XMLHttpRequest 对象。

通过一行简单的 JavaScript 代码，我们就可以创建 XMLHttpRequest 对象。

**创建 XMLHttpRequest 对象的语法：    xmlhttp=new XMLHttpRequest();**


    <script type="text/javascript">
    var xmlhttp;
    function loadXMLDoc(url)
    {
    xmlhttp=null;
    if (window.XMLHttpRequest)
      {// code for all new browsers
      xmlhttp=new XMLHttpRequest();
      }
    else if (window.ActiveXObject)
      {// code for IE5 and IE6
      xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
      }
    if (xmlhttp!=null)
      {
      xmlhttp.onreadystatechange=state_Change;
      xmlhttp.open("GET",url,true);
      xmlhttp.send(null);
      }
    else
      {
      alert("Your browser does not support XMLHTTP.");
      }
    }
    
    function state_Change()
    {
    if (xmlhttp.readyState==4)
      {// 4 = "loaded"
      if (xmlhttp.status==200)
    {// 200 = OK
    // ...our code here...
    }
      else
    {
    alert("Problem retrieving XML data");
    }
      }
    }
    </script>

**注释**：onreadystatechange 是一个事件句柄。它的值 (state_Change) 是一个函数的名称，当 XMLHttpRequest 对象的状态发生改变时，会触发此函数。状态从 0 (uninitialized) 到 4 (complete) 进行变化。仅在状态为 4 时，我们才执行代码。

###为什么使用 Async=true ？
我们的实例在 open() 的第三个参数中使用了 "true"。

该参数规定请求是否异步处理。

True 表示脚本会在 send() 方法之后继续执行，而不等待来自服务器的响应。

onreadystatechange 事件使代码复杂化了。但是这是在没有得到服务器响应的情况下，防止代码停止的最安全的方法。

通过把该参数设置为 "false"，可以省去额外的 onreadystatechange 代码。如果在请求失败时是否执行其余的代码无关紧要，那么可以使用这个参数。