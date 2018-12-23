### 报错 ###

	HTTP Status 500 - Servlet.init() for servlet app threw exception

**根本原因**

    java.lang.IllegalStateException: Ambiguous mapping. Cannot map 'XXXController' method 
    public java.util.List<com.nf147.todo.entity.Todo> com.nf147.todo.controller.TodoController.home()
    to {[/todo],methods=[GET]}: There is already 'todoController' bean method
    public java.util.List<com.nf147.todo.entity.Todo> com.nf147.todo.controller.TodoController.delete(com.nf147.todo.entity.Todo) mapped.


**解决办法：**
这个报错说某个RequestMapping有歧义，模糊不清，基本就是说有重复的RequestMapping了，这是检查下controller层的代码看看是否有重复的RequestMapping注解

例如有两个相同的：

    @RequestMapping(method = RequestMethod.GET)