# TESA Top gun Rally #16 (การประชันทักษะด้านสมองกลฝังตัว ครั้งที่ 16)

## Server Programming and Configuration.

### MQTT Dashboard

> MQTT Dashboard

## วันที่ 2 Docker compose ##
### เรียนรู้ ###
1. เรียนรู้ docker compose
2. กำหนด topic/subscribe ของ MQTT

![EMQX](./assets/CDTI%20Topgun2022-broker.png)


## Docker Compose ##
**Compose** is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.

A docker-compose.yml looks like this:
```Docker
version: '3'

services:

  emqx-mqtt:
    image: emqx/emqx:5.0.7-elixir
    container_name: emqx
    networks:
      - my-network
    volumes:
      - ./emqx_data:/opt/emqx/data
      - ./emqx_log:/opt/emqx/log
    ports:
      - 1883:1883
      - 8083:8083 
      - 8084:8084 
      - 8883:8883 
      - 18083:18083 

  node-red:
    image: nodered/node-red
    container_name: node-red
    networks:
      - my-network
    volumes:
      - ./node_red_data:/data
    ports:
      - 1880:1880

networks:
  my-network:

```

## run compose ## 

```bash
$ docker compose up
                
[+] Running 3/3
 ⠿ Network docker-topgun-compose_my-network  Created                                                  0.0s
 ⠿ Container emqx                            Created                                                  0.1s
 ⠿ Container node-red                        Created                                                  0.0s
Attaching to emqx, node-red

```


## Top Gun Rally CDTI 2022 Day 2 Excercise ##

1. Design MQTT Topics and Subscription.
2. 

