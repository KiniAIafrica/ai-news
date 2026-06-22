# Brainstorm Extraction & Updated Design Direction
### Captured from the founder + co-founder session

> Purpose: capture **every idea, mechanic, direction, tension and open question** from the brainstorm so nothing is lost, organised so you can decide the next steps. Tags: **[DECIDED]** leaning agreed · **[OPEN]** still to decide · **[NEW]** new this session · **[ADVANCED]** later-tier idea · **[PRODUCT]** hardware/digital product idea.

---

## 0. The big shifts this session (read this first)

1. **[NEW][DECIDED-ish] The game now STARTS with building a "Model Card."** Before any data or compute, each player/team assembles the *spec* of the AI they must build (what it does, how fast, what modality, who it's for…). This is a real industry artefact (released models ship with a "model card"). It becomes the first activity *and* the engine of replayability.
2. **[NEW] The win condition is shifting** from "first to launch a working product" → **"first to MEET THE SPECS of your Model Card"** (accumulate points across parameters). Still an open choice — see §5.
3. **[NEW] It's fundamentally a RESOURCE game** — financial, intellectual, physical resources — grounded in **real-world constraints** (chip scarcity, power, water, training time, environmental cost).
4. **[NEW] Consequences must be real, not cancel-out.** Inspired by the anti-AI-in-education critics: the game should teach the *true* economic, environmental and societal footprint of building AI — not hand-wave it.
5. **[NEW][PRODUCT] An "AI Game Master"** — a human umpire role, and later a physical voice device / app that reads cards, settles disputes, rolls digital dice, tracks state, and updates over time.

---

## 1. The Model Card system (the new heart) **[NEW]**

- **What it is:** the starting "spec sheet" of the AI you must build. Everyone builds *to a spec*, not vaguely "an AI."
- **Three categories** (top level) **[DECIDED]:** **Generative AI** · **Classifier** · **Predictive/Algorithmic**.
  - Generative → chatbot/text, code, image, video, audio (incl. multimodal).
  - Classifier → crop-disease detector, X-ray "has it / doesn't," spam filter, image/voice ID.
  - Predictive → recommendation engine (TikTok-style), credit scoring, forecasting.
- **How a Model Card is assembled [NEW]:** draw **attribute/variable cards** that combine into a spec, e.g.:
  - latency / speed ("responds in 10 ms," "real-time voice"),
  - modality ("works with image," "voice output," "multimodal: text+image+video"),
  - task type ("classification," "generation," "ranking"),
  - audience ("for individuals" vs "for a corporation"),
  - quality / intelligence level, safety needs (e.g., hospital = low randomness/temperature).
- **Colour/adjective draw mechanic [NEW]:** attributes grouped by "colour" (e.g., blue/red/yellow/green = different spec categories), with options inside each, drawn so combinations are **varied** and not duplicative. Goal: mixed, distinct model cards each game.
- **Compatibility rules [NEW]:** some spec combinations are **incompatible** — pick a clashing spec and "you've lost your chance"/wasted a slot. So **assembling a valid Model Card is itself a skill/mini-game**; some players get stuck here while others advance.
- **Minimum thresholds [NEW]:** a Model Card must meet a **minimum approval criteria**; exceeding the minimum unlocks downstream choices/effects (and carries ongoing costs, e.g., "every month you pay X to cool/run this").
- **Predetermined products (Version 1 simplification) [NEW][DECIDED-ish]:** instead of free-form, ship **predefined product tasks** per category ("Your task: build a hospital chatbot"). The *outcome* is fixed; the player must **figure out the path** (what data, architecture, training, compute) by trial and error. This teaches the decision process without overwhelming beginners.
- **Why this matters:** the Model Card determines the **data you need, the architecture, the constraints** — and its near-infinite combinations are the answer to the **replayability** worry (see §16).
- **Core lesson it carries [NEW][IMPORTANT]:** *fit-to-purpose beats biggest/best.* A real-time chatbot needs **speed**, not max intelligence; a hospital bot needs **low randomness**. Knowing the right thing to build is the strategy.

---

## 2. The build stages (pipeline) **[DECIDED]**

The agreed development flow (also doubles as the learning spine). A printed **rulebook/cheat-sheet** lists "what a typical AI build needs at each stage" — *not* game rules, but real-world orientation for players who know nothing about AI.

| Stage | What happens | Key options / decisions |
|---|---|---|
| **0. Model Card** | Define the spec (see §1) | category, scale, attributes, compatibility |
| **1. Data** | Gather data matching the spec | license clean · scrape/"steal" web · build/crowdsource own · open-source · synthetic. Sub-decision: **clean & label** (cost vs quality; bias/hallucination risk). Format depends on model (multimodal needs image+video+text). |
| **2. Compute** | Secure training capacity | rent cloud · buy GPUs / own data centre · grants. Needs **chips + power + water**. Training time = f(model size, data, compute). |
| **3. Pre-training** | Pick **architecture** + **approach** | Architecture must fit category: Generative→**Transformer** (text/audio), **Diffusion**/**GAN** (image/video); Classifier→**CNN**, **Vision Transformer**. Approach: **from scratch** (high cost/time, high quality if data good) · **transfer learning / distillation** (low cost/time, good if good teacher) · **self-supervised** (medium/medium/high). Must **check under/overfitting** (false positives, fails on new data). A combo of data×method×GPU×runtime → a **score**; hit threshold to pass the gate. |
| **4. Fine-tuning** | Specialise to the goal | different methods (e.g., RLHF/reinforcement learning) by objective. **Only valuable if you already have a base model** (dependency). Talent/experts help here. |
| **5. Testing & Evaluation** | The gate before market | benchmark · **red-teaming (safety)** · **bias audit** · beta test. Option to **skip and rush** (risk scandal/trust-crash). Takes time (skip a turn). A **"business consultant" card** can help evaluate market-readiness. |
| **6. Market** | Does it succeed? | Launch; draw **market cards** (hallucination, reliability, trust, safety, user feedback, virality, competitor moves). Win = meets market-success threshold (trust + safety + use-case fit). |

- **[NEW] "Connect-the-pipes" evaluation idea:** maybe you **don't test mid-way** — you make all decisions, then **at the end everything comes together** like water flowing through connected pipes. If the "water reaches the end," it works; if not, you go back. Hints/explanations can be given.
- **Dependencies [DECIDED]:** can't fine-tune without a base model; no base model without pre-training; no pre-training without data. Some assets are **locked** until prerequisites exist.

---

## 3. Movement & board structure **[OPEN — biggest open question]**

Everyone agreed: **roll dice to move** (Monopoly feel); **where you land determines what you can do**; you **move around to gather resources**. But the *shape* is undecided. Options discussed:

- **Option A — One shared Monopoly loop.** All resources/spaces spread on one track. You might land on things **not relevant to your current stage** (harder, longer, more luck). Everyone shares the board.
- **Option B — Rings per level.** Separate loop for each stage/level; you circle **your** level's ring (everything there is relevant to you); finishing a level moves your avatar to the next ring. Stage 7 (market) you stop rolling / it takes longer.
- **Option C — No strict levels (leaning) [DECIDED-ish].** Model-Card development is **off the board** (a pre-stage activity). Then there's **one resource-gathering board**; you roam to buy what you need; **dependency locks** (not board rings) enforce order. "Your goal is to build to spec; while moving around you collect."
- **"Docking station" imagery:** stages drawn as a grid/path from level 1 → market/end; each player's **avatar sits at their current stage** so everyone sees who's where. **Can't skip steps** — unless a **surprise card** lets you skip (e.g., skip pre-training) or you **get sued and move back** (re-gather data).
- **Sub-question [OPEN]:** are levels about being **exposed to different things** or **able to do different things**? (Founder note: maybe the wrong question — decide the *dynamics* first, then the physical layout follows.)
- **Forcing progression without rigid levels [NEW]:** use **money + dependencies** as the gate — e.g., "you need money before you can buy data" or "wait N rounds for free data." The need to afford/unlock things naturally pushes players through the order.

---

## 4. Resources & economics — "it's a resource game" **[NEW][CENTRAL]**

**Three resource classes:** **Financial** (money) · **Intellectual** (talent / ML experts) · **Physical** (compute/GPUs/data centres/data/power/water).

### Getting money **[OPEN — needs a clean rule]**
- **Base start:** everyone starts equal (e.g., $500 or $5,000) — only ~**20%** of what's needed → you **must earn more**.
- **Pass-"Go" salary:** collect an amount each lap; **maybe not fixed** — based on what you own (your "salary").
- **Investor cards [NEW]:** a shuffled deck; land on a spot to draw. **Small amounts ($1–2k) unconditional; big amounts ($50k+) conditional** — you must already hold certain assets/milestones to qualify (mirrors real fundraising). Teaches "what do you need to attract big investment?"
- **Selling to players:** if you grabbed a scarce resource first, **resell at a markup** (but everyone building the same thing complicates timing).
- **Chance/Surprise money:** random small payouts.

### Spending money
- Buy data, compute, talent, power, etc. **Land first → buy from the bank/state; already owned → negotiate** with the owner (Monopoly trading).
- **Initial money deliberately insufficient** → movement-to-earn is the engine that makes the game move.

### Scarcity & realism **[NEW][IMPORTANT — addresses "don't cancel out reality"]**
- **Compute is genuinely limited** (real chip scarcity). The shop can say **"not available."** A player can **buy up all compute** and resell at a premium. Sometimes **players must unite** to collectively afford/unlock something (e.g., chips) or it stays unavailable.
- **Data-centre = chips + power + water.** Each is a constraint.
- **Power as ongoing cost:** every turn you **pay to run** your assets; you must **buy power**; bigger footprint = higher running cost.
- **Training takes TIME:** while training you **can't move for N turns** (others keep playing). Bigger model = longer wait. (e.g., "your model trains for 3–6 months.")
- **[ADVANCED] Chip geopolitics:** semiconductors need multiple countries' inputs (bottlenecks); export restrictions; "buy early vs run short" (OpenAI-aggressive vs Anthropic-conservative-then-constrained; Colossus leasing). *Use as advanced-tier flavour; treat figures as illustrative, not exact.*

---

## 5. Win condition **[OPEN — decide]**

Multiple framings surfaced; needs a decision:
- **(a) Meet your Model-Card specs first (leaning) [NEW].** Accumulate points across spec **parameters** (quality, latency, market acceptance, **societal acceptance, economic impact, environmental, human capital**). First to check off all = win. Supports replayability + fit-to-purpose lesson.
- **(b) First to launch a successful product** (current prototype).
- **(c) Highest efficiency / most sustainable product at the end** — compare everyone's scope; **"most efficient wins"** ("maybe that's the ethics of our game").
- **(d) Continuous ranking** (chess/Pokémon/D&D-style) — accumulate over time, **fight other players** (more points likely beats fewer), no fixed end. Raised as inspiration.
- **Tension:** **a game that ENDS vs one that CONTINUES.** Leaning: reaching market shouldn't be the whole story — **what you built and its footprint matter** to the final score.

---

## 6. Societal / environmental / economic consequence layer **[NEW][IMPORTANT]**

The realism layer that answers the AI-critics:
- **Three meters evaluated throughout:** **Economy · Environment · Human Capital.** (Like a strategy game's "citizens' happiness.")
- **Over-gathering / big data centres / high compute → environment score drops**; warnings surface ("be mindful of alternatives… mine for power vs damage the environment").
- **Mitigations score back:** build a **solar farm / water plant / community impact** → offsets penalties, earns **green points**. Sustainable choices have a caveat that protects your score.
- **Anger/backlash mechanic:** protests against data centres; your build making compute/RAM expensive for others → you must respond (community impact) or take penalties.
- **Everything is a measurable point** tied to these factors; thresholds force trade-offs. A great model that wrecks the environment can still lose.

---

## 7. Cards & decision system **[partly DECIDED]**

- **Per-stage decision decks** (pros/cons each) **+ cross-cutting decision cards** that apply at any stage **[OPEN: what those look like]**.
- **Four outcome types [DECIDED]:** **Advance · Delay/Stuck · Setback · Catapult/Bonus.**
- **Card types:**
  - **Chance / "Surprise"** — checks & balances; random (e.g., win $500; **tax card: "pay 10% on every property above $X"** → punishes hoarding, ties to economy).
  - **Trade** — exchange resources / make deals ("$100M and you skip 2 rounds next time you land on my property").
  - **Investor** — money, conditional for big sums (see §4).
  - **Jail** — fail an obligation / draw a card → **pay or roll a specific number** to get out.
- **Card design [DECIDED]:** **Front** = the asset/spec + cost (colourful, game-first). **Back** = plain-English explanation (how data was sourced, what the method is) **+ QR code** → online lesson / **LLM read-aloud**. *Each turn = a decision + a micro-lesson.*
- **Dynamic cards [NEW]:** a card's **value changes with state** — an untrained model vs a trained one (e.g., 500 → 1,000 pts). Need a **physical way to reflect current state** (tokens, trackers, a "vault" to show you've levelled up).
- **[OPEN] Scorekeeping:** paper vs **custom physical tokens** vs **digital tracker**.

---

## 8. Talent / experts **[DECIDED]**
- Hire **AI/ML experts at levels**; gives leverage/points and help with stage decisions (esp. fine-tuning). Intellectual resource. **Only useful with prerequisites** (a base model to fine-tune).

---

## 9. Tiers / complexity **[DECIDED direction]**
- **Beginner / Intermediate / Advanced**, mapped to **primary / secondary / tertiary / family / general**.
- **Don't expose all decision cards at beginner** (avoid overwhelm). Progressive unlock (financial-literacy-game style): each level reveals more, resources grow, alliances form.
- **Advanced:** semiconductors/chip geopolitics, full environmental scoring, market dynamics.
- Founder leaning **simple for MVP**, knowing the depth lives in the decisions/variables, not extra rules.

---

## 10. Team & social dynamics **[OPEN]**
- **Solo, or teams** that decide moves together ("this move because of X").
- **Same vs different builds [OPEN]:** everyone builds the **same** Model Card (drawn together, no favouritism) → **compete for the same resources**; or **different** cards → variety, less head-to-head. Or **same category, different specs**.
- **Cooperate vs interfere:** "I can be a wrench in your wheel, or we work together." Alliances; collective purchases (chips).

---

## 11. The Game Master **[NEW][PRODUCT]**
- **Human umpire/evaluator** — a non-player who runs evaluation; "all these games have that person"; they learn too.
- **[PRODUCT] AI Game Master device:** physical unit with **speaker, mic, memory**; **no Wi-Fi needed** (downloadable upgrades); a **persona** that reads cards aloud, narrates, and **settles rule disputes** ("per the rulebook, you can't proceed"). LLM-plugged.
- **Digital dice / app:** logs in players, rolls digital dice, **auto-tracks scores/state**, remembers everything, can auto-play absent players.

---

## 12. Physical / digital hybrid & longevity **[NEW][PRODUCT]**
- **Physical board + tokens**; tokens **transfer to a platform** → continue online/offline, **carry progress** (chess-like persistent ranking).
- **Digital extension = "unlimited resource":** templates with variables → **infinite content**, a game that "never ends" (vs a fixed physical box).
- **Pushed updates:** fix/extend rules over time so the game **never goes stale** (solves the classic "we should have changed that rule" problem).
- **Online → ratings/feedback:** products get tested/rated; ratings feed points. **Offline → learn via cards.**
- **[NEW] Per-stage SIMULATION:** before passing a stage, **run your decisions through a sim** to check they fit your Model-Card goal; it tells you if you chose wrong → go back / change model. "The market is **our own system**" — simulate expected outcomes (the pipe/water metaphor).

---

## 13. Replayability **[DECIDED solution]**
- Co-founder flagged the current prototype as **low replayability** ("options too low, no surprise on return").
- **Fix = the Model Card's near-infinite combinations** + predetermined-product library (AI-expandable) + dynamic cards + pushed digital content.

---

## 14. Core teaching goals (keep these front-of-mind)
1. **Fit-to-purpose > biggest/best** (right tool for the spec).
2. **The real build pipeline** (data → compute → pretrain → finetune → test → market) and its **dependencies**.
3. **Right architecture for the task** (Transformer/Diffusion/GAN/CNN; under/overfitting).
4. **Resource scarcity & economics** (chips, power, water, money, talent, time).
5. **Real consequences** (economy, environment, society) — no hand-waving.
6. **Decision-making under constraints** = the fun and the learning.
7. Opens players' minds to **what AI can be built** and how to **scope a solution**.

---

## 15. Known issues with the current prototype (to fix later)
- On **mobile**, the setup screen "bunched up" / didn't show options properly (worked on desktop). → needs a **mobile-friendly layout** and clearer setup.
- **Replayability too low** in current version → the Model-Card system addresses this.
- It "didn't fully do what I wanted" but **helped bring it to life** (useful as a thinking tool).

---

## 16. The biggest open decisions (consolidated → see questions)
1. **Win condition:** meet-the-spec (points) vs first-to-market vs efficiency vs continuous ranking.
2. **Board/movement shape:** one shared loop vs per-level rings vs no-levels resource board.
3. **Same vs different builds** per player/team.
4. **Where Model-Card building happens** (off-board pre-stage vs on-board).
5. **Money rule** (pass-Go salary vs investor-only vs hybrid; conditional big money).
6. **End vs continuous** game; solo vs team.
7. **MVP scope** — how much realism (environment/economy) and digital (sim, AI GM) in v1.

---

## 17. Recommended next steps (proposal)
1. **Lock the core loop** via the questions below.
2. I build a **Model-Card generator** (digital) so you can *see* the near-infinite spec combinations and the compatibility rules — the heart of replayability.
3. Rebuild the **digital simulation** around the new direction (Model-Card → resource-gathering board → spec-completion win), **mobile-friendly**.
4. Draft the **printed rulebook + the "AI build cheat-sheet"** (real-world orientation) and a **print-and-cut card set** (Model-Card attributes, data, compute, decisions, chance/surprise/trade/investor).
