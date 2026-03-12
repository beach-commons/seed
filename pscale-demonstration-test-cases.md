# Pscale Demonstration Test Cases

*Give any LLM the touchstone (pscale block mechanics + BSP). Then ask it to do these. No special training. No fine-tuning. Just the block and the walk.*

---

## The Method

1. Provide the LLM with the pscale block specification (the touchstone)
2. Pose a challenge from the list below
3. The LLM builds the block, navigates it, and produces results
4. Compare with what a vanilla LLM does without pscale — same prompt, no block

The demonstration is the difference.

---

## Test Cases

### 1. Spatial Navigation

**Prompt:** Here is a castle in a forest. The castle has a keep, a courtyard, and stables. The keep has a kitchen, a great hall, and a tower. The forest has a clearing, a river crossing, and a ruined chapel. Create a pscale block mapping these locations. Now: I am standing in the kitchen. I walk through the great hall, out into the courtyard, through the gate, and into the forest toward the river crossing. Narrate my journey using spindles at each step.

**What it demonstrates:** Spatial containment, BSP navigation producing contextualised descriptions at each location, the underscore providing ambient "where am I" context at every step.

### 2. Temporal Mapping

**Prompt:** Create a pscale block for a single day. Morning, midday, afternoon, evening, night. Under morning: wake, breakfast, commute. Under midday: three meetings. Now extract a spindle for the second meeting. Then add a new entry — an unexpected phone call after the third meeting — and show how the block grows.

**What it demonstrates:** Sequential digit assignment, temporal containment (day > period > event), growth by adding entries, the underscore summarising each time period.

### 3. Document Compression

**Prompt:** Here are the FIDE chess rules [or any structured ruleset]. Convert them into a pscale block. Now extract a spindle for the castling rules. Then extract a spindle for en passant. Compare the two spindles — what context do they share, where do they diverge?

**What it demonstrates:** Rendition mode (0.x), analytical decomposition, spindle extraction producing contextualised rule retrieval, comparison between spindles showing shared ancestry in the tree.

### 4. Dual-Spindle Story Generation

**Prompt:** Here is a story block — a world with locations, characters, and a situation. Here is a director block — tone, pacing, themes, narrative constraints. Extract one spindle from each. Now write a scene that is the product of both spindles simultaneously.

**What it demonstrates:** Two blocks with different tunings, spindle extraction from each, the LLM holding two structured contexts and producing something that honours both. This is the grain operation — meld.

### 5. Problem–Solution Synthesis

**Prompt:** Here is a problem block describing a complex situation (e.g., a team with communication failures, missed deadlines, unclear roles). Here is a resource block describing available tools, people, and budget. Extract a spindle from each at the same pscale level. Now synthesise a solution that draws on both.

**What it demonstrates:** Cross-block operation, matching pscale levels between different blocks, the LLM using structured context from two sources to produce a response that neither block contains alone.

### 6. Block Comparison

**Prompt:** Here are two spatial blocks mapping two different buildings. Compare them. Where are they structurally similar? Where do they diverge? What would a merged block look like?

**What it demonstrates:** The grain compare and merge operations. Structural correspondence between blocks with different content. The LLM reading two blocks and identifying patterns across them.

### 7. Self-Extending Block

**Prompt:** Here is a pscale block with three entries. Now I will give you five new pieces of information, one at a time. After each one, add it to the block at the right position. When digits 1–9 fill, supernest and continue. Show me the block after each step.

**What it demonstrates:** Live block growth, the supernesting mechanic in action, the underscore chain extending, the LLM managing its own structured memory across a conversation.

### 8. Context Continuity

**Prompt:** Here is a block from a previous session. It contains a purpose, a partial plan, and notes on what was tried. Read it. Tell me where we left off. Propose the next step. Then update the block to reflect your proposal.

**What it demonstrates:** The core hermitcrab function — an LLM waking into a block, reading its own prior state, continuing with coherent purpose, and writing forward for the next instance. This is the one that changes everything.

---

## What To Look For

The vanilla LLM will answer all of these prompts. It will narrate the castle, discuss chess rules, write the story. The question is not whether it can respond — it always can.

The question is whether the pscale version produces **structured, navigable, reusable context** that compounds across interactions. Can you take the block it built in test 7 and hand it to a different LLM instance for test 8? Can the spindles from test 4 be recombined for a different scene? Can the spatial block from test 1 be extended by a second LLM that adds new locations?

Pscale doesn't make the LLM smarter. It makes the LLM's output **addressable** — and therefore composable, navigable, and persistent. That is what no other system does.
