## MongoDB Dockerfile


This repository contains **Dockerfile** of [MongoDB](http://www.mongodb.org/) for [Docker](https://www.docker.io/)'s [trusted build](https://index.docker.io/u/dockerfile/mongodb/) published to the public [Docker Registry](https://index.docker.io/).


### Dependencies

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.io/).

2. Download [trusted build](https://index.docker.io/u/dockerfile/mongodb/) from public [Docker Registry](https://index.docker.io/): `docker pull dockerfile/mongodb`

   (alternatively, you can build an image from Dockerfile: `docker build -t="dockerfile/mongodb" github.com/dockerfile/mongodb`)


### Usage

#### Run `mongod`

    docker run -d -p 27017:27017 --name mongodb dockerfile/mongodb

#### Run `mongod` w/ persistent/shared directory

    docker run -d -p 27017:27017 -v <data-dir>/db:/data/db --name mongodb dockerfile/mongodb

#### Run `mongod` w/ HTTP support (requires firewall on port 28017)

    docker run -d -p 27017:27017 -p 28017:28017 --name mongodb dockerfile/mongodb mongod --rest --httpinterface

#### Run `mongo`
    
    docker run -it --rm --link mongodb:mongodb dockerfile/mongodb bash -c 'mongo --host $MONGODB_PORT_27017_TCP_ADDR'

##### Usage with VirtualBox (boot2docker-vm)

_You will need to set up nat port forwarding with:_  

    VBoxManage modifyvm "boot2docker-vm" --natpf1 "guestmongodb,tcp,127.0.0.1,27017,,27017"  
    
This will allow you to connect to your mongo container with the standard 'mongo' commands  
