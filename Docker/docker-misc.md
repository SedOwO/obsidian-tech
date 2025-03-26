
### MySQL-container
```shell
# You need to specify one of the following as an environment variable:
    #- MYSQL_ROOT_PASSWORD
    #- MYSQL_ALLOW_EMPTY_PASSWORD
    #- MYSQL_RANDOM_ROOT_PASSWORD
sudo docker rm -f doctor-mysql
sudo docker run --name doctor-mysql -e MYSQL_ROOT_PASSWORD=12345 -d -p 3306:3306 mysql:8.0
```
#### Enter the db
```shell
docker exec -it doctor-mysql mysql -u root -p
```

## Elasticsearch-container
```shell
docker run -d --name elasticsearch \
  -e "discovery.type=single-node" \
#  -e "ELASTIC_USERNAME=elastic" \
#  -e "ELASTIC_PASSWORD=yourpassword" \
  -e "cluster.name=cluster1" \
  -p 9200:9200 \
  docker.elastic.co/elasticsearch/elasticsearch:7.17.27


docker run -d --name elasticsearch \
  -e "discovery.type=single-node" \
  -e "cluster.name=cluster1" \
  -p 9200:9200 \
  docker.elastic.co/elasticsearch/elasticsearch:7.17.27

```

