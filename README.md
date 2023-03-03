# Running Ansible Semaphore using Docker

# Create the image

```bash
# clone the repo
git clone git@github.com:ansible-semaphore/semaphore.git
# build the image
cd semaphore/deployment/docker/prod
sudo docker compose -f ./docker-compose.yml build
```

## the image

```bash
sudo docker images ls | grep semaphore
```

# Running the service

## clone the repo

```bash
git clone https://github.com/i40sys/ansible-semaphore.git
```

## modify the docker-compose.yml file

Remember to modify the environment variables of the docker-compose.yml file for setting your own parameters, for instance, the administrator password.

## create directories

```bash
# go to the path where you have your docker-compose.yml
mkdir config data repos
sudo chown 1001 config data repos
```

## run the service

```bash
sudo docker compose up -d
```

# check the service

```bash
sudo docker ps
```

# check the logs

```bash	
sudo docker compose logs -f
```

# UI steps for running a playbook

1. create new project
1. add key store:
    1. none (for local)
    1. SSH private key
1. add environment: none
1. add inventory entry
1. add repository entry
1. create task template
1. run task
