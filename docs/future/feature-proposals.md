# Feature Proposals

This section outlines four proposed gamified mechanics intended to reinforce the engagement loop inside AmongOnes without interfering with the pristine fairness of the core contract execution.

## 1. Streak System & On-Chain "Hot Hand"

**Concept:** Each wallet calculates a consecutive "win streak counter" held securely in the on-chain structures. Extending a streak organically scales the payout multiplier linearly.

* Tier 1 (Normal): 0–2 Streak $\rightarrow$ 1.00x Payout Multiplier
* Tier 5 (Unstoppable): 11+ Streak $\rightarrow$ 1.10x Payout Multiplier

**The Math:** Expanding this multiplier does not arbitrarily penalize losing bettors in the Pari-Mutuel formula. Instead, the fractional bonus scalar routes seamlessly out of the isolated `HousePool`.

## 2. Live Odds Visualization

**Concept:** Elevating the standard 2D top-down map into a breathing data visualizer reflecting capital pressure dynamically.

* Every room morphs toward a color gradient (Blue mapping to Crewmates, Red mapping to Impostors) synchronized meticulously to the real-time betting distributions derived algorithmically via: $Odds = \frac{\text{Total Pot}}{\text{Pool}}$
* Incorporates a psychological FOMO factor; massive capital spikes will visually cascade across the map precisely before lock-in triggers.

## 3. Distributed Chat Voting (OCT)

**Concept:** Evolving standard spectator mechanics—while the lobby awaits the lock sequence, bettors can spend minor OCT allocations dictating "game events."

* **Emergency Meeting (0.005 OCT):** Artificially lowers Impostor win probability parameters by ~5%.
* **Sabotage Reactor (0.005 OCT):** Artificially raises Impostor win probability parameters by ~5%.

The entire voting distribution compiles directly back into the House Pool generating sustainable protocol revenue while shifting purely deterministic behavior toward collective agency.

## 4. Daily & Weekly Missions

**Concept:** A robust achievement structure retaining Daily Active Users via Soulbound Tokens (SBT NFTs) and capital rewards dynamically scaled off-chain and claimed on-chain.

* **Daily Focus:** (ex: *Risk Taker*, bet exactly 0.1 OCT and receive 0.003 OCT returned).
* **Weekly Focus:** (ex: *Dedicated Player*, bet minimum 5 days across the week to claim "Regular" NFT classification).
