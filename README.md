# Docker ELK-Stack Container - Elasticsearch
_maintained by MarvAmBass_

[FAQ - All you need to know about the marvambass Containers](https://marvin.im/docker-faq-all-you-need-to-know-about-the-marvambass-containers/)

## What is it

This Dockerfile (available as ___marvambass/elasticsearch___) gives you a ready to use Elasticsearch Container for your ELK stack or something else.

View in Docker Registry [marvambass/elasticsearch](https://registry.hub.docker.com/u/marvambass/marvambass/elasticsearch/)

View in GitHub [MarvAmBass/docker-elasticsearch](https://github.com/MarvAmBass/docker-elasticsearch)

## Exports

## Running marvambass/elasticsearch Container

You can run the default elasticsearch command simply:

    docker run -d marvambass/elasticsearch

You can also pass in additional flags to elasticsearch:

    docker run -d \
    marvambass/elasticsearch \
    elasticsearch -Des.node.name="TestNode"

This image comes with a default set of configuration files for elasticsearch, but if you want to provide your own set of configuration files, you can do so via a volume mounted at /usr/share/elasticsearch/config:

    docker run -d \
    -v "$PWD/config":/usr/share/elasticsearch/config \
    marvambass/elasticsearch

This image is configured with a volume at /usr/share/elasticsearch/data to hold the persisted index data. Use that path if you would like to keep the data in a mounted volume:

    docker run -d \
    --name elasticsearch \
    -v "$PWD/esdata":/usr/share/elasticsearch/data
    marvambass/elasticsearch

## Based on

This Dockerfile is based on my [marvambass/oracle-java8](https://registry.hub.docker.com/marvambass/oracle-java8) Image.
