# docker-solr
Docker solr with custom core configuration (solr 6.x tested)

How to build the container with core.

1. Install Docker in you machine
2. Clone this repository
3. build the docker container eg:- docker-compose up -d
4. create `data` directory inside the core_6_x
5. create `index`, `snapshot_metadata` and `tlog` directories inside `data` directory.
6. Copy the configuration folder into container. eg: docker cp D:\docker-solr\conf-template\core_6_x [ContainerID]:/opt/solr/server/solr/mycores
7. Restart the container eg- docker restart [container ID]
8. Open browser and goto http://localhost:8983 you can see your solr core is created.

**NOTE**
* If you want to change some configuration then login into the container with root user

docker exec -it --user root [container ID] bash

* How to get your solr server IP address

docker inspect [container ID]

then find "Gateway" under networks then you will get the IP address

