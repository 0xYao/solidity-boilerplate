# Hardhat Boilerplate

## Why ?

Thought to have a fast way of bootstraping projects with best practice's in mind. Having linters, prettiers, standards on how to commit, and changelog creation & maintenance.

---

## How ?

This is achieved using several hardhat plugins, and external known packages.

---

## Tools

This boilerplate includes:

- [Hardhat](https://hardhat.org/)
- [Solhint](https://github.com/protofire/solhint)
- [Prettier](https://github.com/prettier-solidity/prettier-plugin-solidity)
- [Coverage](https://github.com/sc-forks/solidity-coverage)
- [Gas reporter](https://github.com/cgewecke/hardhat-gas-reporter/tree/master)
- [Commitlint](https://github.com/conventional-changelog/commitlint)
- [Standard version](https://github.com/conventional-changelog/standard-version)
- [Uniswap](https://github.com/Uniswap/uniswap-v2-periphery) + [Internal tooling](./test/utils/uniswap.ts)

---

## GitHub Workflows

You need to setup the following GitHub secrets to run the GitHub workflows successfully:

- `ALCHEMYKEY`: the mainnet Ethereum API key is for running e2e tests on the forked mainnet. Get the key from your app on the [Alchemy Dashboard](https://dashboard.alchemyapi.io/).
- `COINMARKETCAP_API_KEY`: the CoinMarketCap API key is for fetching the crypto asset prices to use during the gas report. Get the key from the [CoinMarketCap Developers Dashboard](https://pro.coinmarketcap.com/account).
- `CC`: Codechekcs is for code review automation. We use Codechecks for gas reporting in this project. Get the Codechecks secret by following the "Getting Started" guide on the [codechecks documentation](https://github.com/codechecks/docs/blob/master/getting-started.md).

## Commands

### **Coverage**

- `yarn coverage`: Runs solidity code coverage

### **Fork**

- `yarn fork`: Runs a mainnet fork via hardhat's node forking util.
- `yarn fork:script {script_path}`: Runs the script in mainnet's fork.
- `yarn fork:test`: Runs tests that should be run in mainnet's fork.

### **Lint**

- `yarn lint:fix`: Runs prettier and solhint

### **Release**

- `yarn release`: Runs standard changelog, changes package.json version and modifies CHANGELOG.md accordingly.

### **Test**

- `yarn test:all`: Runs all solidity tests.
- `yarn test:unit`: Runs all solidity tests in folder [unit](./test/unit)
- `yarn test:e2e`: Runs all solidity tests in folder [e2e](./test/e2e)

### **Gas report**

- `yarn test:gas`: Runs all tests and report gas usage.
