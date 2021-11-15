The example project for StringBoot service

<div align="center">
    <img src="./assets/images/spring_boot_icon.png"/>
</div>

## Getting Started

## Project structure
```
.
├── hello-world
│   ├── Dockerfile
│   ...
├── docker-compose.yaml
|
└── README.md
```

## Prerequisites
- Make sure that you have Docker and Docker Compose installed
  - Windows or macOS:
    [Install Docker Desktop](https://www.docker.com/get-started)
  - Linux: [Install Docker](https://www.docker.com/get-started) and then
    [Docker Compose](https://github.com/docker/compose)

## Start infrastructure

```shell script
$ docker-compose -f ./docker-compose-infrastructure.yml -p spring-boot-infrastructure up -d
```

## Start services
### Start services in local

- Build project
```shell script
$ ./mvnw clean package
$ cd hello-word
$ ../mvnw spring-boot:run
...
```

### Start services in docker 

```shell script
$ docker-compose -f ./docker-compose-service.yml -p spring-boot-service up -d
```

## Run testing

```shell script
curl http://localhost:8081/greet?name=World
```

## Stop project

- Kill project if start in local mode
- Stop infrastructure & services in docker

```shell script
$ docker-compose -f ./docker-compose-infrastructure.yml -p spring-boot-infrastructure down
$ docker-compose -f ./docker-compose-service.yml -p spring-boot-service down
```

## Contribute

## Reference
- https://github.com/grpc/proposal/blob/master/A27-xds-global-load-balancing.md
- https://grpc.io/blog/grpc-load-balancing/
- https://salmaan-rashid.medium.com/grpc-xds-loadbalancing-a05f8bd754b8
- https://confluence.zalopay.vn/display/Accounting/Look-aside+load+balancing
- https://cloud.google.com/traffic-director/docs/proxyless-overview
- https://www.envoyproxy.io/docs/envoy/latest/api-docs/xds_protocol
- https://programmer.group/grpc-service-discovery-amp-load-balancing.html
- https://www.envoyproxy.io/docs/envoy/latest/api-docs/xds_protocol#xds-protocol-ads
- https://www.envoyproxy.io/docs/envoy/latest/configuration/overview/xds_api#config-overview-management-server