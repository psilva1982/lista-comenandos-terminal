## MODO BRIDGE                       

### Criar uma nova rede
```
docker network create --driver bridge nome_rede
```
### Listar redes
```
docker network ls 
```
### Inspecionar a rede 
```
docker network inspect inspect nome_rede
```
### Configurar a conexão entre 2 redes distintas
```
docker network connect rede1 rede2
```
### Remover a conexão entre 2 redes distintas
```
docker network disconnect rede1 rede2
```

---

## MODO HOST                           

### Modo host
```
docker container run -d --name nomecontainer --net host nomeimagem
```