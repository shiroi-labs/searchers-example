# About
This repository contains a few examples on how to use a searcher.

## Setup
1. Install protoc to compile protobufs
- Follow instructions at: https://grpc.io/docs/protoc-installation/#install-pre-compiled-binaries-any-os
2. Ensure that the rust toolchain is installed
```bash
$ curl https://sh.rustup.rs -sSf | sh
$ source $HOME/.cargo/env
```
3. Clone the repo
```bash
$ git clone https://github.com/jito-labs/searcher-examples.git --recurse-submodules
$ cd searcher-examples
```

## Infrastructure
You will need access to a few things before running these examples.

### Local keypair
This is a locally generated wallet which you will use to sign transactions and pay for transaction fees and tips with.

### Block Engine URLs
EU:
http://de.shiroi.network:10001

US:
http://ny.shiroi.network:10001

SEA:
http://jp.shiroi.network:10001 

### On-chain addresses
On-chain addresses for tip programs and tip accounts can be found here: https://jito-foundation.gitbook.io/mev/mev-payment-and-distribution/on-chain-addresses

## Folders

### cli
This is a rust program that exercises functionality inside the searcher API so you can explore the functionality. It provides an intuitive CLI-based interface for connecting to the block engine and sending test bundles.
```bash
cargo build --release
./target/release/jito-searcher-cli tip-accounts
./target/release/jito-searcher-cli send-bundle --payer ./wallet.json --message "test" --num-txs 1 --tip-account=96gYZGLnJYVFmbjzopPSU6QiEV5fGqZNyN9nmNhvrZU5 --lamports 1000
```

### shiroi_protos
An example on how to build the protobufs that define the messages and services one can use to talk to our block engine.

### searcher_client
An example on how to authenticate with the block engine as a searcher. All users in the block engine need to perform a challenge-response 

## Disclaimer
Use this at your own risk.
