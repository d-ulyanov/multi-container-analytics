# Docker-compose for analytics infrastructure scratch

![TravisCI](https://travis-ci.org/d-ulyanov/multi-container-analytics.svg?branch=master)

Here you can find high performance application that provides base functions for collecting analytics events,
transferring this events through Kafka to log storage (Yandex.ClickHouse).

Infrastructure consist of following services:

- Nginx frontend (sends cookies to user and collects events to file)
- Kafka (events queue)
- Logstash (transfer events to Kafka)
- ClickHouse (fast analytics storage)
- Grafana (for events visualisation)

## Run via docker-compose

Run stack via docker-compose:
```
docker compose up -d
```

##### Scale out in compose mode:

```
docker-compose scale apache=2
```

## Run stack in Docker Swarm

Step 0. Init swarm
```
docker swarm init
```

Step 1. Prepare docker images
```
$ docker-compose build
```

Step 2. Run stack
```
$ docker stack deploy --compose-file=docker-compose.yml my-app
```
