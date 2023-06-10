# HyperledgerFabric-basic

In order to start the first Hyperledger fabric network Fabric-samples repository will be used. This repository is a set of CLI tool binaries and Fabric Docker Images that help you understand and use the basics of Fabric. Install the below dependencies before starting the project:

## 1.Install Docker

    sudo apt-get -y install docker-compose

## 2. Install Golang-go

    sudo apt install golang-go

## 3. Install jq
(jq is like sed for JSON data )

    sudo apt install jq

## 4. Install Node/java

    sudo apt install npm
    npm install node

## 5. Installing Fabric-samples Repository

    curl -sSLO https://raw.githubusercontent.com/hyperledger/fabric/main/scripts/install-fabric.sh && chmod +x install-fabric.sh

Then you can pull docker containers by running one of these commands:
   
    ./install-fabric.sh docker samples
    ./install-fabric.sh d s


To install binaries for Fabric samples you can use the command below:
   
    ./install-fabric.sh binary

## Building First Network
1. Navigate through the Fabric-samples folder and then through the Test network folder where you can find script files using these we can run our network.
 
       cd fabric-samples/test-network
 
 
2. we would be running ./network.sh down command to remove any previous network containers or artifacts that still exist. 

       ./network.sh down

3. we can bring up a network using the following command. This command creates a fabric network that consists of two peer nodes and one ordering node

        ./network.sh up

###               Now our first Hyperledger Fabric Network is successfully running.



