### Задание 1 - Docker CLI

```
sudo docker run -it busybox ping netology.ru -c 7
sudo docker ps -a
sudo docker rename f5b8c981bff9  pinger
sudo docker ps -a
sudo docker logs pinger
sudo docker start pinger
sudo docker logs pinger
sudo docker rm pinger
sudo docker rmi busybox
```

### Задание 2 - Environment Variables

```
sudo docker run -td -it --env NAME=Иван --env SURNAME=Шулаев node:20.8.0
console.log(process.env.NAME, process.env.SURNAME)
sudo docker ps -a
sudo docker rename trusting_brattain mynode
sudo docker stop mynode
sudo docker image ls -a
sudo docker rmi node:20.8.0
```

### Задание 3 - Volumes

```
sudo docker run -td --name first_node -v /home/adminpy/Desktop/data:/var/first/data node:20.8.0
sudo docker run -td --name second_node -v /home/adminpy/Desktop/data:/var/second/data node:20.8.0
sudo docker ps -a
sudo docker exec -it first_node bash
touch /var/first/data/test.txt
sudo docker exec -it second_node bash
ls -l /var/second/data
sudo docker ps -a 
sudo docker stop first_node
sudo docker stop second_node
sudo docker rm first_node
sudo docker rm second_node
sudo docker images
sudo docker rmi node:20.8.0
```