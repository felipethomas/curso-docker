# Oracle 18c XE

### Método usando oraclelinux:7-slim
[Guia de instruções](https://github.com/felipethomas/docker-oracle-xe/blob/master/README.md)

### Método mais completo
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

