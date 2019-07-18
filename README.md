# Catálogo 'Fast Food' de Serviços Docker

## Descrição
Este Repositório contem os meus scripts de inicialização rápida dos serviços Docker que eu mais costumo usar.  
A idéia é ter um arsenal de serviços prontos para uso sem muita complicação, bastando apenas executar um único comando para subir o serviço, e outro para desliga-lo.  
Esse catálogo tem serviços diversos como bancos de dados, serviços de mensageria, cache, armazenamento web, etc., bastando um comando do tipo npm run {nome do serviço} para inicia-los.  

## Vantagens
Com esse Catálogo, você pode usar qualquer um dos serviços inclusos diretamente no seu computador SEM PRECISAR INSTALAR NEM CONFIGURAR nenhum servidor, salvando assim os preciosos recursos de memória, espaço  e tempo de processador, pois você só usará os serviços quando precisar, e os desligará ao terminar, de maneira que seu sistema operacional não será afetado em absolutamente nada.

### Acesso aos containers e seus serviços
Quase todos os containers estão usando como usuário principal estas credenciais:
```bash
username:   root
password:   rootpass
```
## Requisitos mínimos do sistema
Esta é a lista dos softwares que eu uso e suas versões. É bem provável que funcione perfeitamente mesmo com versões um pouco anteriores a essas.

<a href="https://nodejs.org/en/">Nodejs 8.11.3</a> ou superior  
<a href="https://nodejs.org/en/">npm 6.5.0</a> ou superior  
 <a href="https://www.docker.com/get-started">Docker 18</a> ou superior

Obviamente, estou usando Linux.

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
### Redis Commander
Uma GUI WEB para o Redis

Para iniciar:
```
npm run redis:gui
```

Para desligar:
```
npm run stop:redis:gui
```

Para acessar:
```
http://localhost:8081
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

Dados de conexão:
```bash
username: SA
password: !SenhaDificil%
schema: tempdb
```

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

### Elasticsearch
Principais casos de uso: Banco de dados indexado não relacional baseado em requisições http

Para iniciar uma instancia simples (não salva os dados)
```bash
npm run elasticsearch
```

Para desligar:
```bash
npm run stop:elasticsearch
```

### Kibana
Principais casos de uso: geração de gráficos com base em dados indexados no Elasticsearch

Para iniciar uma instancia simples
```bash
npm run kibana
```

Para desligar:
```bash
npm run stop:kibana
```

### Spotfy Downloader
Um  <a href="https://github.com/ritiek/spotify-downloader">projeto interessante</a> que achei quando procurei formas de baixar playlists inteiras direto do Spotfy.  

Principais casos de uso: Recreação. Este Docker faz o Download de playlists inteiras do spotfy

Comece baixando o índice da playlist dando o link (copie do navegador) como parâmetro
```bash
npm run spotfy:index {URL-DA-PLAYLIST}

exemplo:
npm run spotfy:index https://open.spotify.com/playlist/4fiw57jeMepokneIvlu09q
```


Depois de baixar o índice, é só baixar tudo de uma vez. ja convertendo em mp3 automagicamente.
```bash
npm run spotfy:dl
```
Todas as músicas estarão na pasta 'musicas' que será gerada na raiz desse repositório.  
Este container não precisa ser parado, pois está configurado para morrer automaticamente ao terminar o download das músicas.

### Sonarqube (Serviço de análise de qualidade de código)
[Sonarqube](https://www.sonarqube.org/) é um serviço que recebe resultados de scaneamentos locais com o [sonar-scanner](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner) e analisa o código em varios aspectos interessantes.

Para levantar esse serviço, entre no diretório sonarqube deste repositório, e então execute o comando:
```bash
docker-compose up
```
### Pilha LAMP
Ajuste no argumento -v do script para onde o diretorio /var/www/html deve apontar na maquina host. O padrão é $PWD, ou seja, irá ler como diretorio root do apache o diretorio atual.

Para o [PHP 5](https://hub.docker.com/r/tutum/lamp/):
```
npm run lamp:php5
```

Para o [PHP 7](https://hub.docker.com/r/fauria/lamp/):
```
npm run lamp:php7
```


# Parar todos os containers em execução

Para parar todos os containers em execução e liberar seus recursos:
```
npm run stop:all
```
