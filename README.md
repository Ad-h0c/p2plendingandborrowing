
# P2P-Lending-Borrowing

## About The Project

A decentralized, smart contract based platform for p2p-lending of any existing ERC20 Token on the Ethereum Blockchain with ETH as colletral.
The open ecosystem of the p2p-lending platform has the potential to offer cheaper lending contracts than traditional centralized institutions, while also enabling people all over the world to profit from a fair and transparent portfolio of products.

## Built With

- [Node 13](https://nodejs.org/en/)
- [Truffle](https://truffleframework.com/truffle)
- [Ganache](https://www.trufflesuite.com/ganache)
- [web3.js](https://web3js.readthedocs.io/en/1.0/getting-started.html)

## Prerequisites

These are the requisites you need, in order to use the software and instructions, on how to install them.

### NodeJS and NPM

```sh
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
sudo bash nodesource_setup.sh
sudo apt install nodejs
```
### Ganache

Download it form this link https://truffleframework.com/ganache
### Truffle

```sh
npm install truffle -g
```

## Installation

### Clone the repo

```sh
git clone <Current_URL>
```

### Run Ganache on port 8545

```sh
Ganache -> Settings -> Server -> Port Number -> 8545
```

### Go to smart_contract folder and Install dependencies

```sh
npm install
```

### Compile Smart Contracts

```sh
truffle compile
```

### Deploy Smart Contracts to local blockchain

```sh
npm run migrate:dev
```

### Create Test Cases

**Important** : Run this only if you want to create new test cases. 

Example :
```
truffle create test AskRequest
```

### Run Test

```sh
npm run test
```

## Backend

### Update Smart Contract address in config/development.js (get this from the ganache gui or console output)

config.smartContractAddress.p2pToken

config.smartContractAddress.p2pPlatform

### Go to api folder and Install dependencies

```sh
sudo npm install
```

### Create Log folder

```
sudo mkdir -p /var/log/defi/
sudo chmod 777 -R /var/log/defi
```

### Start backend

```sh
npm run start
```

### Point to Testnets

Change below configuration in config/development.js

config.blockchain.url = {INFURA_URL}
config.blockchain.chainId = {CHAIN_ID} (Ropsten - 3) 

## API Document

https://www.getpostman.com/collections/bab6a07226f6791e2eda

## Deploying the Smart contract (Manually)

1. P2PToken.sol
2. RequestFactory.sol
3. Governance.sol
4. P2PPlatform.sol


## Understand the Smart contract

1. Create Ask Request with collateral as ETH
2. Get created requests from API -> get Requests
3. Give Token approval from Lender to above address (same amount as asked)
4. Call Lend Function from Lender
5. Transfer some extra token to asker so that he can payback
6. Payback from lender, Colletral will come back
7. Collect Collateral if not paid before deadline
8. Cancel Request before Lender pay
9. Change is Valid from upVote from Governance Contract

# Deploy on Ropsten Network

*HINT (Session 2)* Deploy contract on ethereum ropsten network 

1. Set your Infura Key(https://infura.io/) and Mnemonic as below (Use your existing seed or create new and transfer some ether to it)
2. Update "from" address in truffle-config.js which have funds

```sh
export INFURA_API_KEY="asdasd"
export MNEMONIC="asd asd ...."
```

# Services

## Block Crawler (Sample)

To capture all blockchain transaction

```sh
cd api
node script/blockCrawler.js
```

# Upgradable Smart Contract Demo

Move to upgradable_smart_contract_demo folder.

## Install Open Zepplelin Cli

```
npm install -g @openzeppelin/cli
oz --version
```
