# mysql默认8小时连接断开机制解决 https://blog.csdn.net/u012129031/article/details/72621288
# C3P0官方对于MySQL8小时问题的解决方案 https://blog.csdn.net/frankcheng5143/article/details/50589264
# 解决MYSQL 8小时连接问题 https://blog.csdn.net/risingsun001/article/details/12199075
# spring boot mysql 8小时连接超时 https://blog.csdn.net/u013378306/article/details/78085366
# 《深入理解mybatis原理》 Mybatis数据源与连接池 https://blog.csdn.net/luanlouis/article/details/37671851
# Mybatis jdbc连接超时解决 https://blog.csdn.net/a360616218/article/details/77512217

<environments default="development">   
   <environment id="development">   
       <transactionManager type="jdbc"/>   
       <dataSource type="POOLED">   
           <property name="url" value="${cp.Url}"/>  
           <property name="driver" value="${cp.DriverClassName}"/>  
           <property name="username" value="${cp.Username}"/>   
           <property name="password" value="${cp.Password}"/>   
           <property name="poolPingEnabled" value="true"/>  
           <property name="poolPingQuery" value="select 1"/>  
           <property name="poolPingConnectionsNotUsedFor" value="3600000"/>  
       </dataSource>   
   </environment>   
</environments>  
