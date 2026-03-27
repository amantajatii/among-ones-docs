# Betting System

The smart contract layer inside `among-ones-sc/src/AmongOnes.sol` determines all token movements safely on the One Chain network. Games dynamically rotate from `Uninitialized → Open → Locked → Settled / Cancelled`.

## Essential Methods

| Smart Contract Logic | Who executes | Purpose |
|----------------------|--------------|---------|
| `placeBet(gameId, team)` | Bettor Base | Pledging capital to back a side. |
| `claimPayout(gameId)` | Bettor Base | Pulling yields after victory confirmation. |
| `claimRefund(gameId)` | Bettor Base | Escaping suspended or broken games. |
| `seedPool() & lockGame()` | Node.js Backend Engine | Starting gameplay while securing initial capital. |
| `settleGame(gameId, winner)`| Node.js Backend Engine | Emitting final state to enable claims. |

## Pari-Mutuel Payout Model

Because there are no centralized "odds makers," the payout adapts heavily to the distribution of liquidity.

$$ \text{Payout} = \left(\frac{\text{Your Bet}}{\text{Total Winning Pool}}\right) \times \text{Distributable Amount} $$

* $$ \text{Distributable Amount} = \text{Total Pot} - \text{Protocol Fee (0.1\%)} $$
* Due to logic above, heavily favored teams will have drastically smaller comparative payouts.

## Rolling House Pool

To guarantee liquidity in the early seconds of betting, a "House Pool" (representing the protocol or owner) injects capital into both the Impostors' side and Crewmates' side simultaneously (e.g., 1 OCT vs 1 OCT).
Rather than physically transferring these amounts to fresh proxy contracts manually out-of-band, the internal state applies accounting magic.
1. The **House seed** acts functionally identical to regular spectator bets during the Pari-Mutuel payout.
2. The House's "share" plus the 0.1% transaction fee naturally cycles back into the master pool following game settlement, drastically limiting operational downtime.
