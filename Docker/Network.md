`docker network ls` -  получить список доступных сетей
`docker network create <name>` -  создать сеть
`docker network rm <name>` -  удалить сеть
`docker network connect <network> <container>` - подключает `<container>` к `<network>`
`docker network disconnect <network> <container>` - отключает контейнер от сети 