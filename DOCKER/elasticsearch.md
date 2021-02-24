1.  PULL IMAGE

    docker pull elasticsearch:7.7.0

2.  RUN

    docker run -d --name es -p 9200:9200 -p 9300:9300 e ES_JAVA_OPTS="-Xms512m -Xmx512m" -e "discovery.type=single-node" elasticsearch
    docker ps

3.  CONFIG

    docker exec -it es /bin/bash
    vi coinfig/elasticsearch.yml

>     cluster.name: "docker-elastic-104"
>     network.host: 0.0.0.0
>     node.name: node0
>     http.host: 0.0.0.0
>     http.cors.enabled: true
>     http.cors.allow-origin: "*"

4.  Others

> Folder Mapping:
> -v /dockerfile/elasticsearch/plugins:/usr/share/elasticsearch/plugins \
> -v /dockerfile/elasticsearch/data:/usr/share/elasticsearch/data \
> -v /dockerfile/elasticsearch/logs:/usr/share/elasticsearch/logs \
>
> Kibana:
> docker pull kibana:7.7.0
> docker run --link es:elasticsearch -p 5601:5601 -d kibana:7.7.0

![火狐截图_2021-02-24T06-12-38.031Z.png][1]

[1]: http://www.mmtech.top/usr/uploads/2021/02/2407611317.png
