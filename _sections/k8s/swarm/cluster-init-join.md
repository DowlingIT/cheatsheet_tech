---
title: Init & Join
subtopic: swarm
group: Cluster Management
order: 1
---

#### Standing up a cluster

```bash
docker swarm init --advertise-addr 192.168.1.10
docker swarm join-token worker           # print worker join command
docker swarm join-token manager            # print manager join command
docker swarm join --token SWMTKN-... 192.168.1.10:2377
```
