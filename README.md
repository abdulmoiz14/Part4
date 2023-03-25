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
### Stopping and removing the nginx_contaianer.
**first disconnect nginx_container from my_network.**
```
docker network disconnect  my_network nginx_container
```
**Now stop the running nginx_container.**
```
docker stop nginx_container
```
**Remove the nginx_container.**
```
docker rm nginx_container
```
**Output**<br />
![Screenshot (67)](https://user-images.githubusercontent.com/65711565/227741166-d617af7d-c53c-4ae0-9d30-aa19ff070023.png)

## nginx_container_2
**Creating a new Docker container using the "httpd" image and connect it to the "my_network" network. Name the container "nginx_container_2".**
```
docker run -it -d --name nginx_container_2 -p 8082:80 --network my_network nginx
```
**Output**<br />
b2ffcbc0db3308fc7f9a7e8668315b9bfcfbf9d532d94c455318d80b0673eb43

**Verify that the "nginx" default page is accessible on your host machine using this IP.**
```
http://localhost:8082
```
**Output**<br />
![Screenshot (68)](https://user-images.githubusercontent.com/65711565/227741288-fee440d0-0ab5-4666-9772-38b56d3b0acf.png)

**use this command to display information about the "my_network" network.**
```
docker network inspect my_network
```
**Output**<br />
![Screenshot (69)](https://user-images.githubusercontent.com/65711565/227741302-1907fbb7-161d-4d25-84b3-d75d1c8a4475.png)
## Use the "docker container ls" command to display information about all running containers.
```
docker container ls
```
**Output**<br />
![Screenshot (71)](https://user-images.githubusercontent.com/65711565/227741943-373137ae-921c-43d0-829f-7e3b5302853c.png)

## Stopping and removing the all containers.
**first disconnect all containers from my_network.**
```
docker network disconnect  my_network nginx_container_2
docker network disconnect  my_network httpd_container
```
**Now stop the running all containers.**
```
docker stop nginx_container_2
docker stop httpd_container
```
**Remove the all containers.**
```
docker rm nginx_container_2
docker rm httpd_container
```
**Output**<br />
![Screenshot (70)](https://user-images.githubusercontent.com/65711565/227741657-cc9b34cc-9a95-4cbd-82cf-e138578ebd40.png)
**Cleanup: Remove the "my_network" network.**
```
docker network rm my_netwokr
```
**Use command to list all networks.**
```
docker network ls
```
**Output**<br />
![Screenshot (72)](https://user-images.githubusercontent.com/65711565/227742266-0a796be8-3898-4811-b792-de776d3473db.png)

**Create README.md file and describe your findings in markdown language.**
```
touch README.md
nano README.md
```
**Create git repo and clone it to local file.**
```
git clone https://github.com/abdulmoiz14/Part4.git
```
**copy README file to Part4 folder and push it to the github.**
```
cp README.md /Part4
git add --all
git commit -m "adding codebase to the github"
git push -u origin main
```
