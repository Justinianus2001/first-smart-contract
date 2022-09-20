# Solidity Smart Contract
This repository describe how to code and deploy your first smart contract on **Goerli testnet of Ethereum**. Using virtual wallet ([MetaMask](https://metamask.io/)), [Solidity](https://soliditylang.org/), [HardHat](https://hardhat.org/) and [Alchemy](https://www.alchemy.com/). Let's dive into it!
## Setup
First, run this code to install all package needed for the project (check in *package.json*)
```
npm install
```
Next, we need the environment to deploy and manage smart contracts.
- Sign up an Alchemy account **[here](https://auth.alchemyapi.io/signup)** and then create an app in Goerli network.
- Download extension MetaMask **[here](https://metamask.io/download/)** to build an Ethereum account address, then switch to Goerli Test Network. Need fake ETH to deploy smart contract? Visit this *[faucet](https://goerlifaucet.com/)* provided by Alchemy to get free 0.25 Goerli ETH per day.

To connect MetaMask & Alchemy with this project, we need to create a *.env* file
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

For more information, visit Ethereum tutorial [here](https://ethereum.org/vi/developers/tutorials/hello-world-smart-contract/). You can also apply the *Ethereum Request for Comments (ERC)* by [OpenZeppelin](https://docs.openzeppelin.com/contracts/4.x/tokens) to this project to write and deploy another smart contract (ERC-20, ERC-721, ERC-777, ERC-1155).
## Interact & Submit to Etherscan
Now, we've successfully deployed a smart contract to Goerli network. Let's interact with it!

Add two new lines into *.env* file, which is your Alchemy app API key get from API URL and your deployed smart contract address.
```
API_KEY = "your-alchemy-app-api-key"
CONTRACT_ADDRESS = "your-contract-deployed-address"
```
You can run this code to try change the contract message. Which original is "Hello World!" we have implement in *deploy.js*
```
npx hardhat run scripts/interact.js --network goerli
```
To allow everyone view and interact with your smart contract. You can publish it to Etherscan
You can register an account **[here](https://etherscan.io/register)** and create an app in **[API Keys](https://etherscan.io/myapikey)** option.

Next, connect Etherscan app with this project by add another line into *.env* file
```
ETHERSCAN_API_KEY = "your-etherscan-api-key-token"
```
Lastly, verify your smart contract on Etherscan now!
```
npx hardhat verify --network goerli YOUR_DEPLOYED_CONTRACT_ADDRESS 'your-contract-message'
```