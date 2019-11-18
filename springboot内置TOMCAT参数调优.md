# springboot

zuul.host.maxTotalConnections = 100000
zuul.host.maxPerRouteConnections = 10000
zuul.ribbon-isolation-strategy = semaphore
zuul.semaphore.max-Semaphores = 20000
hystrix.command.default.execution.isolation.strategy = semaphore
hystrix.command.default.execution.isolation.semaphore.maxConcurrentRequests = 20000

# springboot 内置TOMCAT参数调优

server.connection-timeout = 10000
server.tomcat.max-threads = 20000
server.tomcat.min-spare-threads = 200
server.tomcat.accept-count = 20000
server.max-http-header-size = 65536


查看线程数 ps -TH $pid|wc -l 





/usr/java/jdk1.8.0_121/bin/java -server -XX:G1ReservePercent=10 -XX:+HeapDumpOnOutOfMemoryError -XX:+UseConcMarkSweepGC -XX:CMSInitiatingOccupancyFraction=85 -XX:MaxDirectMemorySize=512m -XX:+CMSParallelRemarkEnabled -XX:+UseParNewGC -XX:PermSize=128m -XX:MaxPermSize=128m -XX:MetaspaceSize=256m -XX:MaxMetaspaceSize=256m -Xms5G -Xmx5G -XX:NewSize=1g -XX:MaxNewSize=1g -Dserver.port=9213 -javaagent:/home/wls81/tomcat/skywalking_agent/skywalking-agent.jar -Dskywalking.agent.service_name=webconfig -jar /home/wls81/tomcat/webconfig/webconfig.jar


http://i2.51cto.com/images/blog/201808/21/b116170771ecb3117ae7fead03fcaa0d.png?x-oss-process=image/watermark,size_16,text_QDUxQ1RP5Y2a5a6i,color_FFFFFF,t_100,g_se,x_10,y_10,shadow_90,type_ZmFuZ3poZW5naGVpdGk=


jps 

jmap -heap $pid



