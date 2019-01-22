# Catálogo 'Fast Food' de Serviços Docker

## Descrição
Este Repositório contem os meus scripts de inicialização rápida dos serviços Docker que eu mais costumo usar.  
A idéia é ter um arsenal de serviços prontos para uso sem muita complicação, bastando apenas executar um único comando para subir o serviço, e outro para desliga-lo.  
Esse catálogo tem serviços diversos como bancos de dados, serviços de mensageria, cache, armazenamento web, etc., bastando um comando do tipo npm run {nome do serviço} para inicia-los.  

### Acesso aos containers e seus serviços
Todos os containers estão usando como usuário principal estas credenciais:
```bash
username:   root
password:   rootpass
```
## Requisitos mínimos do sistema
Esta é a lista dos softwares que eu uso e suas versões. É bem provável que funcione perfeitamente mesmo com versões um pouco anteriores a essas.

<a href="https://nodejs.org/en/">Nodejs 8.11.3</a> ou superior  
<a href="https://nodejs.org/en/">npm 6.5.0</a> ou superior  
 <a href="https://www.docker.com/get-started">Docker 18</a> ou superior

## Lista de serviços e como usá-los

### Redis
Principais casos de uso: Serviço de banco de dados não relacional, cache e broker.

Para iniciar:
```bash
npm run redis
```

Para desligar:
```bash
npm run stop:redis
```

### Minio
Principais casos de uso: Serviço de armazenamento de arquivos para Web

Para iniciar:
```bash
npm run minio
```

Para desligar:
```bash
npm run stop:minio
```

### Apache ActiveMQ
Principais casos de uso: Message Broker

Para iniciar:
```bash
npm run activemq
```

Para desligar:
```bash
npm run stop:activemq
```

Para acessar o serviço via navegador web:
```bash
http://localhost:8161
```

### RabbitMQ
Principais casos de uso: Message Broker

Para iniciar:
```bash
npm run rabbitmq
```

Para desligar:
```bash
npm run stop:rabbitmq
```

Para acessar o serviço via navegador
```bash
http://localhost:8080
```

### MongoDB
Principais casos de uso: Banco de Dados não-relacional

Para iniciar:
```bash
npm run mongodb
```

Para desligar:
```bash
npm run stop:mongodb
```

Para acessar o container:
```bash
npm run shell:mongodb
```

### Microsoft Sql Server (Linux)
Principais casos de uso: Banco de dados Relacional

Para iniciar uma instancia que PERSISTE os dados no repositório:
```bash
npm run mssql:persistent
```

Para iniciar uma instancia simples (não salva os dados)
```bash
npm run mssql:test
```

Para desligar:
```bash
npm run stop:mssql
```

Para acessar o container:
```bash
npm run shell:mssql
```

### Postgre-Sql
Principais casos de uso: Banco de dados Relacional (O melhor de todos!)

Para iniciar uma instancia que PERSISTE os dados no repositório:
```bash
npm run postgre:persistent
```

Para iniciar uma instancia simples (não salva os dados)
```bash
npm run postgre:test
```

Para se conectar via terminal ao container ( Necessário postgresql-client )
```bash
npm run shell:postgre
```

Para desligar:
```bash
npm run stop:postgre
```

# Parar todos os containers em execução

Para parar todos os containers em execução e liberar seus recursos:
```
npm run stop:all
```
