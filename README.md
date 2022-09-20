# Solidity Smart Contract
This repository describe how to code and deploy your first smart contract on **Goerli testnet of Ethereum**. Using virtual wallet ([MetaMask](https://metamask.io/)), [Solidity](https://soliditylang.org/), [HardHat](https://hardhat.org/) and [Alchemy](https://www.alchemy.com/). Let's dive into it!
## Setup
First, run this code to install HardHat to the project
```
npm install --save-dev hardhat
```
Install library Ethers.js to easily interact with Ethereum blockchain
```
npm install --save-dev @nomiclabs/hardhat-ethers 'ethers@^5.0.0'
```
Next, we need the environment to deploy and manage smart contracts.
- Sign up an Alchemy account **[here](https://auth.alchemyapi.io/signup)** and then create an app in Goerli network.
- Download extension MetaMask **[here](https://metamask.io/download/)** to build an Ethereum account address, then switch to Goerli Test Network. Need fake ETH to deploy smart contract? Visit this *[faucet](https://goerlifaucet.com/)* provided by Alchemy to get free 0.25 Goerli ETH per day.

To connect MetaMask & Alchemy with this project, we need to create a *.env* file by install dotenv package:
```
npm install dotenv --save
```
Then write this into *.env*
```
API_URL = "https://eth-goerli.g.alchemy.com/v2/your-api-key"
PRIVATE_KEY = "your-metamask-private-key"
```
This two key can fill by your information in Alchemy app HTTPS and MetaMask Private Key.

Finally, run code to compile & deploy the smart contract
```
npx hardhat compile
```
```
npx hardhat run scripts/deploy.js --network goerli
```
**Contract deployed !!!** 🎉🎉🎉

For more information, visit Ethereum tutorial [here](https://ethereum.org/vi/developers/tutorials/hello-world-smart-contract/).