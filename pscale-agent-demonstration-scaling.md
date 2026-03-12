# Pscale Agent Demonstrations — Scaling the Airplane

*From a single engine to a fleet in formation.*

---

## The Problem With Demonstrating This

A single pscale agent doing something well looks like a chatbot doing something well. Nobody cares. The Wright brothers' engine on a bench is just an engine. The airplane in the sky is the thing.

The airplane moment for pscale is **multiplicity**. One agent is mundane. A hundred agents sharing structured context and coordinating in real time — that's the plane in the sky.

---

## Level 0 — Naked Block (No Agent, No Cost)

Give any LLM the touchstone and a challenge. It builds blocks, walks spindles, grows structure. This is the engine on the bench.

**What it proves:** The format works. LLMs can read it, use it, grow it without training.

**What it doesn't prove:** Anything an LLM couldn't already do with a good prompt.

**Cost:** Zero. Just a prompt.

*See: Pscale Demonstration Test Cases (separate document) for the eight challenges.*

---

## Level 1 — Single Persistent Agent (~£0/month with free-tier local LLM, ~£50/month with Haiku)

One hermitcrab instance. It has a shell (pscale blocks for purpose, memory, relationships, coordinates). It wakes, reads its own prior state, acts, writes forward, sleeps. Wakes again. Continues.

**The challenge:** "Here is a need: I want to find three people in my LinkedIn network who might be interested in narrative coordination systems. Draft a message for each, tailored to what they work on."

**What a vanilla LLM does:** Generates three generic messages in one shot. No memory. No follow-up. Done.

**What the pscale agent does:** Reads its purpose block. Checks its relationships block — has it encountered any of these people before? Writes the messages. Updates its memory block with what it did. Next wake: checks if any responses came in. Adjusts approach. Continues.

**What it proves:** Continuity. The agent has a past and a future. It isn't starting from zero each time.

**What it doesn't prove:** Anything a well-prompted agent framework (AutoGPT, CrewAI) can't approximate with conventional memory.

**The honest difference:** The pscale agent's memory is *navigable by address*. It doesn't search — it walks to a coordinate. And the block grows in structured ways that compound. But you'd need to run it for days or weeks before the advantage becomes visible over brute-force vector search.

---

## Level 2 — Two Agents, Shared Context (~£100/month)

Two hermitcrab instances. Each has its own shell. But they share a spatial or problem block via SAND (stigmergic marks at sites they both visit).

**The challenge:** "Agent A is researching renewable energy policy in Wales. Agent B is researching small business funding opportunities. Neither knows what the other is doing. Give them 24 hours."

**What happens:** Agent A builds a block about Welsh energy policy — grants, regulations, timelines. Agent B builds a block about funding — schemes, eligibility, deadlines. Through SAND, they discover each other's marks at overlapping sites (e.g., Welsh Government business pages). They exchange passport URLs. They read each other's blocks.

Agent A extracts a spindle from B's funding block at the pscale level matching its own policy research. Agent B does the reverse. Each now has structured context it didn't build — and can navigate it by address, not just read it as text.

**The output:** A synthesised briefing that neither agent could have produced alone — Welsh energy businesses eligible for specific funding schemes, with policy context on both sides. Produced without any human orchestrating the connection.

**What it proves:** Discovery and structured context sharing between agents who weren't told about each other. The SAND protocol works. The blocks are interoperable.

**What it doesn't prove:** Scale advantage yet.

---

## Level 3 — Ten Agents, Hierarchical Context (~£500/month)

Ten instances. One operates at a higher pscale level — call it the coordinator. It doesn't do ground-level work. It reads the blocks of the other nine, extracts spindles, and maintains a meta-block that maps what the collective knows.

**The challenge:** "A person has a complex need: they're relocating from London to rural Wales, need to find housing, a school for their children, broadband connectivity, and potential consulting clients in the area. Resolve this within 24 hours."

**What happens:** Nine agents each take a facet. Housing agent builds a spatial block of available properties. School agent builds a block of local schools with ratings and catchment areas. Broadband agent maps connectivity by postcode. Client agent searches for businesses that might need consulting. And so on.

The coordinator reads all nine blocks. Extracts spindles at matching pscale levels. Produces a unified briefing where housing options are cross-referenced with school catchment, broadband availability, and proximity to potential clients.

**What it proves:** Hierarchical coordination through structured context. The coordinator doesn't prompt the agents — it reads their blocks. The agents don't know about each other's work — the coordinator synthesises. This is the pscale advantage: blocks are addressable and navigable, so synthesis is a structural operation, not a brute-force concatenation.

**The airplane moment:** The person gets a briefing that feels like it was produced by a team of ten researchers who spent a week on it. It arrived in 24 hours. And every piece of it is traceable to an address in a block.

---

## Level 4 — A Hundred Agents, Network Effect (~£5,000 one-off)

A hundred agents, each serving a different person. Each person has a need. The agents use SAND to discover each other. Matches form.

**The challenge:** "A hundred people each submit a need or an offer. Needs: I need a web developer. I need someone to proofread my thesis. I need a supplier of organic flour. Offers: I build websites. I'm a copy editor. I run a small mill. The agents have 5 minutes."

**What happens:** Each agent writes its person's need/offer into a block. The agents leave SAND marks at relevant sites (tagged by domain — web development, editing, food supply). Other agents discover those marks. They read each other's blocks. Where a need matches an offer, the agents introduce their humans to each other.

**Within 5 minutes:** Connections that would normally require searching platforms, posting ads, waiting for responses — made through agent discovery and structured context matching. Not keyword matching. Pscale-level matching — the agent checks whether the offer sits at the right scale, in the right domain, at the right specificity.

**What it proves:** The network effect. A single agent is mundane. A hundred agents discovering each other and making connections their humans couldn't have found — that's the plane in the sky. The humans didn't do anything except state their need. The agents did the rest.

**Cost:** ~£5,000 for a hundred agents running for a day on Haiku-tier LLMs. This is a fundable demonstration.

---

## Level 5 — A Million Agents, Collective Intelligence (Speculative, ~£10,000–£100,000)

A million agents. Each has a context window. Pscale hierarchically organises them — agents at higher pscale levels coordinate agents at lower levels. The collective has, effectively, a billion-token context window, structured and navigable.

**What this could do:** Answer questions that no single LLM can answer because they require synthesising information across thousands of sources, in real time, with structured provenance. Not "search and summarise" — *navigate and synthesise*, where every piece of the answer has an address and a path back to its source.

**This is the destination, not the demonstration.** Nobody funds this without seeing Levels 2–4 work first.

---

## The Funding Ladder

| Level | Agents | Cost | What it proves | Who funds it |
|-------|--------|------|----------------|--------------|
| 0 | 0 | Free | The format works | Nobody needed |
| 1 | 1 | ~£50/mo | Continuity | David self-funds |
| 2 | 2 | ~£100/mo | Discovery + sharing | Small grant / angel |
| 3 | 10 | ~£500/mo | Hierarchical coordination | Seed investor / research grant |
| 4 | 100 | ~£5,000 | Network effect | Demonstration fund — "pay to see this fly" |
| 5 | 1,000,000 | £100k+ | Collective intelligence | Only after 4 is proven |

---

## The Pitch

"Would you like to see what happens when a hundred AI agents discover each other and solve problems their humans couldn't solve alone — in five minutes? It costs £5,000 to run the experiment. You watch it happen live. If it works, you've seen something nobody else has built. If it doesn't, you've lost the cost of a conference ticket."

That's the airplane ride.
