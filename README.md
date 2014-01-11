## MongoDB Dockerfile


This repository contains **Dockerfile** of [MongoDB](http://www.mongodb.org/) for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/dockerfile/mongodb/) published to the public [Docker Registry](https://index.docker.io/).


### Dependencies

* [dockerfile/ubuntu](https://github.com/dockerfile/ubuntu)


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://index.docker.io/u/dockerfile/mongodb/) from public [Docker Registry](https://index.docker.io/): `docker pull dockerfile/mongodb`

   (alternatively, you can build an image from Dockerfile: `docker build -t="dockerfile/mongodb" .`)


### Usage

#### Run `mongod`

    docker run -p 27017:27017 dockerfile/mongodb

#### Run `mongod` w/ HTTP support (requires firewall on port 28017)

    docker run -p 27017:27017 -p 28017:28017 dockerfile/mongodb --rest

#### Run `mongo`

    docker run -i -rm -t -entrypoint="mongo" dockerfile/mongodb
