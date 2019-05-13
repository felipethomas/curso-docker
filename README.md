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
- docker container run -p 80:80 ex-build-copy  
- docker container run -it -v $(pwd):/app -p 80:8000 --name python-server ex-build-dev  
- docker container run -it --volumes-from=python-server debian cat /log/http-server.log  

#### > pull
- docker image pull redis:latest  

#### > build
- docker image build -t ex-simple-build .  
- docker image build --build-arg S3_BUCKET=myapp -t ex-build-arg .  
- docker image build -t ex-build-copy .  

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
  
  
### Instalação Docker CE
- sudo apt-get update  
- sudo apt-get install \  
apt-transport-https \  
ca-certificates \  
curl \  
gnupg-agent \  
software-properties-common  
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
  
- sudo apt-key fingerprint 0EBFCD88  
- sudo add-apt-repository \  
"deb [arch=amd64] https://download.docker.com/linux/ubuntu \  
$(lsb_release -cs) \  
stable"  
  
- sudo apt-get update  
- sudo apt-get install docker-ce docker-ce-cli containerd.io  
- sudo docker run hello-world  
- sudo groupadd docker  
- sudo usermod -aG docker $USER  
  
- [Documentação Docker](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
  
  
### Docker Hub
- docker image tag oracle/database:12.2.0.1-ee felipethomas/oracle:12.2.0.1-ee  
- docker login --username=felipethomas  
- docker image push felipethomas/oracle:12.2.0.1-ee 