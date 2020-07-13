## Introduction

This is a recipe to be followed for a Lotus workshop.

## Pre-workshop Phase 1: Setup

- Go to [lotu.sh](https://lotu.sh/)
- Find the appropriate Setup page for your system, go through the steps to install dependencies
- Before building Lotus, checkout the 
[ntwk-nerpa branch](https://github.com/filecoin-project/lotus/tree/ntwk-nerpa) 
by running `git checkout -b ntwk-nerpa origin/ntwk-nerpa`
- Follow the instructions to build Lotus
- When done, run `./lotus daemon` to get your node up and running.

## Phase 2: Explore the node

Open a new tab
- `./lotus sync status` displays your sync status
- `./lotus wallet new` creates a new account in your wallet
- Click "Send Funds" on [the faucet](https://faucet.nerpa.fildev.network/) to get rich!
- `./lotus wallet balance` displays your balance
- Although there isn't one for `nerpanet`, explorers like filscan.io, filscout.io, and filfox.io
can be used to visualize testnet state
- Use `./lotus send` to send money to your friends on `nerpanet`

### Phase 3: Advanced features
- Try sending a request over the RPC: 
```
curl -X POST \
    -H "Content-Type: application/json" \
    --data '{ "jsonrpc": "2.0", "method":"Filecoin.ChainHead", "params": [], "id": 0
    }' \
    'http://127.0.0.1:1234/rpc/v0'
```
- `./lotus msig create <params>` creates a multisig wallet with the provided params
- `./lotus client import <file>` imports a file into your local store
- `./lotus client deal <params>` can be used to create a deal with a miner
- `./lotus client retrieve <params>` can be used to retrieve files from miners