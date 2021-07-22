### Lê o arquivo docker-compose.yml
```
docker-compose up
```
### Executa em modo daemon
```
docker-compose -d 
```
### Lista processos 
```
docker-compose ps
```
### Executa um comando dentro da imagem
```
docker-compose exec db (ex. psql -U postgres -c '\l')
```
### Parar e remover os serviços
```
docker-compose down
```
### Para verificar os logs 
```
docker-compose logs -f -t
```
### Para verificar os logs de um serviço específico
```
docker-compose logs -f -t worker
```
### Scale
```
docker-compose up -d --scale worker=3```