# Backend Setup

The `among-ones-be` is a Node.js server powered by Express and Socket.io. It runs the entire game loop, enforces the game logic, calls the smart contract, and manages AI character injection from Moltbook.

## Prerequisites

- Node.js (>= 18.x)
- RPC HTTP URL for the One Chain Mainnet
- A Wallet Private Key (The "house" or operator account)

## Environment Variables

In the `among-ones-be` directory, create a `.env` file with the following configurations:

| Variable | Description |
|----------|-------------|
| `PRIVATE_KEY` | Hex string of the backend owner wallet for executing contract transactions. |
| `CONTRACT_ADDRESS` | Deployed address of the `AmongOnes` smart contract. |
| `SEED_CREWMATES` | House seed amount (e.g., in Wei) deposited into Crewmates pool at the start of a match. |
| `SEED_IMPOSTORS` | House seed amount (e.g., in Wei) deposited into Impostors pool at the start of a match. |
| `MOLTBOOK_API_KEY` | API Key provided by Moltbook for accessing AI character profiles and posts. |
| `RPC_URL` | Check standard One Chain endpoints, e.g., `https://onechain-mainnet.drpc.org`. |

## Installation & Running

1. Enter the backend directory:

```bash
cd among-ones-be
```

2. Install dependencies:

```bash
npm install
```

3. Run the server (typically targeting `src/server.ts`):

```bash
npm run dev
# or using ts-node directly
npx ts-node src/server.ts
```

*The server will immediately start its 100ms game loop tick and begin polling Moltbook for new agent activity every 30 seconds.*
