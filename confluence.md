# Centos 6.8  Install  Confluence 6.8
1. wget https://product-downloads.atlassian.com/software/confluence/downloads/atlassian-confluence-6.8.0-x64.bin
2. wget http://download.oracle.com/otn-pub/java/jdk/8u161-b12/2f38c3b165be4555a1fa6e98c45e0808/jdk-8u161-linux-x64.rpm
3. wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.46.tar.gz 
4. wget https://downloads.mysql.com/archives/community/   下载mysql5.7.20版本
# Install  confluence
1. ./atlassian-confluence-6.8.0-x64.bin
![install.jpg](confluence_install.jpg)
2. 此时会出现授权码需要在网上搜索下载注册机如下图,把服务器ID填写到注册机破解
![serveri id](confluence_server_ID.jpg)
3. 进到confluence安装目录/atlassian/confluence/confluence/WEB-INF/lib/atlassian-extras-decoder-v2-3.3.0.jar把这个软件包下载到本地修改成atlassian-extras-2.4.jar
 然后用注册机打开破解,破解完成后还需要上传到下载原文件的目录改成原来的名字就好了破解完成
![key1](key1.jpg)
![key2](key2.jpg)
4. 一定要吧Mysql 驱动放到cp  mysql-connector-java-5.1.46.jar  到/atlassian/confluence/confluence/WEB-INF/lib 这个目录下面然后重启confluence服务
![mysql](mysql.jpg)
5. 配置完毕后看下server.xml配置文件里面有说明
