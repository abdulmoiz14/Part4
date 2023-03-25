# Part4
**Creating a new Docker network named "my_network" using the bridge driver.**
```
docker network create --driver bridge my_network
docker network ls
```
**Output**<br />
![Screenshot (59)](https://user-images.githubusercontent.com/65711565/227738562-cb2bae42-a098-41ac-8f75-5359ebac4b8b.png)
## Nginx 
**Creating a new Docker container using the "nginx" image and connect it to the "my_network" network. Name the container "nginx_container".**
```
docker run -it -d --name nginx_container -p 8080:80 --network my_network nginx
```
**Output**<br />
![Screenshot (60)](https://user-images.githubusercontent.com/65711565/227738923-a32f7021-30a0-4a0f-8634-80910b6364ab.png)
**use this command to display information about the "my_network" network.**
```
docker network inspect my_network
```
**Output**<br />
![Screenshot (61)](https://user-images.githubusercontent.com/65711565/227739023-c066ec3f-5319-4f90-9794-2d528b0ad0fe.png)
**Verify that the "nginx" default page is accessible on your host machine using this IP.**
```
http://localhost:8080
```
**Output**<br />
![Screenshot (63)](https://user-images.githubusercontent.com/65711565/227739924-fa5e6fee-7f0c-4b30-a4cf-952ecaf97d72.png)

## Httpd
**Creating a new Docker container using the "httpd" image and connect it to the "my_network" network. Name the container "httpd_container".**
```
docker run -it -d --name httpd_container -p 8081:80 --network my_network httpd
```
**Output**<br />
![Screenshot (65)](https://user-images.githubusercontent.com/65711565/227740038-ee678be0-b9e9-4a35-9f0b-22a5069e3265.png)

**Verify that the "httpd" default page is accessible on your host machine using this IP.**
```
http://localhost:8081
```
**Output**<br />
![Screenshot (64)](https://user-images.githubusercontent.com/65711565/227739918-da8f1ef7-0d24-4418-81c5-1c40956989d7.png)
**use this command to display information about the "my_network" network.**
```
docker network inspect my_network
```
**Output**<br />
![Screenshot (62)](https://user-images.githubusercontent.com/65711565/227739912-608b7bb7-3fa7-4811-b066-6901a7446d43.png)
### Stopping and removing the httpd_contaianer.
**first disconnect httpd_container from my_network.**
```
docker network disconnect httpd_container my_network
```
**Now stop the running httpd_container**
```
docker stop httpd_container
```
**Remove the httpd_container.**
```
docker rm httpd_container
```
**Output**<br />
