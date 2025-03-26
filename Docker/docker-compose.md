#### uses **`.yaml`** file
sample docker-compose file
```yaml
version: '3'  
services:  
  website:  
    image: nginx:latest  
    container_name: github_frontend  
    volumes:  
      - ./build:/usr/share/nginx/html  
    ports:  
      - "3000:80"  
    restart: always
```

#### run the docker compose file
```bash
sudo docker-compose up -d --force-recreate
```

#### remove all the docker containers
```bash
docker-compose down --volumes
docker system prune --all --volumes --force
```