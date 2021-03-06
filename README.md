# NFT Market Place - A web3 dApp application

An NFT Market Place where any user can mint an NFT, providing the url, name and description.
Thanks to the great article of Nader Dabit at https://dev.to/dabit3/building-scalable-full-stack-apps-on-ethereum-with-polygon-2cfb 

When minted, the NFT is automatically transfered to the MArket Place.
There any other user can buy the NFT.
When a NFT is sold, a fee will be tranferred to the owner.
Any user with a wallet can mint, sell and buy NFTs.

First you need to add your account key into the .env file.
You can test your contract with the following command:

```javascript
npx hardhat test
```

If everything is ok, then deploy the smart contract locally.

Start first hardhat node locally from a shell:

```javascript
npx hardhat node
```

Now from another shell deploy the 2 smart contracts locally:

```javascript
npx hardhat run scripts/deploy.js --network localhost
```

Now that the smart contract is deployed you can start the wep application to interact with the contract. In order to connect the web application to the blockchain and the 2 smart contracts you need to update the `config.js` file

```javascript
export const nftmarketaddress = "ADDRESS_OF_NFT_MARKET"; // 0x...
export const nftaddress = "ADDRESS_OF_NFT"; // 0x...
export const rpc_url = "URL OF THE BLOCKCHAIN"; // http://localhost:8545 for local node
```

To start the web application, first you need to install the dependencies and then start the application in dev mode:

```javascript
npm install
```

If everything is ok, you can start the application with the following command:

```javascript
npm run dev
```

After some test with different accounts to mint, sell and buy NFTs from different users, you can think to deploy to the polygon testnet
To deploy the contract to testnet polygon chain here the command:

```javascript
npx hardhat run scripts/deploy.js --network mumbai
```

remember to copy the 2 addresses generated by the deployment and replace the address in the `config.js` file and also the `rpc_url`

```javascript
export const nftmarketaddress = "ADDRESS_OF_NFT_MARKET"; // 0x...
export const nftaddress = "ADDRESS_OF_NFT"; // 0x...
export const rpc_url = "URL OF THE BLOCKCHAIN"; // "https://matic-mumbai.chainstacklabs.com";
```

Once done, restart the web application.
Done! Now you have your NFT MarketPlace deployed to Polygon testnet and you can have people interact with it via your Web3 application

## Basic Sample Hardhat Project

This project demonstrates a basic Hardhat use case. It comes with a sample contract, a test for that contract, a sample script that deploys that contract, and an example of a task implementation, which simply lists the available accounts.

Try running some of the following tasks:

```shell
npx hardhat accounts
npx hardhat compile
npx hardhat clean
npx hardhat test
npx hardhat node
node scripts/sample-script.js
npx hardhat help
```
