# Oracle 18c XE

### Método que usa oraclelinux:7-slim
- [Guia de instruções](https://github.com/felipethomas/docker-oracle-xe/blob/master/README.md)
  
##### TL;DR
- mkdir container-18c.1.0.1-xe  
- chmod -R o+w container-18c.1.0.1-xe  
- git clone https://github.com/fuzziebrain/docker-oracle-xe.git  
- cd docker-oracle-xe  
- cp ~/Downloads/oracle-database-xe-18c-1.0-1.x86_64.rpm files/  
- docker build -t oracle-xe:18c .  
- docker run -d \  
  -p 32118:1521 \  
  -p 35518:5500 \  
  --name=oracle18c_xe \  
  --volume /home/01308900490/ambientes/oracle/container-18c.1.0.1-xe:/opt/oracle/oradata \  
  oracle-xe:18c  
- docker logs oracle18c_xe (aguardar "Completed: ALTER PLUGGABLE DATABASE XEPDB1 SAVE STATE")  
- docker ps (aguardar STATUS "healthy")  
- docker stop -t 200 oracle18c_xe  
- docker start oracle18c_xe  
    
### Método que usa centos:7
- download dos arquivos: oracle-database-preinstall-18c-1.0-1.el7.x86_64 e oracle-database-xe-18c-1.0-1.x86_64

- docker container run -it --name centos_oracle centos:7  
- docker cp Downloads/oracle-database-xe-18c-1.0-1.x86_64.rpm centos_oracle:/home/oracle-database-xe-18c-1.0-1.x86_64.rpm  
- cd /home  
- curl -o oracle-database-preinstall-18c-1.0-1.el7.x86_64.rpm https://yum.oracle.com/repo/OracleLinux/OL7/latest/x86_64/getPackage/oracle-database-preinstall-18c-1.0-1.el7.x86_64.rpm  
- yum -y localinstall oracle-database-preinstall-18c-1.0-1.el7.x86_64.rpm  
  
- vi /etc/pam.d/su  
- comentar a linha: session                include         system-auth  
- testar: su - oracle  
- yum -y localinstall oracle-database-xe-18c-1.0-1.x86_64.rpm  
- /etc/init.d/oracle-xe-18c configure  

