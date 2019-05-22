# Enviar imagem para o Docker Hub
- docker image tag oracle/database:12.2.0.1-ee felipethomas/oracle:12.2.0.1-ee  
- docker login --username=felipethomas  
- docker image push felipethomas/oracle:12.2.0.1-ee 