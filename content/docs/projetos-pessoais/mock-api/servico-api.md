---
title: "Servico API"
weight: 2
github: ""
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
O Serviço API é a parte principal da aplicação. É onde está toda a lógica relacionada com o API Mocking.

## Utilização básica
Antes de começar a utilizar o serviço é necessário instalar-lo num servidor. Os requisitos para executar a aplicação são:
* Servidor Web Nginx ou Apache com serviço *Rewrite Engine*
* PHP na versão 7.2.5
* Um sistema de gestão base de dados suportado nativamente pelo Laravel
* Composer
* Git

### Instalação
Existem 3 modos de instalar o serviço: usar uma imagem pronta do Docker Hub (recomendado), montar a própria imagem docker ou fazer uma instalação tradicional

{{< tabs "instalation" >}}

{{< tab "Download do Docker Hub" >}}
Para executar este processo basta fazer pull da imagem e executar-la
```bash
docker pull wultyc/mockapi:latest
docker run -p 8080:80 -dt wultyc/mockapi
```
O parametro ```-p 8080:80``` server para criar um túnel entre a porta ```8080``` da máquina que está a executar o container e a porta ```80``` do próprio container  
Para ter acesso à shell do container basta trocar o parametro ```-dt``` por ```-it```

{{< /tab >}}

{{< tab "Construir imagem Docker" >}}
1. Clonar branch especifica do repositório criada para o efeito
  ```bash
  git clone -b docker https://github.com/Wultyc/mock-api.git mock-api
  ```
2. Mudar o terminal para dentro da pasta clonada e construir a imagem
  ```bash
  cd mock-api
  docker build --tag wultyc:mockapi .
  ```
  A tag pode ser mudada para o que preferir, mas tem de a guardar para usar a seguir
3. Executar o container
  ```bash
  docker run -p 8080:80 -dt wultyc:mockapi 
  ```
  O parametro ```-p 8080:80``` server para criar um túnel entre a porta ```8080``` da máquina que está a executar o container e a porta ```80``` do próprio container  
  Para ter acesso à shell do container basta trocar o parametro ```-dt``` por ```-it```
{{< /tab >}}

{{< tab "Instalação tradicional" >}}
1. Configurar o servidor Web e sistema de gestão de base de dados
2. Criar uma base de dados para o serviço
3. Fazer download da aplicação. Aqui existem duas opções distintas:
  - Fazer o download da última versão estável na página de [lançamentos](https://github.com/Wultyc/mock-api/releases/) do repositório e copiar o conteúdo para o root do servidor web.
  - Fazer clone do repositório para o root do servidor
  ```bash
  https://github.com/Wultyc/mock-api.git /caminho/para o/root do/ webserver/
  ```
  Deste modo com um simples git pull poderá receber as novas atualizações

  {{< hint danger >}}
  O uso deste metodo para obter a versão beta pode causar instabilidades na aplicação e não deve nunca ser usado em ambientes de produção.
  {{< /hint >}}
4. No diretório onde se copiou os ficheiros executar os seguintes comandos
  ```bash
  cp .env.example .env
  php artisan key:generate
  ```
5. Preencher o ficheiro .env com os dados da base de dados
6. Instalar as dependências e criar as tabelas na base de dados
  ```bash
  composer install
  php artisan migrate:fresh
  ```
{{< /tab >}}

{{< /tabs >}}

{{< hint info >}}
  Devido à necessidade de fazer download de todas as dependências, as soluções baseadas em Docker podem demorar um pouco mais para fix«car operacionais na primeira execução. 
{{< /hint >}}

{{<figure src="/images/mock-api/docker_hub_dw.png" caption="Execução da do serviço apartir da imagem obtida do Docker Hub" >}}

Após a instalação concluída é possivel começar de imediato a utilizar o serviço. Para isso basta fazer um request POST para criar um endpoint e um request GET para obter o payload enviado no POST.

### Endpoints
Um endpoint neste serviço pode ser qualquer coisa dentro de ```/api/``` à exceção de ```/api/mgmt/``` que é usado para fazer algumas operações de gestão no serviço. Assim se quisermos, p.e., criar o endpoint ```/api/first-endpoint```, basta fazer um request POST para esse endpoint.

### Verbos HTTP disponíveis e as suas funcionalidades
Estão disponíveis neste momento 5 verbos HTTP.  
* [GET]    Retorna o payload enviado no request de criação do endpoint  
* [POST]   Cria um endpoint e grava na base de dados o payload e a query string enviados. Os endpoints devem ser únicos! Se precisar atualizar deve fazer um request PUT para isso.
* [PUT]    Substitui o payload e query string registados na base de dados pelo que for enviado neste request.
* [DELETE] Marca um endpoint como apagado. Isto serve para bloquear o acesso a um endpoint sem o apagar da base de dados. Se pretender efetivamente apagar o endpoint, deverá fazer o request com o query parameter ```MockAPiForceDelete=true```. Esta operação é irreversível!
* [PATCH]  Ativa um endpoint que estava marcado como apagado.

## Gestão da Mock API
São disponibilizados alguns recursos de gestão no endpoint ```/api/mgmt/```
* [GET]  Lista todas os endpoints registados. Para obter os detalhes de apenas um endpoint, basta fazer um get request para ```/api/mgmt/{endpoint}```
* [POST] Possiblita a criação de vários endpoints ao mesmo tempo. O payload deverá ter o seguinte formato
```json
[
  {
    "endpoint": "test/endpoint",
    "query": "[]",
    "payload": "{\"message\":\"Hello World :)\"}",
    "created_at": "2020-05-15T23:53:57.000000Z",
    "updated_at": "2020-05-16T11:52:43.000000Z",
    "deleted_at": "2020-05-16T11:52:43.000000Z"
  },
  {
    "endpoint": "test/endpoint/2",
    "query": "[]",
    "payload": "{\"message\":\"Hello World\"}",
    "created_at": "2020-05-16T11:18:46.000000Z",
    "updated_at": "2020-05-16T13:29:13.000000Z",
    "deleted_at": null
  },
]
```
Será retornada uma reposta semelhante à seguinte
```json
[
  {
    "test/endpoint": "ok"
  },
  {
    "test/endpoint/2": "fail"
  }
]
```
Isto significa que o primeiro endpoint foi inserido com sucesso, mas o segundo não. Normalmente isto acontece porque o endpoint já esta registado na base de dados.