# Dummy Token

A simple dummy token. Based on the [HardHat Tutorial](https://hardhat.org/tutorial/).

## Setup

1. Run `npm install` to install dependencies
2. Run `npx hardhat test` to test the code
3. Start a local development ethereum node on a new terminal using `npx hardhat node --hostname 0.0.0.0`
4. Run `npx hardhat --network localhost run scripts/deploy.js` to deploy the Dummy Token contract, keep note of the `Token Address` that will output in the terminal.
5. Run `npx hardhat --network localhost faucet <token-address> <your-address>`, where `<token-address>` is the address of the Dummy Token contract deployed in the previous step, and `<your-address>` is your Ethereum address (i.e., your MetaMask account). This will fund your Ethereum account with ETH and mint DUMMY tokens.
6. Connect your MetaMask extension to the `localhost` network. You should have 1 ETH in your balance.
7. Add the Dummy Token to MetaMask:
   - Click on `Add Token`
   - Click on `Custom Token`
   - Paste on `Token Contract Address` the Dummy Token contract address (from step 4)
   - You should see `100 DUMMY` tokens in your wallet

## Adding a Development Network to MetaMask

To add a development network to MetaMask, follow the instructions in the [MetaMask documentation](https://docs.metamask.io/wallet/how-to/run-devnet/).

1. Open MetaMask and click on the network dropdown at the top.
2. Select "Add Network".
3. Fill in the network details:
   - Network Name: Localhost
   - New RPC URL: <http://0.0.0.0:8545>
   - Chain ID: 1337
   - Currency Symbol: ETH
4. Click "Save"

## Hardhat Configuration

To ensure you always get the same account, define the account mnemonic in the `hardhat.config.js` file.

```js
...
  networks: {
    hardhat: {
      accounts: {
        mnemonic: "test test test test test test test test test test test junk",
      },
      chainId: 1337,
    },
  },
...

