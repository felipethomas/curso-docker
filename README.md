# curso-docker
Anotações e exercícios praticados no curso de Docker da Udemy  

### comandos
- docker --help  
- docker --help | more  
- docker --version  
- docker COMMAND --help  
- docker COMMAND --help | more  

#### > run
- docker container run hello-world  
- docker container run debian bash --version  
- docker container run -it debian bash  
- docker container run --help  
- docker container run --name mydeb -it debian bash    
- docker container run -p 8080:80 nginx    
- docker container run -p 80:80 ex-simple-build  
- docker container run -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx     
- docker container run -d --name ex-daemon-basic -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx  
- docker container run --name my-apache httpd  
- docker container run --name my-apache -p 8081:80 httpd 
- docker container run ex-build-arg bash -c 'echo $S3_BUCKET'   

#### > pull
- docker image pull redis:latest  

#### > build
- docker image build -t ex-simple-build .  
- docker image build --build-arg S3_BUCKET=myapp -t ex-build-arg .  

#### > exec
- docker container exec ex-daemon-basic uname -or   

#### > ps, ls, list
- docker container ps  
- docker container ps -a  
- docker container ls  
- docker container ls -a  
- docker container list  
- docker container list -a  
- docker image ls  
- docker volume ls  

#### > start, stop, restart
- docker container start -ai mydeb  
- docker container start ex-daemon-basic  
- docker container stop ex-daemon-basic  
- docker container restart ex-daemon-basic  

#### > rm
- docker container rm 3cd2f4743b0e  
- docker container rm my-apache  
- docker image rm redis:latest cod3r-redis  

#### > logs
- docker container logs ex-daemon-basic  

#### > inspect
- docker container inspect ex-daemon-basic  
- docker image inspect redis:latest  
- docker image inspect --format="{{index .Config.Labels \"maintainer\"}}" ex-build-arg  

#### > tag
- docker image tag redis:latest cod3r-redis

#### > outros
- docker container -p 8081:80 my-apache  

