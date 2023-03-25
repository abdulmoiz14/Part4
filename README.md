# Part4
**Creating a new Docker network named "my_network" using the bridge driver.**
```
docker network create --driver bridge my_network
docker network ls
```
**Output**<br />
![Screenshot (59)](https://user-images.githubusercontent.com/65711565/227738562-cb2bae42-a098-41ac-8f75-5359ebac4b8b.png)
**Creating a new Docker container using the "nginx" image and connect it to the "my_network" network. Name the container "nginx_container". **
```
docker run -it -d --name nginx_container --network my_network nginx
```
**Output**<br />
![Screenshot (60)](https://user-images.githubusercontent.com/65711565/227738923-a32f7021-30a0-4a0f-8634-80910b6364ab.png)
**use this command to varify the containers in the network.**
```
docker network inspect my_container
```
