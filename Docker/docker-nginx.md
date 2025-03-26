
#### Run the nginx docker container
```bash
# run the docker container with name=nginx-base
sudo docker run -d --name nginx-base -p 80:80 nginx:latest
```
#### Get the configuration file from the docker container
```bash
# copies the default.conf file(from the docker container) to the desktop
sudo docker cp nginx-base:/etc/nginx/conf.d/default.conf ~/Desktop/default.conf
```
#### After editing **copy** the default.conf file back inside the container
```bash
# copy the file back the to the container
sudo docker cp ~/Desktop/default.conf nginx-base:/etc/nginx/conf.d/
```
#### Useful nginx-commands
**can be used using the `exec`  command**
```bash
# general syntax
sudo docker exec <docker-container name> <nginx-commands>
```


[[nginx-commands]] : all the basic docker commands are here

