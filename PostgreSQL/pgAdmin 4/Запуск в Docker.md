###### Скачать образ pgadmin4
`docker pull dpage/pgadmin4`

###### Запуск контейнера 
```sh
sudo docker run -d \
-p 5050:80 \
--name pgadmin4-dev \
--net=UniHelper_network \
-e "PGADMIN_DEFAULT_EMAIL=email@mail.com" \
-e "PGADMIN_DEFAULT_PASSWORD=password" \
dpage/pgadmin4
```