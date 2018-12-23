# idea的使用 #
**Alt-Enter**	万能补全
**两个Shift** 搜索框
**Ctrl + Alt + L** 格式化代码 （常用） 
**Alt + Insert**自动生成某个类的 Getters, Setters, Constructors, hashCode/equals, toString 等代码。（常用）生成构造器，get / seter等  
**Ctrl+Shift+Space** 在列出的可选项中只显示出你所输入的关键字最相关的信息。（常用）  
**Ctrl + mouse** 跳进到某个类或者方法源代码中进行查看。（常用）  
**Ctrl + Alt + T**自动生成具有环绕性质的代码，比如：if..else,try..catch, for, synchronized 等等，**使用前要先选择好需要环绕的代码块。**（常用）
**Ctrl + /**对单行代码，添加或删除注释。分为两种情况：如果只是光标停留在某行，那么连续使用该快捷键，会不断注释掉下一行的代码；如果选定了某行代码（选定了某行代码一部分也算这种情况），那么连续使用该快捷键，会在添加或删除该行注释之间来回切换。（常用）
**Ctrl + Shift +/**对代码块，添加或删除注释。它与 Ctrl + / 的区别是，它只会在代码块的开头与结尾添加注释符号！（常用）  
**Ctrl + W**	选中当前光标所在的代码块，多次触发，代码块会逐级变大。（常用）  
**Ctrl + Alt + O** 去除没有实际用到的包，这在 java 类中特别有用。（常用  
**Ctrl + Alt + I**	按照缩进的设定，自动缩进所选择的代码段。  
**Tab / Shift + Tab** 缩进或者不缩进一次所选择的代码段。（常用）  
**Shift + F6**		修改名字。（常用）不单可以改项目、文件名 还包括代码名  
**Ctrl + P** 显示 方法参数列表  


  


 
 
  
Ctrl + X 或 Shift Delete	Cut current line or selected block to clipboard	剪切当前代码。 （常用）  
Ctrl + C 或 Ctrl + Insert	Copy current line or selected block to clipboard	拷贝当前代码。 （常用）  
Ctrl + V 或 Shift + Insert	Paste from clipboard	粘贴之前剪切或拷贝的代码。（常用）  
Ctrl + Shift + V	Paste from recent buffers…	从之前的剪切或拷贝的代码历史记录中，选择现在需要粘贴的内容。（常用）    
Ctrl + D	Duplicate current line or selected block	复制当前选中的代码。（常用）    
Ctrl + Y	Delete line at caret	删除当前光标所在的代码行。（常用）    
Ctrl + Shift + J	Smart line join	把下一行的代码接续到当前的代码行。  
Ctrl + Enter	Smart line split	当前代码行与下一行代码之间插入一个空行，原来所在的光标不变。（常用）  
Shift + Enter	Start new line	当前代码行与下一行代码之间插入一个空行，原来光标现在处于新加的空行上。（常用）  
Ctrl + Shift + U	Toggle case for word at caret or selected block	所选择的内容进行大小写转换。。（常用）  
Ctrl + Shift + ]/[	Select till code block end/start	从当前光标所在位置开始，一直选择到当前光标所在代码段起始或者结束位置。  
Ctrl + Delete	Delete to word end	删除从当前光标所在位置开始，直到这个单词的结尾的内容。  
Ctrl + NumPad(+/-)	Expand/collapse code block	展开或收缩代码段。 （常用）  
Ctrl + Shift + NumPad(+)	Expand all	展开所有代码段。  
Ctrl + Shift + NumPad(-)	Collapse all	收缩所有代码段。  
Ctrl + F4	Close active editor tab	关闭当前标签页。  











http://45.63.55.2/idea

Sources 一般用于标注类似 src 这种可编译目录。有时候我们不单单项目的 src 目录要可编译，还有其他一些特别的目录也许我们也要作为可编译的目录，就需要对该目录进行此标注。只有 Sources 这种可编译目录才可以新建 Java 类和包，这一点需要牢记。



Tests 一般用于标注可编译的单元测试目录。在规范的 maven 项目结构中，顶级目录是 src，maven 的 src 我们是不会设置为 Sources 的，而是在其子目录 main 目录下的 java 目录，我们会设置为 Sources。而单元测试的目录是 src - test - java，这里的 java 目录我们就会设置为 Tests，表示该目录是作为可编译的单元测试目录。一般这个和后面几个我们都是在 maven 项目下进行配置的，但是我这里还是会先说说。从这一点我们也可以看出 IntelliJ IDEA 对 maven 项目的支持是比彻底的。


Resources 一般用于标注资源文件目录。在 maven 项目下，资源目录是单独划分出来的，其目录为：src - main -resources，这里的 resources 目录我们就会设置为 Resources，表示该目录是作为资源目录。资源目录下的文件是会被编译到输出目录下的。
Test Resources 一般用于标注单元测试的资源文件目录。在 maven 项目下，单元测试的资源目录是单独划分出来的，其目录为：src - test -resources，这里的 resources 目录我们就会设置为 Test Resources，表示该目录是作为单元测试的资源目录。资源目录下的文件是会被编译到输出目录下的。


Excluded 一般用于标注排除目录。被排除的目录不会被 IntelliJ IDEA 创建索引，相当于被 IntelliJ IDEA 废弃，该目录下的代码文件是不具备代码检查和智能提示等常规代码功能。