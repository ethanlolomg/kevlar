# Kevlar

Kevlar is a CLI tool to run a light client-based RPC Proxy for PoS Ethereum. Kevlar can be used to make your Metamask or any RPC-based wallet completely trustless! Kevlar first syncs to the latest header of the beacon chain and then starts an RPC server. This local RPC server can be added to MetaMask or any other RPC-based wallet. Every RPC call made by the wallet is now verified using Merkle Inclusion proofs to the latest block header. Currently Kevlar supports two kinds of sync methods: the **Light Sync** based on the light client sync protocol specified by the Ethereum Specification and the **Optimistic Sync** (which is 100x faster than Light Sync) based on construction from the research paper [Proofs of Proof of Stake in Sublinear Complexity](https://arxiv.org/abs/2209.08673).

### Build Locally

Clone the repo and perform the following commands

```bash
npm install
npm run build
npm run rpc-proxy  

curl -X POST --header "Content-type: application/json" --data '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":1}' http://localhost:8546/
```
