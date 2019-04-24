# Container Oracle
Configurações necessárias para subir um container Oracle.
  
### Geração da imagem
- Clonar o repositório [docker-images](https://github.com/oracle/docker-images)  
- Fazer o download do [Oracle Database 12c Release 2 para Linux x86-64](http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index.html)  
- Copiar o arquivo linuxx64_12201_database.zip para o diretório docker-images/OracleDatabase/SingleInstance/dockerfiles/12.2.0.1  
- Gerar a imagem com o comando ./buildDockerImage.sh -v 12.2.0.1 –e  
  
### Referências
 - [Utilizando o Oracle Database 12.2 no Docker](https://www.oracle.com/technetwork/pt/articles/database-performance/oracle-db12-2-no-docker-4427706-ptb.html)