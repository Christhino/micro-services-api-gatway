# microservices-apigatway-rabbitmq

(api-gateway) et 3 microservices (user/product/client)

RabbitMQ comme file d'attente de messagerie, donc si un microservice tombe en panne, il recevra des messages lorsqu'il se rétablira.

  
### Installing

- Clone the repository

```
git clone https://github.com/Christhino/micro-services-api-gatway.git
```

- Install dependences de l' api-gateway

```
cd api-gateway

npm install
```
- Install dependences de chaque microservice (user, product and client)
```
cd services/<microservice>

npm install
```

### Environment variables

Ce projet utilise les variables d'environnement suivantes :
##### api-gateway
```
# Port
PORT=8000

# User service
USER_SERVICE_URL='http://localhost:8001'

# Client service
CLIENT_SERVICE_URL='http://localhost:8002'

# Product service
PRODUCT_SERVICE_URL='http://localhost:8003'
```

##### microservice
```
# Database
DB=''

# Service port
PORT=8001

# RabbitMQ configuration
MESSAGE_BROKER_URL=''
```

### Running the project

```
cd rabbitmq
docker-compose up -d
```

Development mode
```
cd services/<microservice>

npm run dev
```
Production mode
```
cd services/<microservice>

npm start
```

- Start  api-gateway
```
cd api-gateway

npm start

or

npm run dev
```
Navigate to `http://localhost:8000`

### Endpoints

`http://localhost:8000/user/list`

`http://localhost:8000/user/ping-client`

`http://localhost:8000/user/ping-product`


`http://localhost:8000/client/list`

`http://localhost:8000/client/ping-user`

`http://localhost:8000/client/ping-product`

  

`http://localhost:8000/product/list`

`http://localhost:8000/product/ping-user`

`http://localhost:8000/product/ping-client`

