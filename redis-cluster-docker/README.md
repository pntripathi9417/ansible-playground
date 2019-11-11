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

```
cd ansible
ansible-playbook provision_redis_cluster.yaml
```
