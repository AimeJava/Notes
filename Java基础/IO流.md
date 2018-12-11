# IO流 （输入输出流） #
File类：
作用：管理文件或文件夹
常用的方法：
createNewFile();//根据给定的路径创建新文件
exists()：判断文件是否存在
isDirectory()：判断是否是目录
delete()：如果存在则删除
list()：列出给定目录中的内容
listFiles()：如果是目录，则列出全部内容，
length()：方法返回的是文件的大小
mkdir（）：方法可以创建一个目录
mkdirs（）：没有父目录则 一起创建
renameTo(File dest):重命名

常用的常量：
pathSeparator分隔符是\;
Separator：分隔符是\

### 字节流 ###
写入文件用输出，读取文件用输入

操作类型：byte[] 

低层流:OutputStream（输出）类和InputStream（输入）类

**OutputStream**：抽象类，必须通过子类实例化对象
方法：write()
**InputStream**：抽象类，必须通过子类实例化对象
方法：read()
高层流: bufferOutputStream（输出）类和bufferInputStream（输入）类
**Flush()**:可以把缓冲区的内容清空并写入文件

### 字符流 ###
写入文件用输出，读取文件用输入
字符输出流：Writer

        //找到文件
        FileWriter fr = new FileWriter("E:" + File.separator + "IOTest.txt");
        //创建字符流
        BufferedWriter bw = new BufferedWriter(fr);
        //输出
        bw.write("大家好");
        //清除缓存
        bw.flush();
        bw.close();
        fr.close();
字符输入流：Reader
 	
    FileReader fr = new FileReader("E:" + File.separator + "IOTest.txt");
    
    BufferedReader br = new BufferedReader(fr);
    
    String str ;
    
    while ((str = br.readLine()) != null){
    System.out.println(str);
    }
（高层流）: bufferedWriter（输出）类和bufferedReader（输入）类
Flush():可以把缓冲区的内容清空并写入文件



### 序列化和反序列化 ###
把对象写入文件里
高层流：
ObjectoutputStream：
ObjectinputStream：

Transient关键字：
如果一个对象中的某个属性不希望被序列化，则可以使用transient关键字声明

字节流和字符流的步骤：
1. 使用File类打开一个文件
2. 通过流的子类指定输出的位置
3. 进行读和写
4. 关闭输入/输出