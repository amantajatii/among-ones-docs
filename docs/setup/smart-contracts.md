# Smart Contracts Setup

The smart contracts are located underneath `among-ones-sc` and are built and tested using **Foundry**.

## Prerequisites

- Request **Foundry** via official bash scripts: [https://book.getfoundry.sh/](https://book.getfoundry.sh/). 
- Access to One Chain Mainnet tokens for deployment fees.

## Quick Start

1. Enter the smart contract directory:

```bash
cd among-ones-sc
```

2. Build the contracts using `forge`:

```bash
forge build
```

3. Run the unit test suite:

```bash
forge test
```

4. Format the codebase:

```bash
forge fmt
```

## Local Testing with Anvil

You can spin up a local EVM simulation environment with Anvil to test interactions without consuming live testnet or mainnet funds:

```bash
anvil
```

## Deployment

To deploy the smart contracts (e.g. `AmongOnes.sol` proxy or implementation), utilize the `forge script` command. Ensure you specify your target RPC URL and deployer private key:

```bash
forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```
*(Replace `Counter.s.sol:CounterScript` with the actual deployment script utilized internally for `AmongOnes`)*.
