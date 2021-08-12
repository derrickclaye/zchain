# zchain

## Steps to start the network

* reproduce these first 3 steps in two terminal windows *

- cd into zchain directory
- cd into blockchain_hw directory
- cd into eth-blockchain-tools

* right now you should have two terminal windows open each in the eth-blockchain-tools directory

- start the first node by running the following command:

```

./geth --datadir node1 --rpc --mine --miner.threads 1 --unlock '0xb278bdacdddF81CF70Ab9A701942F5dB65c04851' --allow-insecure-unlock

```

- copy the enode path once you run the first node and use that to start the second node

```
./geth --datadir node2 --unlock 'd1e97C9701df2E91c66bd3dB515b28b26bC14716' --mine --port 30304 --bootnodes 'enode://ffd4182b434f08bbe6d52c6124896f49c6ee273dc613ef4f9954853484e0e5b7046e01a05f03abf494cec0f62d81bbdf6086c5971da175baff9daedfbdbefb72@127.0.0.1:30303'

```

( Make sure you copy the correct enode path. Above is just an example of what it should look like )

### Flags meanings

-- datadir: choose node directory 
--mine: make that node a miner
--miner.threads: specify how many threads your computer should dedicate to this task
--rpc: enables us to talk to our second node, which will allow us to use MyCrypto or Metamask to transact on our chain
--bootnodes: allows you to pass the network info needed to find other nodes in the blockchain. This will allow us to connect both of our nodes
-unlock: unlock nodes to allow them to mine and contribute to blockchain 
--port: specify which port to run the node on (For the second node, make sure to increment the port number by 1 from the port number used for node 1. This is the last 6 numbers of the enode path.)

### Network Config

- node 1 password: banana
- node 2 password: apple
- chain ID: 7362

### Connect to MyCrypto

- create a custom node by following these steps:
  - Change Network
  - Add Custom Node
  - Change Network to "Custom"
  - Enter zchain for Node Name and Network Name
  - Enter ETH for currency
  - Enter 7362 for Chain ID
  - Enter http://127.0.0.1:8545 for URL

### Send Transaction

First make sure you are connected to the zchain network on MyCrypto

Both addresses for node1 and node2 are prefunded.
Access the wallet for node1 by using the keystore option: The keystore file you need is within the keystore folder with the node1 or node2 directory.
Send transaction from one address to the other and view in terminal.

Node 1 address: 0xb278bdacdddF81CF70Ab9A701942F5dB65c04851
Node 2 address: 0xd1e97C9701df2E91c66bd3dB515b28b26bC14716



