1.文件上传和下载
         安装插件  yum install lrzsz
         rz     宿主机——>虚拟机
         sz     虚拟机——>宿主机
         
2.FTP
         yum -y remove vsftpd     卸载
         useradd admin
         passwd admin             添加用户密码
         yum -y install vsftpd    安装
         service iptables stop    关闭服务
         setenforce 0
         service vsftp restart    重启

3.jdk安装
         yum -y remove java         卸载
         tar -zxvf jdk---.tar.gz    解压
         vim /etc/profile           修改添加环境变量
                  export JAVA_HOME=/usr/java
                  export PATH=$JAVA_HOME/bin:$PATH
                  export classpath=.:JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
         source /etc/profile        
         java -version
         
 4.tomcat
         tar -zxvf 安装包.gz
         mv old tomcat8
         vim /etc/profile
                  tomcat_home=tomcat8
                  catalina-home=tomcat8
                  path=;$tomcat_home/bin
         source /etc/profile
         sh startup.sh
         sh shutdown.sh  
         
5.mysql
         先移动  到  /etc/yum.repos.d
         rpm -ivh mysql.rpm
         yum install my-community-server -y
         service mysqld start
         mysql -u root -p
         set password for root@localhost=password("root")
         exit
         create database db_name;
         use db_name
         source /usr/local/my/ss.sql
         
         
        
