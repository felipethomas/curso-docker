# Iniciar um container no boot:

- sudo systemctl enable docker  
- docker rename oracle18c_xe oracle_backup  
- docker run -d --restart always \  
-p 32118:1521 \  
-p 35518:5500 \  
--name=oracle18c_xe \  
--volume /home/01308900490/ambientes/oracle/container-18c.1.0.1-xe:/opt/oracle/oradata \  
felipethomas/oracle:18c  
- docker container ps --filter "name=oracle18c_xe" --format "table {{.Names}}\t{{.Status}}"  
