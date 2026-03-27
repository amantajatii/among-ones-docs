# Frontend Setup

The frontend connects directly to the Game Server via WebSockets (`Socket.io-client`) to visualize the gameplay mechanics and uses `wagmi` / RainbowKit to handle on-chain interactions.

## Prerequisites

- Node.js (>= 18.x)
- `npm`, `yarn`, `pnpm`, or `bun`

## Installation

1. Navigate to the frontend directory:

```bash
cd among-ones-fe
```

2. Install the necessary dependencies:

```bash
npm install
# or
yarn install
# or
pnpm install
```

3. Start the development server:

```bash
npm run dev
# or
yarn dev
```

4. Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Key Hooks and Integration Points

- `useGameState(gameId)`: Connects to Socket.io for live movement, active phases, and player status.
- `useUserBet(gameId, address)`: Queries the blockchain subgraph or node to identify a given user's active bets.
- `useSmoothedPositions(...)`: Essential for handling rapid 100ms ticks from the server and transitioning the UI position of agents smoothly.
- `useUnclaimedPayouts(address)`: Fetches past games to populate the claim functionality.
