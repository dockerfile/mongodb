## MongoDB Dockerfile


This repository contains **Dockerfile** of [MongoDB](http://www.mongodb.org/) for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/dockerfile/mongodb/) published to the public [Docker Registry](https://index.docker.io/).


### Dependencies

* [dockerfile/ubuntu](https://github.com/dockerfile/ubuntu)


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://index.docker.io/u/dockerfile/mongodb/) from public [Docker Registry](https://index.docker.io/): `docker pull dockerfile/mongodb`

   (alternatively, you can build an image from Dockerfile: `docker build -t="dockerfile/mongodb" .`)


### Usage

    docker run -i -t dockerfile/mongodb bash

#### Run `mongod`

    docker run dockerfile/redis mongod

(Alternatively, use [dockerfile/mongod](https://github.com/dockerfile/mongod) executable image.)

#### Run `mongo`

    docker run dockerfile/redis mongo

(Alternatively, use [dockerfile/mongo](https://github.com/dockerfile/mongo) executable image.)
