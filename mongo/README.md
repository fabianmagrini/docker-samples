# Using Docker to deploy MongoDB

Using Docker to deploy MongoDB as a container and interact with it using the shell client.

## Prerequisites

* [Docker](https://www.docker.com/products/docker-desktop)

## Downloading the Latest MongoDB Docker Image

```sh
docker pull mongo
docker pull mongo:latest
docker pull mongo:4.2.8
```

## Deploying MongoDB as a Container

Run the container in detached mode. Map the container [ports](https://docs.mongodb.com/manual/reference/default-mongodb-port/) with host ports so that can access the database from the host.

```sh
docker run -d -p 27017-27019:27017-27019 --name mongodb mongo:4.2.8
```

## Interact with the MongoDB Container

```sh
docker exec -it mongodb bash
```

Launch the MongoDB shell client:

```sh
mongo
```

List databases:

```sh
show dbs
```

Create a new database and collection:

```sh
use footballfan
db.feed.save({ name: "TheWorldGame", url: "https://foo" })
db.feed.save({ name: "TheGuardian", url: "https://bar" })
```

Query for data:

```sh
db.feed.find({ name: "TheWorldGame" })
```

Exit the MongoDB shell client:

```sh
exit
```

Exit the Container:

```sh
exit
```

## Cleanup

```sh
docker stop mongodb
docker rm mongodb
```
