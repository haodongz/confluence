# Centos 6.8  Install  Confluence 6.8
# 先把软件包都下载下来
1. wget https://product-downloads.atlassian.com/software/confluence/downloads/atlassian-confluence-6.8.0-x64.bin
2. wget http://download.oracle.com/otn-pub/java/jdk/8u161-b12/2f38c3b165be4555a1fa6e98c45e0808/jdk-8u161-linux-x64.rpm
3. wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz 
4. wget https://downloads.mysql.com/archives/community/
# Install  confluence
1. ./atlassian-confluence-6.8.0-x64.bin   安装好以后需要配置下/atlassian/confluence/conf/server.xml  

server.xml 在这个里面添加Confluence 域名同理JIRA也是一样。


2. 

<Server port="8000" shutdown="SHUTDOWN" debug="0">
    <Service name="Tomcat-Standalone">
        <Connector port="8090" connectionTimeout="20000" redirectPort="8443"
                maxThreads="48" minSpareThreads="10"
                enableLookups="false" acceptCount="10" debug="0" URIEncoding="UTF-8"
		 proxyName="haodongz.com" proxyPort="80"/>

![这是一个图片](confluence_install.jpg)

