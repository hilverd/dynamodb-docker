# Amazon DynamoDB in Docker

This project lets you run the
[downloadable version](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.html)
of [Amazon DynamoDB](https://aws.amazon.com/documentation/dynamodb/) in Docker.

See [hilverd/dynamodb](https://hub.docker.com/r/hilverd/dynamodb/) on Docker Hub.

## Usage

```
docker run -p 127.0.0.1:8000:8000 hilverd/dynamodb
```

To confirm things are working, open DynamoDB's [Web Shell](http://localhost:8000/shell/). To learn
more, you can follow
[Getting Started with Amazon DynamoDB](http://docs.aws.amazon.com/amazondynamodb/latest/gettingstartedguide/Welcome.html).

### Storing databases on the host

Databases are stored under `/databases` inside the container. You may want to mount a host directory
to this location:

```
docker run -p 127.0.0.1:8000:8000 -v /path/to/my/dynamodb/databases:/databases hilverd/dynamodb
```

### Custom options

By default, the `-sharedDb` option is set when you start a container. For other options, do

```
docker run --rm hilverd/dynamodb -help
```
