# Estudo de Pós-graduação em Arquitetura de Integração e Serviços

Essa é uma aplicação para gerenciar seus estudos no Infnet - Guia de Estudos.


## Getting Started
Estudo de caso com Docker Swarm para a máteria Integração Contínua, DevOps e Computação em Nuvem.


## Best Practices

Informações de boas práticas do uso de Node.js e Docker pode ser encontrado aqui [Node.js Best Practices](https://github.com/nodejs/docker-node/blob/main/docs/BestPractices.md).

## Docker

A aplicação é executada com Docker:
```
# Comando se pretende rodar buildar e executar a aplicação
docker-compose up

```

### Docker Swarm

Usando o docker-compose-stack.yml para definir os serviços e réplicas em YAML para Swarm.

```
docker stack deploy -c docker-compose-stack.yml infnet-studies-stack
```
