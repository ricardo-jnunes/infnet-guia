# Estudo de Pós-graduação em Arquitetura de Integração e Serviços

Essa é uma aplicação para gerenciar seus estudos no Infnet - Guia de Estudos.


## Getting Started
Estudo de caso com Docker Swarm para a máteria Integração Contínua, DevOps e Computação em Nuvem.

## Documentos e evidências
Informações, documentação e evidências da execução deste projeto podem ser encontrado aqui [PROJETO DA DISCIPLINA - RICARDO JOSÉ NUNES - Integração Contínua, DevOps e Computação em Nuvem](https://github.com/ricardo-jnunes/infnet-guia/blob/main/docs/Ricardo_José_Nunes_Integração_Contínua_DevOps_e_Computação_em_Nuvem_pd.pdf).

## Best Practices

Informações de boas práticas do uso de Node.js e Docker podem ser encontrado aqui  [Node.js Best Practices](https://github.com/nodejs/docker-node/blob/main/docs/BestPractices.md). 
## Docker

A aplicação é executada com Docker:
```
# Comando se pretende rodar o build e executar a aplicação
docker-compose up
```

### Docker Swarm

Usando o docker-compose-stack.yml para definir os serviços e réplicas em YAML para Swarm.

```
docker stack deploy -c docker-compose-stack.yaml infnet-guide-stack # Deploy Stack

docker stack rm infnet-guide-stack # Apagar Stack
```
#### Docker Swarm Commands

Comandos para os EC2
```
1  sudo yum install Docker
2  sudo yum install docker
3  sudo service docker start
4  docker ps
5  sudo usermod -a -G docker ec2-user
6  sudo service docker start
```

Comandos para o Manager
```
docker node ls # Lista os nós configurados
docker swarm join-token [OPTIONS] (worker|manager) # Solicitar token para inserir novos nós/nodes

# Ver os serviços
docker stack services infnet-guide-stack

# Logs dos serviços
docker service logs infnet-guide-stack_grafana
```

#### AWS - Montando um Volume
```
sudo mkfs -t xfs /dev/sdf
sudo mkdir /mnt/data
sudo mount /dev/sdf /mnt/data

# Dar permissão ao usuário
sudo chgrp -R ec2-user /mnt/data 
sudo chown -R ec2-user:ec2-user /mnt/data/

# Crie os diretórios necessários
mkdir /mnt/data/prometheus_data
mkdir /mnt/data/grafana_data
mkdir /mnt/data/mysql_data
```
