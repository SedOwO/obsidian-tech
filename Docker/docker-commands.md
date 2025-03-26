Docker stuff
### Docker commands
#### `pull`
```bash
sudo docker pull {name}:{version}
```

#### List `images`
lists all the docker images in the local machine
```bash
sudo docker images
```

#### List all the running processes
```bash
sudo docker ps

# shows all the container that has ever run/running
sudo docker ps -a
```

### `run` the docker image
`run` command runs the docker images.
If the docker image is not present, then it pulls the docker image an then runs it
```bash
sudo docker run {name}:{version}

# to detach from the terminal
sudo docker run -d {name}:{version}

# port binding
sudo docker run -p {HOST_PORT}:{CONTAINER_PORT} {name}:{version}

# to name a container
sudo docker run --name {NAME_OF_CONTAINER} {name}:{version}
```

#### `stop` the docker processes
```bash
sudo docker stop {name} <or> {process_id}
```

#### `build` the docker file
```bash
sudo docker build -t myapp .
```

#### `tag` docker file
```bash
sudo docker tag {local_image}:{version} your-dockerhub-username/{image_name}:{version}
```

#### `push` the docker file
```bash
sudo docker push your-dockerhub-username/image_name}:{version}
```
#### information about docker-compose.yaml file: [[docker-compose]]

#### setup *nginx* server using docker: [[docker-nginx]]
