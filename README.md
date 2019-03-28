# curso-docker
Anotações e exercícios praticados no curso de Docker da Udemy  

### comandos
- docker --help  
- docker --help | more  
- docker --version  

#### > run
- docker container run hello-world  
- docker container run debian bash --version  
- docker container run -it debian bash  
- docker container run --help  
- docker container run --name mydeb -it debian bash    
- docker container run -p 8080:80 nginx  
- docker container run -p 8080:80 -v $(pwd)/not-found:/usr/share/nginx/html nginx  
- docker container run -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx  
- docker container run -d --name ex-daemon-basic -p 8080:80 -v   
- docker container run -d --name ex-daemon-basic -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx  
- docker container run --name my-apache httpd  
- docker container run --name my-apache -p 8081:80 httpd  

#### > ps
- docker container ps  
- docker container ps -a  

#### > ls
- docker container ls  
- docker container ls -a  

#### > list
- docker container list  
- docker container list -a  

#### > start
- docker container start -ai mydeb  
- docker container start ex-daemon-basic  

#### > stop
- docker container stop ex-daemon-basic  

#### > restart
- docker container restart ex-daemon-basic  

#### > rm
- docker container rm 3cd2f4743b0e  
- docker container rm my-apache  

#### > logs
- docker container logs ex-daemon-basic  

#### > inspect
- docker container inspect ex-daemon-basic  

#### > exec
- docker container exec ex-daemon-basic uname -or  

#### > outros
- docker image  ls  
- docker volume ls  
- docker container -p 8081:80 my-apache  
- docker COMMAND --help  
- docker COMMAND --help | more  
