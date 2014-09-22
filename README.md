## MongoDB Dockerfile


This repository contains **Dockerfile** of [MongoDB](http://www.mongodb.org/) for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/dockerfile/mongodb/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).


### Base Docker Image

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/dockerfile/mongodb/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull dockerfile/mongodb`

   (alternatively, you can build an image from Dockerfile: `docker build -t="dockerfile/mongodb" github.com/dockerfile/mongodb`)


### Usage

#### Run `mongod`

    docker run -d -p 27017:27017 --name mongodb dockerfile/mongodb

#### Run `mongod` w/ persistent/shared directory

    docker run -d -p 27017:27017 -v <db-dir>:/data/db --name mongodb dockerfile/mongodb

#### Run `mongod` w/ HTTP support

    docker run -d -p 27017:27017 -p 28017:28017 --name mongodb dockerfile/mongodb mongod --rest --httpinterface

#### Run `mongod` w/ Smaller default file size

    docker run -d -p 27017:27017 --name mongodb dockerfile/mongodb mongod --smallfiles

#### Run `mongo`

    docker run -it --rm --link mongodb:mongodb dockerfile/mongodb bash -c 'mongo --host mongodb'

##### Usage with VirtualBox (boot2docker-vm)

_You will need to set up nat port forwarding with:_  

    VBoxManage modifyvm "boot2docker-vm" --natpf1 "guestmongodb,tcp,127.0.0.1,27017,,27017"

This will allow you to connect to your mongo container with the standard `mongo` commands.
