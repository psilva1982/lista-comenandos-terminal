# DOCKER

### Executar um container (Faz o download e executa) 
* Este modo sempre cria um novo container
```
docker container run hello-world
```

### Executar um container em modo interativo
``` 
Exemplos: 

docker container exec -it nomecontainer comando 
docker container run -it debian bash
docker exec -i -u 0 -t elasticsearch /bin/bash
```

### Atribuir um nome para o container
```
docker container run --name mydeb -it debian bash
```

### Cria um container no modo daemon - Vai executar o container por 1000 segundos
    
```
docker container run -d --name nome_container --net nome_rede  nome_imagem sleep 1000 
```

### Mostra quais containers estão ativos
```
docker container ps
```

### Mostra quantos container foram executados / existem
```
docker container ps -a
```

### Lista os container ativos 
```
docker container ls 
```

### Lista todos os containers
```
docker container ls -a
```

### Inicia um container existente 
```
docker container start -ia mydeb
```

### Expoe a porta 8080 para acessar a porta 80 interna do servidor
```
docker container run -p 8080:80 nginx
```

### Mapear um diretório 
```
docker container run -p 8080:80 -v /home/public/html:/usr/share/nginx/html nginx
```

### Executar um container com o modo daemon
* Define um nome para o container
* Publicando as portas do container 
* Compartilhamento de volumes 
```
docker container run -d --name ex-daemon-basic -p 8080:80 -v /home/shared/html:/usr/shared/nginx/html nginx
``` 

### Parar um container que esteja executando
```
docker container stop ex-daemon-basic
```

### Exibir logs
``` 
docker container logs nome_container
```

### Inspecionar o container
```
docker container inspect nome_container
```

### Baixar a última versão da imagem
```
docker image pull redis:latest
```
### Listar imagens disponíveis
```
docker image ls
```
### Adicionar uma nova tag para imagem 
```
docker image tag imagem:latest descricao-tag
```
### Excluir uma imagem
```
docker image rm nome_imagem:versao 
```
### Baixar uma imagem
```
docker image pull
```
### Publicar imagem
```
docker image push
```
### Buildar uma imagem. Parâmetro -t serve para definir o nome da tag
* No diretório onde estiver o arquivo DockerFile
```
docker image build -t ex-simple-build . 
```
### Passando um build arg / variáveis de ambiente no comento da construção da imagem
```
docker image build --build-arg S3_BUCKET=myapp
```
### Inspecionar um aspecto específico da imagem
```
docker image inspect --format="{{index .Config.Labels \"maintainer"}}" ex-build-arg
```

### Executando o container e mapeando o diretório (pwd) para dentro do /app
* Remapeando a porta 8000 para acessar a porta 80
```
docker container run -it -v $(pwd):/app -p 80:8000 --name python-server ex-build-dev
```
### Montando um container para ler um volume de outro container 
```
docker container run -it --volumes-from=python-server debian cat /log/http-server.log
```

### Enviar uma imagem para o dockerhub
```
docker image tag ex-simple-build dockercod3r/simple-build:1.0 
docker login --username=login
docker image push dockercod3r/simple-build:1.0
```

### Listar redes 
```
docker network ls 
```

### Container sem rede
```
docker container run --net none alpine
```
