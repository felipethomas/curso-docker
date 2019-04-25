# Container Oracle
Configurações necessárias para subir um container Oracle.

### Considerações iniciais
Caso você queira gerar sua própria imagem, siga os passos a partir do tópico *Geração da imagem*.
  
Caso queira usar uma imagem já criada, siga as instruções abaixo:
- Criar um diretório para ser mapeado como volume do container  
- Dar permissão ao diretório com chmod -R o+w *diretório_criado_acima*  
- Executar o comando:  
docker container run \  
--name oracle12_2 \      
-p 1521:1521 \  
-p 5500:5500 \  
-e ORACLE_PWD=senha123 \
-v /home/oracle/container-12.2.0.1-ee:/opt/oracle/oradata \  
felipethomas/database:12.2.0.1-ee  
  
Para saber quais são os possíveis parâmetros usados na criação do container acesse o [repositório de configurações da Oracle](https://github.com/oracle/docker-images/blob/master/OracleDatabase/SingleInstance/README.md#running-oracle-database-in-a-docker-container)  
  
### Geração da imagem
- Clonar o [repositório de configurações da Oracle](https://github.com/oracle/docker-images)  
- Fazer o download do [Oracle Database 12c Release 2 para Linux x86-64](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html)  
- Copiar o arquivo *linuxx64_12201_database.zip* para o diretório *docker-images/OracleDatabase/SingleInstance/dockerfiles/12.2.0.1*  
- Gerar a imagem com o comando ./buildDockerImage.sh -v 12.2.0.1 –e  
  
### Criação do banco de dados usando a imagem criada
- Criar um diretório para ser mapeado como volume do container  
- Dar permissão ao diretório com chmod -R o+w *diretório_criado_acima*  
- Executar o comando:  
docker container run \  
--name oracle12_2 \      
-p 1521:1521 \  
-p 5500:5500 \  
-e ORACLE_PWD=senha123 \  
-v /home/oracle/container-12.2.0.1-ee:/opt/oracle/oradata \  
oracle/database:12.2.0.1-ee  
  
### Alterar a senha
- Executar o container com docker container start -i oracle12_2  
- Abrir outra aba do terminal  
- Ir até o diretório *docker-images/OracleDatabase/SingleInstance/dockerfiles/12.2.0.1/*  
- Executar o comando docker exec oracle12_2 ./setPassword.sh *nova_senha*  
  
### Inicializar o banco de dados
- Executar o container com docker container start oracle12_2  
- Aguardar o status do container ficar *healthy* (cerca de 1 minuto)  

### Referências
 - [Utilizando o Oracle Database 12.2 no Docker](https://www.oracle.com/technetwork/pt/articles/database-performance/oracle-db12-2-no-docker-4427706-ptb.html)