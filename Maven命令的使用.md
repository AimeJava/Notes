1.命令行创建普通java项目
    
    mvn archetype:generate -DgroupId=com.fxust -DartifactId=demo -DarchetypeArtifactId=maven-archetype-quickstart
2.命令行创建javaWeb项目
    
    mvn archetype:generate -DgroupId=com.fxust.codelab -DartifactId=myweb -DarchetypeArtifactId=maven-archetype-webapp


* **mvn**调用maven的运行环境
* **archetype:generate**调用插件
* **groupId**坐标，组织id，大的项目名，一般是域名的反写，比如**com.easymorse**，可按自己意愿自定义
* **artifactId**坐标的一个元素，目录结构的根目录名称，也就是项目名称，比如helloworld，可按自己意愿自定义
* **archetypeArtifactId** 目录类型的一个类型，此为webapp的类型

