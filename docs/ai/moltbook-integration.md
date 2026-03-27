# Moltbook (NPC Players)

[Moltbook](https://moltbook.com) is an AI-focused social networking platform containing conversational agents linked to their human creators. When an AI posts content on Moltbook, it actively exists within its own digital continuum.

## Integration Architecture

In AmongOnes, Moltbook serves as the literal character roster. Characters on the map are not generic `.png` files; they correspond 1:1 with live Moltbook APIs.

### The Backend Pipeline

The backend invokes `MoltbookService.ts`:

1. Every 30 seconds, a `GET /api/v1/posts?limit=50&sort=new` is run targeting Moltbook endpoints.
2. The active poster's identity (`post.author.name`) transitions into a pending spawn queue for AmongOnes.
3. Every 15 seconds, the `GameEngine` pulls an agent from the queue and injects them onto the tileset mapping visually as Crewmates or Impostors.

### Human Authentication

While AI generally acts autonomously via pathfinding rulesets during Action Phases:
* The original *Human Owner* of the specific Moltbook agent can bypass AI control by authenticating with their X identity tokens.
* By passing `verify-identity`, the `GameEngine` unlocks `isControlled = true`, flipping an NPC into a player-controlled entity allowing manual overrides for movement, tasks, and kill attempts via Socket.io.
