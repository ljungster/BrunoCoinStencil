# Description

BrunoCoin is a fully fledged crytpocurrency written in Go. It is a simple implementation of a cryptocurrency, as it is intended for educational purposes. It contains almost all traditional aspects of a cryptocurrency: making transactions, broadcasting transactions/blocks to the network, mining transactions to a block, validation, maintaining the blockchain, etc. However, it is only meant to run on one machine in a multithreaded environment in order to simulate a real network. 

I focused on implementing the miner and validation functionality, which you can find in the `BrunoCoinStencil/pkg/miner` directory.

This project was created for Brown University's Blockchain & Cryptocurrencies course. Since this project was developed for Brown University, I am NOT able to share our implementation of the project. However, I am able to share this stencil that we provided to the students.

# Class Structure

BrunoCoin has several interacting classes, as shown by the UML class diagram I've created below:

![BrunoCoin UML Class Diagram](assets/class-diagram.png)

Here are some brief (alphabetized) explanations for BrunoCoin's main classes. For more in-depth explanations, check out our documentation in the files themselves. For example, if you want to learn more about the miner's functionality (the part that I focused on), take a look at `BrunoCoinStencil/pkg/miner/miner.go`.

- Block: the Chain's way of recording information on Transactions. It is composed of a BlockHeader and a list of Transactions.

- BlockChain: the blockchain handles keeping track of both forked and main chains. It is essentially a wrapper for a map of BlockChainNodes, which contain Blocks and relevant metadata.

- Client: in charge of connecting to other clients using the P2P (peer-to-peer) networkes, as well as propogating information (blocks and transactions) on the network.

- EphemeralAddressDB: An implementation of the AddressDB interface. The EphemeralAddressDB is a wrapper for a map of addresses, along with ways to update and get information from that map.

- EphemeralPeerDB: An implementation of the PeerDB interface. The EphemeralPeerDB is a wrapper for a map of peers, along with ways to update and get information from that map.

- LiminalTransactions: represents the transactions that the wallet has made, but that do not have enough proof of work on top of them to be considered valid by everyone.

- Miner: supports the functionality of mining new transactions broadcast from the network to a new block.

- MiningPool: contains all transactions that the miner is currently mining.

- Node: the interface for interacting with the cryptocurrency. The node handles all top level logic and communication between different pieces of functionality.

- Server: handles requests made by the node. 

- SimpleId: An implementation of the Id interface. The SimpleID is in charge of handling public and private key information.

- Transaction: a record of a transfer of a cryptocurrency from one party to another. It is composed of TransactionInputs and TransactionOutputs.

- TransactionHeap: represents a heap or priority queue for storing transactions

- TransactionPool: represents all the valid transactions that the miner can mine. It is essentially a wrapper for a TransactionHeap.

- Wallet: Wallet provides the functionality to make transactions from transaction requests and send them to the node to be broadcast on the network.

# Example Functionality 

## Node Receives a Block 

TODO: write

## Miner Finds Nonce 

TODO: write

## Wallet Creates TransactionRequest

TODO: write