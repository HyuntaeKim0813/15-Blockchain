# Blockchain Homework

## Introduction

This readme is designed to help the user to compose the blockchain and join the network. In addition, this readme provides lists of items, directions, and indications of completion. This readme also aims to describe the successful construction of the Proof of Authority (PoA) blockchain.


(Nota Bene: Vast Majority of Text (99.999999%) from Instructors GS, AN, and KS and from Tutor, Ms. LT)



## General Start

### Material

The user needs specific programs.

-Git Bash

-MyCrypto Application

-Go Ethereum

-Microsoft Windows

-Anaconda (Optional)

### What to Do with Material

The user must have Git Bash terminal (https://gitforwindows.org/). In addition, the user must have the MyCrypto application downloaded (https://download.mycrypto.com/). The user must have a version of Go Ethereum; the student author has the version labeled “Geth & Tools 1.9.23” (https://geth.ethereum.org/downloads/). It would help to have access to Microsoft Windows Explorer in order to view the structure of files and folders. The user could benefit from access to the Anaconda interface, leveraging the name of the anaconda network (possible name: “zbank_blockchain”).

At least two action items help the process. One is to have the MyCrypto application open. Another action item is to have two (2) Git Bash terminals open with the ability to open either the puppeth or geth program (i.e., have two (2) terminals open at the Ethereum directory).

### Check

The icons for each of these programs appears with the successful download and loading.

 

## Data Specific for Network

### Node 1 Information (Directly Below)

Public address of the key:   0xdAE9DBf83eE733f0a86A9D5Df3f471bf967a8C25

Path of the secret key file: node1\keystore\UTC--2021-05-09T06-15-37.038355500Z--dae9dbf83ee733f0a86a9d5df3f471bf967a8c25

Password: Morning123@

Port: 30303

### Node 2 Information (Directly Below)

Public address of the key:   0xEdB8d9723dbfd51B7631166a8227EdBaB5526F52

Path of the secret key file: node2\keystore\UTC--2021-05-09T06-17-11.906900200Z--edb8d9723dbfd51b7631166a8227edbab5526f52

Password: Morning123@

Port: 30304 

Enode from Node 1 (Directly Below):

enode://49585f4de1d76f48af01ce097371ebded8d57105de5a1dec4044cdf1f34b4812e3bf7d9edd1153b87da569854675ee30fdf6f03464eab63c8d6d813d993e4ba0@127.0.0.1:30303"

### General Clique Data

Chain ID: 450

Blocktime: 15

Network Name: puppet


## What to Do with Data Specific for Network

(Nota Bene: Text below lifted almost exclusively from POA-Blockchain-guide.md)

The Proof of Authority (PoA) algorithm is typically used for private blockchain networks as it requires pre-approval of, or voting in of, the account addresses that can approve transactions (seal blocks).

Unlike for Proof of Stake (PoS), it is important to start new accounts in the geth program (./geth) before running the puppeth program (./puppeth).

The user has the option to set the virtual environment to the zbank_blockchain with the specific command (provided below).

conda activate zbank_blockchain

Otherwise, it is possible to have the two (2) Git Bash terminals, with each open on the Ethereum network (as described above).

The user must accounts for two nodes for the network with a separate datadir for each using geth.

In order to activate the first node, the user has to enter a specific command (listed directly below).

./geth init trial_five.json --datadir node1

In order to activate the second node, the user has to enter a specific command (listed directly below).

./geth init trial_five.json --datadir node2

The user would do well to create a file with the passwords (Player13 for node1 and Player31 for node2) and to save this file in the same directory as the node files. In addition, the user would do well to enter each password at the correct time. At least one time would be after entering the command to start mining.

 

 

The user would most likely mine most efficiently with starting mining on node1 in one Git Bash terminal and with continuing mining on node2 in another Git Bash terminal.

The user may start mining on node1 with a specific command (given below).

./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock

With the “SEALER_ONE_ADDRESS” as the address of the first public address of the key for the first node, the command changes.

./geth --datadir node1 --unlock "0xdAE9DBf83eE733f0a86A9D5Df3f471bf967a8C25" --mine --rpc --allow-insecure-unlock

For node2, which may be entered in a different Git Bash terminal as described above, the command is somewhat different (given below).

./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

With “SEALER_TWO_ADDRESS” being the second public address for the second node and with the “SEALER_ONE_ENODE_ADDRESS” as the address of the enode address for the first node, the command changes.

./geth --datadir node2 --unlock "0xEdB8d9723dbfd51B7631166a8227EdBaB5526F52" --mine --port 30304 --bootnodes "enode://49585f4de1d76f48af01ce097371ebded8d57105de5a1dec4044cdf1f34b4812e3bf7d9edd1153b87da569854675ee30fdf6f03464eab63c8d6d813d993e4ba0@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

After entering these last two commands, the user should enter the unique passwords, even when not prompted (Player13 for node1 and for node2, Player31).

![ETH 1](https://user-images.githubusercontent.com/74793861/117895877-53bd9b80-b28d-11eb-9043-bd973fb6cc06.PNG)
![ETH2](https://user-images.githubusercontent.com/74793861/117895908-66d06b80-b28d-11eb-9c44-7508efcd88eb.PNG)
![ETH 3](https://user-images.githubusercontent.com/74793861/117895915-69cb5c00-b28d-11eb-8551-0c114598f77a.PNG)
![ETH 4](https://user-images.githubusercontent.com/74793861/117895943-7e0f5900-b28d-11eb-94fa-ac86cf6cdcdf.PNG)
![ETH 5](https://user-images.githubusercontent.com/74793861/117895947-7f408600-b28d-11eb-8c9b-66c3a45e5e87.PNG)
![ETH 6](https://user-images.githubusercontent.com/74793861/117895949-8071b300-b28d-11eb-9c97-131bbdb11b3d.PNG)
![ETH 7](https://user-images.githubusercontent.com/74793861/117895951-81a2e000-b28d-11eb-89e3-e6bc5e60e384.PNG)
![ETH 8](https://user-images.githubusercontent.com/74793861/117895953-82d40d00-b28d-11eb-8bb8-248511e09b3f.PNG)
![ETH 9](https://user-images.githubusercontent.com/74793861/117895955-836ca380-b28d-11eb-86e8-b5181490a0fc.PNG)


