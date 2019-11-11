# ipresence-tasks
The demo implements, redis-cluster, rabbitmq-cluster, mysql-cluster using ansible, vagrant, and dockers

## Installation (MacOS)
1. VirtualBox: `brew cask install virtualbox`
2. Vagrant: `brew cask install vagrant`
3. Vagrant Plugins: `vagrant plugin install vagrant-auto_network && vagrant plugin install vai`
4. Ansible: `brew install ansible`

## Setup VM

```
vagrant up
```

## redis-cluster
The demo sets up 6 redis instances - 3 master and 3 slaves

### Getting Started

#### Provision Redis Cluster
```
cd ansible
ansible-playbook provision_redis_cluster.yaml
```

#### Verify Redis Cluster

```
vagrant ssh
sudo docker ps
redis-cli -p 32779 # take port from one of the redis instance
cluster info
```

The output will look like following
```
127.0.0.1:32779> cluster info
cluster_state:ok
cluster_slots_assigned:16384
cluster_slots_ok:16384
cluster_slots_pfail:0
cluster_slots_fail:0
cluster_known_nodes:6
cluster_size:3
cluster_current_epoch:6
cluster_my_epoch:1
cluster_stats_messages_ping_sent:1764
cluster_stats_messages_pong_sent:1798
cluster_stats_messages_sent:3562
cluster_stats_messages_ping_received:1793
```

#### Debugging

1. In case `cluster_state` is `fail` try re-running `sudo docker-compose up -d --build --scale redis=6`

## rabbitmq-cluster

### Getting Started

## mysql-replication

