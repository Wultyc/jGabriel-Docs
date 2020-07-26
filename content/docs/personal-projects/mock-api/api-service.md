---
title: "API Service"
weight: 2
github: ""
bookCollapseSection: false
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookComments: true
---
The API Service it the main module of the application. Is here where all logic related with mocking is stored.

## Basic usage
Before start using is necessary to install the service on a server. There is two different formats for the installation:

1. Using Docker containers. For this in only needed Docker installed and running in the system and a good internet connection.
2. Using a tradicional installation. For this is necessary to have:
    - Servidor Web Nginx ou Apache com serviço *Rewrite Engine*
    - PHP na versão 7.2.5
    - Um sistema de gestão base de dados suportado nativamente pelo Laravel
    - Composer
    - Node JS
    - NPM
    - Git

### Installation
There is three ways to install the service:
- Using a pre built image from Docker Hub (recommended).
- Build your own image. This can be useful if you want to personalize the service.
- Install the service in your server manually.

{{< tabs "installation" >}}

{{< tab "Download from Docker Hub" >}}
Download abd run the image on your system.
```bash
docker pull wultyc/mockapi:latest
docker run -p 8080:80 -dt wultyc/mockapi
```
The flag ```-p 8080:80``` is used to create a bind between the port 8080 of the host machine and the port 80 of the container.  
To access the shell you should replace the flag ```-dt``` with ```-it```

{{< /tab >}}

{{< tab "Build the Docker Image" >}}
1. Clone the GIT repository of the docker build
  ```bash
  git clone -b docker https://github.com/Wultyc/mock-api.git mock-api
  ```
2. Change your terminal to clone folder and build the image.
  ```bash
  cd mock-api
  docker build --tag wultyc:mockapi .
  ```
  The tag can be changed in this step but you have to remember it for the next ones.
3. Run container
  ```bash
  docker run -p 8080:80 -dt wultyc:mockapi 
  ```
  The flag ```-p 8080:80``` is used to create a bind between the port 8080 of the host machine and the port 80 of the container.  
  To access the shell you should replace the flag ```-dt``` with ```-it```
{{< /tab >}}

{{< tab "Tradicional Installation" >}}
1. Configure your webserver and your Database Management System (DBMS)
2. Create a database for the service
3. Download the application. Here you can choose:
  - Download the last stable release available from the [release page](https://github.com/Wultyc/mock-api/releases/) on the repository and copy the content to the root of your webserver.
  - Clone the repo to the root of the webserver.
  ```bash
  https://github.com/Wultyc/mock-api.git /path/to/webserver/root/
  ```
  This way you can get the latest changes by making a ```git pull```

  {{< hint danger >}}
  This method to get the development version can be unstable and should not be used in production environment.
  {{< /hint >}}
4. Change the webserver root to the ```public``` folder inside the cloned folder
5. On the root of the cloned folder run this commands
  ```bash
  cp .env.example .env
  php artisan key:generate
  ```
6. Complete the ```.env``` file with the database credentials
7. Install the dependencies, migrate the database and build the Vue.JS frontend
  ```bash
  composer install
  php artisan migrate:fresh
  npm install
  npm run dev
  ```
{{< /tab >}}

{{< /tabs >}}

{{<figure src="/images/mock-api/docker_hub_dw.png" caption="Executing the service from the image downloaded from Docker Hub" >}}

After installation is possible to start using the service immediately. For this you just need to make a POST request to create an endpoint and retrieve it with a GET request on the same endpoint.

### Endpoints
An endpoint in this service can be anything inside the path ```/api/``` excepting ```/api/mgmt/``` that is used to make management operation on the service. 

### HTTP verbs available an its uses
There are available 5 HTTP verbs.  
* [GET]    Return the payload stored during the endpoint creation.
* [POST]   Create an endpoint storing the payload and query string on the database. The endpoints should be unique.
* [PUT]    Updates the payload and query string stored in the database.
* [DELETE] Mark an endpoint as deleted. This disables the endpoint without deleting it. To permanently delete an endpoint send the following query parameter ```MockAPiForceDelete=true```. This operation is irreversible!
* [PATCH]  Remove the deleted flag of an endpoint.

## Mock API Management
The management resource are available inside ```/api/mgmt/```
* [GET]  List all stored endpoints endpoints. To get the details of a specific endpoint, you just need to insert it at the end of the URL: ```/api/mgmt/{endpoint}```
* [POST] Creates multiple endpoints at once. The payload for this request should use the following format.
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
The response will be something similar with this
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
> The response of this example means that the first endpoint was successful stored but the second one not. This usually occurs because the specific endpoint was already stored.