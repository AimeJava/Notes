     <!-- 为了防止生成的代码中有很多注释，比较难看，加入下面的配置控制  -->
     <!-- &lt;!&ndash; 是否去除自动生成的注释 true：是 ： false:否 &ndash;&gt; -->
      <commentGenerator >
               <property name="suppressDate" value="true"/>
                <property name="suppressAllComments" value="true"/>
            </commentGenerator>
    <!-- 注释控制完毕 -->

注意先后顺序。上面去除注释的配置要放在数据库配置的前面，不然会报错。