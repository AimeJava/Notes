
      <commentGenerator >
             <property name="suppressDate" value="true"/>
             <property name="suppressAllComments" value="true"/>
      </commentGenerator>

其中suppressDate是去掉生成日期那行注释，suppressAllComments是去掉所有的注解；
另外，commentGenerator还可以配置一个type，设置自己的注解生成器，默认使用的是org.mybatis.generator.internal.DefaultCommentGenerator；


注意先后顺序。上面去除注释的配置要放在数据库配置的前面，不然会报错。