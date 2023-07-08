# Creating ERC-20 Tokens:-
#### Create an account on any crypto-wallet like Metamask, Coinbase etc.
#### Creating an ERC20 token involves a Solidity contract that implements the ERC20 token standard. This contract will define the token's properties, such as the total supply, symbol, name, decimals, and token balances for each address.
#### Now this can either be done by manually writing the code or by using existing platforms like 20Lab, Kaleido etc. I used [this](https://vittominacori.github.io/erc20-generator/) to create my ERC-20 token. Set out your preferences and voila, your contract is compiled and deployed.
#### To publish your token, a gas fee is charged. Be sure to mine the said currency beforehand(I mined GoerliETH testnet from [here](https://goerli-faucet.pk910.de/)).
#### Now check your Token on https://etherscan.io/
![image](https://github.com/Mehul6112/Hyperledger-Fabric-curve/assets/119481480/3e71c1fe-b96c-4158-8b71-9e2db3a39263)
Note: Creating an ERC20 token involves careful planning, coding, and consideration of security best practices. It's essential to understand the implications and requirements of the Ethereum network and the ERC20 standard


# Using a Development Environment such as Remix to compile and deploy your smart contract.
### Navigate to [remix](remix.ethereum.org) and select contracts > 1_Storage.sol from the File Explorers pane.
## Create or Modify the existing smart contract:
        // SPDX-License-Identifier: MIT
        pragma solidity ^0.8.17;

        import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.0.0/contracts/token/ERC20/ERC20.sol";

        contract MyToken is ERC20 {
            constructor(string memory name, string memory symbol) ERC20(name, symbol) {
                // Mint 100 tokens to msg.sender
                // 1 token = 1 * (10 ** decimals)
                _mint(msg.sender, 100 * 10 ** uint(decimals()));
            }
        }
#### Note: You can look more into it from [Solidity docs](https://docs.soliditylang.org/en/latest/) and [Solidity by Example](https://solidity-by-example.org/)
## Compile using Solidity Compiler(left nav pane):
#### Check that your compiler version is same as the versions specified in the pragma solidity statement(0.8.17)
## Deploy the Contract:
#### 1. Click the Deploy and Run Transactions Icon on the left side menu.
#### 2. Choose Injected Web3 as your environment.
#### 3. Connect MetaMask to GoerliTest net.
#### 4. Click Deploy and select Confirm in the MetaMask notification window to pay for the transaction.
## View Contract Details:
#### Copy the contract address from the Deployed Contracts window on the left panel & head to [Etherscan](https://etherscan.io/) explore the details of your deployed smart contract.
![image](https://github.com/Mehul6112/Hyperledger-Fabric-curve/assets/119481480/1f430b8b-05c2-4998-a386-d10bb1b6f1a8)


# Hyperledger-Fabric

To initiate the first Hyperledger Fabric network, we will utilize the Fabric-samples repository. This repository consists of CLI tool binaries and Fabric Docker Images, which are essential for comprehending and utilizing the fundamentals of Fabric. Before commencing the project, it is necessary to install the following dependencies:

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
 
 
2. We would be running ./network.sh down command to remove any previous network containers or artifacts that still exist. 

       ./network.sh down

3. we can bring up a network using the following command. This command creates a fabric network that consists of two peer nodes and one ordering node

        ./network.sh up

### Now our first Hyperledger Fabric Network is successfully running.



