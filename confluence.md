# Centos 6.8  Install  Confluence 6.8
1. wget https://product-downloads.atlassian.com/software/confluence/downloads/atlassian-confluence-6.8.0-x64.bin
2. wget http://download.oracle.com/otn-pub/java/jdk/8u161-b12/2f38c3b165be4555a1fa6e98c45e0808/jdk-8u161-linux-x64.rpm
3. wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz 
4. wget https://downloads.mysql.com/archives/community/   下载mysql5.7.20版本
# Install  confluence
1. ./atlassian-confluence-6.8.0-x64.bin
2. 此时会出现授权码需要在网上搜索下载注册机如下图,把服务器ID填写到注册机破解
3. 进到confluence安装目录/atlassian/confluence/confluence/WEB-INF/lib/atlassian-extras-decoder-v2-3.3.0.jar把这个软件包下载到本地修改成atlassian-extras-2.4.jar
 然后用注册机打开破解,破解完成后还需要上传到下载原文件的目录改成原来的名字就好了破解完成
4. 一定要吧Mysql 驱动放到cp  mysql-connector-java-5.1.46.jar  到/atlassian/confluence/confluence/WEB-INF/lib 这个目录下面然后重启confluence服务
5. 进入confluence用户管理授权信息查看授权信息是否破解成功
6. confluence配置完毕后需要修改下/atlasian/confluence/conf/server.xml配置文件添加下当前confluence的域名我这里写的443端口因为要配置手机客户端可以使用confluence,默认是8090端口nginx代理下80就行了
```xml
<Server port="8000" shutdown="SHUTDOWN" debug="0">
    <Service name="Tomcat-Standalone">
        <Connector port="8090" connectionTimeout="20000" redirectPort="8443"
                maxThreads="48" minSpareThreads="10"
                enableLookups="false" acceptCount="10" debug="0" URIEncoding="UTF-8"
		proxyName="haodongz.com" proxyPort="443" scheme="https"/>
```
7. JIRA也是一样/atlassian/jira/conf/server.xml
```xml
       <Service name="Catalina">

        <Connector port="8080"

                   maxThreads="150"
                   minSpareThreads="25"
                   connectionTimeout="20000"

                   enableLookups="false"
                   maxHttpHeaderSize="8192"
                   protocol="HTTP/1.1"
                   useBodyEncodingForURI="true"
                   redirectPort="8443"
                   acceptCount="100"
                   disableUploadTimeout="true"
                   bindOnInit="false"
		   proxyName="haodongz.com" proxyPort="443" scheme="https"/>

        <!--
```

8. 所有修改都需要重启服务才能生效/etc/init.d/jira  &&  /etc/init.d/confluence   &&  stop   start
9. 修改 cd /data/atlassian/confluence/conf/server.xml
```xml
 -->


        <Connector port="8090" connectionTimeout="20000" redirectPort="8443"
                   maxThreads="48" minSpareThreads="10"
                   enableLookups="false" acceptCount="10" debug="0" URIEncoding="UTF-8"
                   protocol="org.apache.coyote.http11.Http11NioProtocol"
                   scheme="http" proxyName="www.haodongz.com" proxyPort="80"/>


        <!--
```
