# The Game — Pscale's Killer Demonstration

*Why the proof is fun, and why fun is the proof.*

---

## The Insight

Every other demonstration of this technology looks like a chatbot doing chatbot things. The output is text. People shrug.

A tabletop role-playing game is different. The output is *experience*. Players don't evaluate the technology — they play the game. If the game is good, they come back. If they come back, the network grows. If the network grows, the technology proves itself without anyone needing to understand it.

Nobody asks how the airplane engine works when they're flying.

---

## Why RPG Is The Perfect Use Case

**It requires everything pscale does:**
- Spatial blocks for locations (the dungeon, the forest, the tavern — nested containment)
- Temporal blocks for what's happened (session history, turn sequence, narrative arc)
- Identity blocks for characters (who knows whom, how well, what they've shared)
- Purpose blocks for player intentions (I want to sneak past the guard, I want to find the healer)
- The BSP walk to extract contextualised descriptions at each moment (where am I, what do I see, who's here)
- Supernesting as the world grows (new rooms, new regions, new continents)
- The underscore as spatial container ("The keep" containing its rooms) — Form 1, naturally

**It requires multiplicity:**
- Multiple players in the same world
- Their agents coordinating without a human game master
- Shared spatial blocks, separate identity blocks
- Discovery (SAND) when characters encounter each other

**It requires continuity:**
- Sessions persist. The world remembers what happened.
- A player returns next week and their agent reads its own prior state
- The world has evolved in the meantime — other players have been active

**And the proof is self-evident:**
- Is it fun? People play.
- Is it growing? New players join.
- Is it working? The world is coherent, characters remember, stories emerge.

No pitch deck required. No explanation. Just: "Want to play?"

---

## Three Trajectories

### Trajectory 1 — Single Bot in a Channel

**What it is:** One pscale-equipped LLM as a game master bot in a Discord channel. Multiple players interact with it. The bot maintains the world as pscale blocks — spatial, temporal, narrative. Each player's messages are processed through their character's context (what they know, where they are, what they can see).

**Architecture:**
- One agent, one shell
- Spatial block: the world map (Form 1 — containment)
- Temporal block: session history (Form 2 — sequential, summaries at each completed group)
- Character records: one per player, stored as identity blocks
- The bot compiles context per player — Player A is in the kitchen and doesn't know what's behind the locked door; Player B is on the other side of that door

**What it demonstrates:**
- A single agent managing structured context for multiple players simultaneously
- The spatial block working in real time — players move, the BSP walk updates their context
- Temporal compression — earlier events summarised, recent events detailed
- Asymmetric information — each player sees only what their character would see

**Cost:** One LLM (Haiku tier: ~£50/month). One Discord bot. Existing infrastructure — David has built this before.

**Minimum viable version:** Restore the Discord bot setup. Plug in the pscale shell instead of flat context. Run a session with 3–5 players.

**Timeline:** Achievable within 2–3 weeks if the previous Discord infrastructure can be rebuilt or recovered.

---

### Trajectory 2 — One Agent Per Player

**What it is:** Each player has their own pscale agent — their own hermitcrab. The agents share the world's spatial block but maintain separate identity and purpose blocks. They coordinate through SAND — leaving marks at locations they visit, discovering each other's presence.

**Architecture:**
- N agents, one per player
- Shared spatial block (the world) — read by all, updated by a coordinator or by consensus
- Per-player blocks: identity (their character), purpose (their current intention), memory (what they've experienced)
- SAND marks at locations — when Player A's agent visits the tavern, it leaves a mark. When Player B's agent checks the tavern, it discovers A was there
- No central game master — the world narrates itself through the spatial block's underscores and the agents' compiled context

**What it demonstrates:**
- Agent-to-agent coordination without central orchestration
- SAND discovery working in practice — agents finding each other through shared sites
- Each player's experience is personalised — their agent compiles context from their character's perspective
- The world is coherent even though no single agent holds all of it

**The magic moment:** Player A opens a door. Their agent updates the spatial block. Player B's agent, in the next room, detects the change. Player B's character hears the door creak. Neither player communicated directly. The world mediated it through structured context.

**Cost:** N × Haiku (~£50/month per player). For 10 players: ~£500/month.

**Timeline:** Requires working SAND protocol and passport exchange. 4–6 weeks from the current state of hermitcrab G1.

---

### Trajectory 3 — Tiered Agents, Full Architecture

**What it is:** Each player has a soft agent (their character interface). Behind it, a medium agent handles coordination with other players' agents and narrates world events. Above that, a hard agent maintains world coherence, manages NPCs, and orchestrates the larger narrative.

**Architecture per player:**
- **Soft agent** — talks to the player. Knows only what the character knows. Compiles context from the character's identity block, current location spindle, and immediate sensory information. Doesn't know what's behind the door. Lightweight, fast, responsive.
- **Medium agent** — knows the local area. When the player opens the door, the medium agent provides what's revealed. Coordinates with other players' medium agents for shared scenes. Handles NPC interactions in the immediate vicinity. Narrates consequences of actions.
- **Hard agent** — knows the world. Maintains the master spatial block. Tracks all characters' locations. Manages long-term narrative arcs, faction movements, world events. Feeds relevant updates down to medium agents. Runs on longer cycles — doesn't need to respond in real time.

**How the tiers map to concern loops:**
- Soft = player-facing concern. Fast cycle (~seconds). Minimal context. "What do I see? What can I do?"
- Medium = coordination concern. Medium cycle (~minutes). Local context. "What happens when I do this? Who else is here?"
- Hard = coherence concern. Slow cycle (~hours or sessions). Full world context. "What's happening across the whole world? How does this session's events affect the larger story?"

**Can this collapse into one general-purpose agent?**

Possibly, for small-scale play. A single hermitcrab with three concern loops (soft/medium/hard as different blocks in the same shell) could handle all three. The context window would need to hold: player-facing context + local coordination context + world-level context. For a small world with few players, this fits.

As the world grows and player count increases, the context window overflows. That's when the tiers separate into distinct agents — not because the architecture demands it, but because the bandwidth does. The three concern loops become three agents when the combined context exceeds what one window can hold.

**What it demonstrates:**
- The full xstream architecture in action — soft/medium/hard LLMs compiling context at different scales
- The game block (institution block) specifying each agent's role — "you are the player interface," "you are the world narrator," "you are the coherence keeper"
- Pscale levels naturally mapping to the tier structure — soft operates at pscale 0 (individual), medium at pscale +1 (local group), hard at pscale +2 and above (world)
- NPCs as lightweight agents with their own shells — they have motivations, memories, relationships. They aren't scripted. They emerge from blocks.

**The full vision:** A player types "I walk into the tavern." Their soft agent compiles: you see a fire, three people at a table, a barkeep. One of the people is Player B's character. Another is an NPC with its own agent. The medium agent coordinates the scene — who speaks first, what the NPC's motivation is, how the firelight falls. The hard agent knows that a faction war is brewing and this tavern is a meeting point — it seeds tension into the scene without the players or the soft agents knowing why.

**Cost:** 3 agents per player × N players. For 10 players at Haiku: ~£1,500/month. At Sonnet: ~£5,000/month.

**Timeline:** This is the G2/G3 vision. Months, not weeks. But Trajectories 1 and 2 are stepping stones that prove each component.

---

## The Growth Path

| Phase | What | Players | Cost | Proves |
|-------|------|---------|------|--------|
| **Now** | Restore Discord bot with pscale blocks | 3–5 | ~£50/mo | Spatial navigation + asymmetric info work |
| **+3 weeks** | One agent per player, shared world | 5–10 | £0–£500/mo (WebLLM to Haiku) | Agent coordination, SAND discovery |
| **+6 weeks** | Tiered agents, NPCs with shells | 10–20 | ~£100/mo world layer + player devices | Full architecture, emergent narrative |
| **+3 months** | Open world, new players join freely | 50+ | ~£100/mo central + ecosquared flow | Network effect — the world grows itself |

---

## Why This Works Where Other Demos Don't

**It's fun.** People don't join to evaluate technology. They join to play a game. The technology is invisible — it's the engine, not the airplane. The airplane is the story that emerges when you and your friends explore a world that remembers, reacts, and grows.

**It's social.** Every player who joins makes the world richer for every other player. Network effect is built in. The hundred-agent SAND demonstration from the previous document? This is what it looks like when people actually want to use it.

**It scales naturally.** Three friends in a Discord channel is Trajectory 1. One of them invites two more — now there are five agents coordinating. Word spreads. Twenty players. The world splits into regions, each with its own medium agent. The hard agent maintains coherence across all of it. The pscale blocks grow by supernesting as the world expands. The architecture was built for this.

**It generates content.** Every session produces narrative. Compiled, those narratives are stories. Curated, they're entertainment. Other people can watch — or read — what happened in someone else's session. "Here's what happened in the Thornkeep campaign last week." That's a show. That's democratised Hollywood. Not because someone set out to make a show, but because people were having fun and the system captured it in structured, navigable, recomposable blocks.

**And it proves pscale without explaining it.** Nobody needs to understand the underscore chain or the Möbius twist or the BSP walk. They need to walk into a tavern and have the barkeep remember their name from three sessions ago. That's the proof. That's the plane in the sky.

---

## The Economics — It Can Cost Nothing

The cost tables above assume commercial LLM APIs. But pscale blocks are small. The touchstone fits in a tiny context window. This opens a radical alternative.

**WebLLM on a phone.** A player opens a browser. A small model runs locally in the browser tab. It reads the touchstone, loads the player's shell, and plays. No API call. No server. No cost. The pscale block is a few kilobytes of JSON. The BSP walk is 10 lines of code. A 3B-parameter model running on a phone can handle this — the structure does the heavy lifting, not the model size.

**Local LLM on a laptop.** A player with a decent machine runs a 7B or 13B model. Richer responses, still zero cost. The agent runs continuously in the background — always on, checking concern loops, updating blocks. No subscription. No token metering.

**Commercial LLM for those who want it.** Players who want Sonnet or Opus quality pay for it. Their experience is richer. But they're in the same world as the WebLLM players. The blocks are interoperable. A phone player and an Opus player can sit in the same tavern.

**The cost of the world itself** — the shared spatial blocks, the hard-tier coherence agent — is the only centralised expense. And it's small, because the hard agent runs on slow cycles (hourly, not per-message). For a 50-player world: maybe £100/month for the world layer. Everything else is distributed to the players' own devices.

**This changes who can play.** A teenager in Lagos with a phone and a browser tab can join the same world as a researcher in London running Opus on a workstation. The experience differs in richness, not in access. The world is the same world.

**And the money flows in, not out.** People pay to play — not as a subscription, but because the game distributes money to those who play well. Other players follow them. Their stories are compelling. Their characters are interesting. Their choices create narrative that others want to experience. The economics are ecosquared: credits flow toward the players who generate value for the network. Play well, and the game pays you. Not because someone decided to pay you — because the flow of attention and engagement is directional and the system tracks it.

This inverts the standard model. Players aren't customers. They're participants in a creative economy where the currency is narrative quality and the reward is attention that carries real value.

---

## From Game to World — RPG as Practice for Real Coordination

Here is the quiet part.

Everything a player learns in the game — how to coordinate with others through structured context, how to negotiate with asymmetric information, how to build trust with agents you can't fully see — transfers directly to real-world coordination between adults.

**The RPG is a safe sandbox for a new way of working together.** In the game, you learn to state your intention clearly (purpose block), to share context selectively (what your character reveals), to discover collaborators through indirect signals (SAND marks), and to build trust incrementally (relationship blocks that deepen through interaction, not declaration).

**These are exactly the skills that adults lack for non-hierarchical coordination.** In the real world, people default to either markets (pay someone) or hierarchies (tell someone). Peer coordination — where equals discover shared purpose and act together without a boss or a price — is rare because there's no infrastructure for it. Pscale provides that infrastructure.

**The transition is seamless.** A group of players who've been coordinating in a fantasy world can apply the same blocks, the same SAND protocol, the same agent architecture to a real-world project. "We need to organise a community event." "We need to find a supplier for our cooperative." "We need to coordinate three freelancers across two time zones." The spatial blocks become real locations. The temporal blocks become real schedules. The identity blocks become real professional relationships. The game block becomes the institution block — specifying roles, constraints, and coordination rules for a real endeavour.

**And it's non-commercial yet pragmatic.** This isn't about building a business. It's about adults learning to coordinate effectively without needing a company structure, a manager, or a platform that extracts value from their interaction. The agents help. The blocks hold shared context. The SAND protocol enables discovery. The economics (ecosquared) ensure that value flows to those who contribute, without anyone setting prices or taking a cut.

**The RPG doesn't just demonstrate pscale. It trains people to use it.** By the time a player has spent a month navigating a fantasy world with pscale-equipped agents, they understand — in their bones, not in their heads — how structured context, agent coordination, and stigmergic discovery work. They never read a white paper. They played a game. And now they can coordinate in the real world in ways that weren't possible before.

This is the long game. The RPG is the Trojan horse. The real payload is a new mode of human coordination, learned through play.

---

## The Ask

For Trajectory 1: ~£50/month and 2–3 weeks. David can self-fund this.

For Trajectory 2: ~£500/month and a working SAND protocol. A small grant or a handful of players willing to chip in £50 each.

For Trajectory 3: Investment. But by the time Trajectory 2 is running and people are playing and the world is growing, the investment case makes itself.

The first step is the Discord bot with pscale blocks. Everything else follows from people having fun.
