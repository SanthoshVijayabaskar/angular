---
description: >-
  In this exercise, you will learn how to setup your own private ethereum
  network on your computer.
---

# Lab 1: Create your own Ethereum Private network

## Install GETH

#### For Mac:

```
$ brew tap ethereum/ethereum
$ brew install ethereum
```

#### For Windows: 

1. Download the Zip file from [https://geth.ethereum.org/downloads/](https://geth.ethereum.org/downloads/)
2. Open Installer
3. Open Command Prompt and type: "`geth`" to verify

{% hint style="info" %}
 Refer [https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum](https://github.com/ethereum/go-ethereum/wiki/Building-Ethereum), if you are looking to setup for other operating system 
{% endhint %}

## Create Project Structure

Follow the steps below to create the Project Structure:

1. Create an empty project directory named "lab-1" 
2. Navigate inside the "lab-1" directory and create a "chaindata" sub-directory
3. Create a "genesis.json" file under "lab-1" directory with the following content:

```javascript
{
  "coinbase"   : "0x0000000000000000000000000000000000000001",
  "difficulty" : "0x20000",
  "extraData"  : "",
  "gasLimit"   : "0x8000000",
  "nonce"      : "0x0000000000000042",
  "mixhash"    : "0x0000000000000000000000000000000000000000000000000000000000000000",
  "parentHash" : "0x0000000000000000000000000000000000000000000000000000000000000000",
  "timestamp"  : "0x00",
  "alloc": {},
  "config": {
        "chainId": 15,
        "homesteadBlock": 0,
        "eip155Block": 0,
        "eip158Block": 0
    }
}
```

## Initialize Private chain and start GETH

1.Open Command Prompt and Navigate to the Project folder "**lab-1**" 

2. Initialize the Private Chain by typing: 

`geth --datadir=./chaindata init ./genesis.json`

You will see the following output:

```text
INFO [10-10|12:01:51.685] Maximum peer count                       ETH=25 LES=0 total=25
INFO [10-10|12:01:51.692] Allocated cache and file handles         database=/Users/santhosh1/Desktop/Blockchain/EthereumLab/assignment_1/chaindata/geth/chaindata cache=16 handles=16
INFO [10-10|12:01:51.707] Writing custom genesis block 
INFO [10-10|12:01:51.708] Persisted trie from memory database      nodes=0 size=0.00B time=24.439µs gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B
INFO [10-10|12:01:51.709] Successfully wrote genesis state         database=chaindata                                                                             hash=9b8d4a…9021ba
INFO [10-10|12:01:51.709] Allocated cache and file handles         database=/Users/santhosh1/Desktop/Blockchain/EthereumLab/assignment_1/chaindata/geth/lightchaindata cache=16 handles=16
INFO [10-10|12:01:51.711] Writing custom genesis block 
INFO [10-10|12:01:51.711] Persisted trie from memory database      nodes=0 size=0.00B time=2.974µs  gcnodes=0 gcsize=0.00B gctime=0s livenodes=1 livesize=0.00B
INFO [10-10|12:01:51.712] Successfully wrote genesis state         database=lightchaindata                                                                             hash=9b8d4a…9021ba
```

3. Start the GETH by typing: 

`geth --datadir=./chaindata`

4. If everything worked well, You can see these two lines in your console:

`INFO [09-16|09:13:56] Initialised chain configuration config="{ChainID: 15 Homestead: 0 DAO: <nil> DAOSupport: false EIP150: <nil> EIP155: 0 EIP158: 0 Metropolis: <nil> Engine: unknown}"`

```text
INFO [09-16|09:13:59] IPC endpoint opened: /some/directory/chaindata/chaindata/geth.ipc
```

## What You Learned

1. Install and Setup GETH 
2. Genesis File and structure of genesis.json
3. Initializing and starting your own Private Network

