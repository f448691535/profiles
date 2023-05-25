seata-server jvm_args
jvm_args: 
-Dloader.path=D:\soft\seata-server\seata-server-1.6.1/lib
-Xmx2048m 
-Xms2048m 
-Xmn1024m 
-Xss512k 
-XX:SurvivorRatio=10 
-XX:MetaspaceSize=128m 
-XX:MaxMetaspaceSize=256m 
-XX:MaxDirectMemorySize=1024m 
-XX:-OmitStackTraceInFastThrow 
-XX:-UseAdaptiveSizePolicy 
-XX:+HeapDumpOnOutOfMemoryError 
-XX:HeapDumpPath=D:\soft\seata-server\seata-server-1.6.1/logs/java_heapdump.hprof 
-XX:+DisableExplicitGC 
-Xloggc:D:\soft\seata-server\seata-server-1.6.1/logs/seata_gc.log 
-verbose:gc 
-Dio.netty.leakDetectionLevel=advanced 
-Dapp.name=seata-server 
-Dapp.repo=D:\soft\seata-server\seata-server-1.6.1\lib 
-Dapp.home=D:\soft\seata-server\seata-server-1.6.1 
-Dbasedir=D:\soft\seata-server\seata-server-1.6.1 
-Dspring.config.location=D:\soft\seata-server\seata-server-1.6.1/conf/application.yml 
-Dlogging.config=D:\soft\seata-server\seata-server-1.6.1/conf/logback-spring.xml  


jvm配置记录
jvm最大堆内存限制为32766m，约为31.99G，超过这个值则jvm不使用指针压缩（基于java1.8~1.14版本测试）  
可通过JAVA_HOME=`/usr/libexec/java_home -v 1.8` java -Xmx32767m -XX:+PrintFlagsFinal 2> /dev/null | grep UseCompressedOops  命令来测试
     bool UseCompressedOops   = false
     上面为测试结果，为true表示使用了指针压缩，false则表示没有使用
     
-Xmx32766m //最大内存为32766m
-Xms32766m //初始内存设置为与最大内存相同  

-XX:+HeapDumpOnOutOfMemoryError //堆dump文件  
-XX:HeapDumpPath=D:\soft\seata-server\seata-server-1.6.1/logs/java_heapdump.hprof //堆文件存储路径（自行修改）  
-XX:+UseG1GC //使用G1垃圾回收器  
-Xloggc:D:\soft\seata-server\seata-server-1.6.1/logs/seata_gc.log //gc日志文件路径（自行修改）  
