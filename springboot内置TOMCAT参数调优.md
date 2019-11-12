# springboot

zuul.host.maxTotalConnections = 8000

zuul.host.maxPerRouteConnections = 8000

zuul.ribbon-isolation-strategy = semaphore

zuul.semaphore.max-Semaphores = 8000

hystrix.command.default.execution.isolation.strategy = semaphore

hystrix.command.default.execution.isolation.semaphore.maxConcurrentRequests = 8000

# springboot 内置TOMCAT参数调优

server.connection-timeout = 20000

server.tomcat.max-threads = 8000

server.tomcat.min-spare-threads = 20

server.tomcat.accept-count = 8000

server.max-http-header-size = 65536


 java -server -Xms1g -Xmx1g -XX:MetaspaceSize=2g -XX:MaxMetaspaceSize=2g -XX:+DisableExplicitGC -XX:+UseG1GC -XX:MaxGCPauseMillis=200 -XX:ParallelGCThreads=8 -XX:ConcGCThreads=8 -XX:InitiatingHeapOccupancyPercent=45 -XX:NewRatio=2 -XX:SurvivorRatio=8 -XX:MaxTenuringThreshold=15 -XX:G1ReservePercent=10 -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/data/walkeureka/logs/ -Denv=fat -Ddubbo.reference.check=false  -javaagent:/home/wls81/tomcat/skywalking_agent/skywalking-agent.jar -Dskywalking.agent.service_name=walkingapigateway -jar /home/wls81/tomcat/walkeureka/walkeureka.jar

java -XX:+UseConcMarkSweepGC -XX:CMSInitiatingOccupancyFraction=85 -XX:MaxDirectMemorySize=512m -XX:+CMSParallelRemarkEnabled -XX:+UseParNewGC -server -Xms12G -Xmx12G -Dserver.port=9227 -javaagent:/home/wls81/tomcat/skywalking_agent/skywalking-agent.jar -Dskywalking.agent.service_name=walkingapigateway -jar /home/wls81/tomcat/walkingapigateway/walkingapigateway.jar
