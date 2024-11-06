Unichain Node Setup
===
Learn how to set up a Unichain node

## Information
- Site:  [Unichain](https://www.unichain.org/)
- X:  [Unichain](https://x.com/unichain)
- Docs: [Set Up A Node](https://docs.unichain.org/docs/getting-started/set-up-a-node)

## Tested Platform
- Software
  ```
  OS: ubuntu-24.10-live-server-amd64
  Docker: 26.1.3
  Docker Compose: v2.29.1
  ```
- Hardware
  ```
  CPU: 4-core processor or higher
  RAM: 8 GB or more
  Storage: At least 100 GB free space (SSD recommended)
  Network: Stable internet connection
  ```

## Install & Dependence
- Docker
- Node Provider: [Alchemy](https://www.alchemy.com/unichain) | [QuickNode](https://www.quicknode.com/chains/unichain) | [PublicNode](https://ethereum-sepolia-rpc.publicnode.com)

## Install Docker
- Update Your Package List
  ```
  sudo apt-get update && sudo apt-get upgrade
  ```
- Install Required Packages
  ```
  apt-get install -y ca-certificates curl gnupg lsb-release
  ```
- Install Docker
  ```
  apt-get install -y docker.io docker-compose
  ```
- Add Your User to the Docker Group
  ```
  gpasswd -a $USER docker
  ```
- Activate the Changes to Groups
  ```
  newgrp docker
  ```
- Verify Docker Installation
  ```
  docker -v
  ```
- Install Docker-Compose
  > Replace v2.29.1 in the command below with the latest version if necessary.
  ```
  curl -L "https://github.com/docker/compose/releases/download/v2.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
  ```
- Apply Execute Permissions
  ```
  chmod +x /usr/bin/docker-compose
  ```
- Verify Docker-Compose Installation
  ```
  docker-compose -v
  ```

## Install Unichain Node
- Clone Unichain Node
  ```
  git clone https://github.com/Uniswap/unichain-node.git
  ```
- Go To unichain-node Folder
  ```
  cd unichain-node
  ```
- Edit .env.sepolia
  ```
  nano .env.sepolia
  ```
  ***
  > OP_NODE_L1_ETH_RPC=https://ethereum-sepolia-rpc.publicnode.com [Or Use Your Own Node Provider]
  > OP_NODE_L1_BEACON=https://ethereum-sepolia-beacon-api.publicnode.com
  ***
- Start Node
  ```
  docker-compose up -d
  ```
- Get Some Data JSON Testing
  ```
  curl -d '{"id":1,"jsonrpc":"2.0","method":"eth_getBlockByNumber","params":["latest",false]}' \
  -H "Content-Type: application/json" http://localhost:8545
  ```
- Verify The Containers Are Running
  ```
  docker ps
  ```
- Check OP Node Logs
  ```
  docker-compose logs -f [Your OP Node TAG]
  ```
  
  or

  ```
  docker logs unichain-node-op-node-1
  ```
- Check Execution Client Logs
  ```
  docker-compose logs -f [Your Execution Client TAG]
  ```
  
  or

  ```
  docker logs unichain-node-execution-client-1
  ```
- Backup Generated PrivateKey, Import To Metamask (Checker)
  ```
  sudo cat ~/unichain-node/geth-data/geth/nodekey
  ```
- To Stop Your Node
  ```
  docker-compose down
  ```

## Follow Airdrop Infinity 🌐
➖ Telegram Channel: [Airdrop Infinity](https://t.me/airdropinfinityid)\
➖ Telegram Group: [Airdrop Infinity Group](https://t.me/airdropinfinitygroup)\
➖ X: [0xFAS](https://x.com/0xFASNET)

## Donate ☕
♦️ Ethereum: 0x8B42A04627120f4e23c8702d2b8127A3827aDcf9

❤️ Thank You