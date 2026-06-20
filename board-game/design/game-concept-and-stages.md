# Game Concept & Stage Details — "Build an AI"

> The complete game concept (win/lose, luck, progression, turns) plus **the decision options at every stage**. This is the design we'll turn into a clickable **digital simulation**. Recommendations are marked ★ — confirm/adjust and we build to it.

---

## A. The core concept (answering your questions directly)

### What is the game?
A **strategy board journey** (Monopoly × Snakes-&-Ladders feel) where each player builds an AI product through real phases — **Define → Data → Compute → Pretraining → Fine-Tuning → Testing → Market** — making decisions that can move you **forward, back, delay you, or catapult you**. The decisions are real AI-building choices, so you learn by playing.

### What does it mean to WIN? ★
**Be the first to launch a model that *succeeds in the market.*** Reaching the market is **not enough** — your product must pass **Testing** and then earn enough **Market Success** (a Trust + Quality threshold) to be declared a winner. *This is the key design choice:* a player who rushes and ships a bad model can "arrive" first and still **lose**, because their AI hallucinates/flops. This teaches that *doing it right beats doing it fast.*

### What does it mean to LOSE?
- **Soft loss (friendly mode):** you simply don't launch a successful product first.
- **Hard loss / "Model Failed" (intermediate+):** your **Trust hits zero** (a catastrophic scandal/hallucination) or you **run out of money** before launch — you're knocked out.

### Is it competitive? How? ★
Yes — three dials, recommended **medium**:
- **Race:** everyone is rushing the same finish.
- **Shared scarcity:** limited data/compute/talent in a central **Market Row**; if a rival grabs the best GPU cluster, you can't.
- **Direct interaction (Monopoly-style):** some cards let you **poach a rival's researcher, out-bid them for data, or trigger an audit on them.** (Can be toggled off for a gentler family game.)

### Is there luck? Dice? ★
**Yes, but strategy dominates.** Luck keeps it fun, social, and lets weaker players catch up:
- **Dice** = your **base movement / "time passing"** each turn (the Monopoly feel).
- **Event/Chance cards** = the surprises (a breakthrough, a power cut, a viral launch).
- **Your decisions** = what actually determines whether you win (which data, method, fine-tuning, whether you test). *Roughly 70% skill / 30% luck.*

### What determines progress?
Two things together:
1. **Dice movement** along the path (luck + pace).
2. **Stage gates:** to leave a zone you must **complete that stage's requirement** (e.g., you can't enter Pretraining until you hold enough Data + Compute). So a player can be physically ahead on the board yet **stuck at a gate** because they skipped a step.

### Turn mechanics — extra turns & waiting (the "watch your turn" bit) ★
On your turn: **Roll → Move → Resolve the space → (apply any card effects) → End.** Cards and outcomes can:
- **ADVANCE** — jump forward / clear a gate.
- **SETBACK** — sent back toward the previous stage.
- **DELAY** — **skip your next turn** ("model is retraining / debugging").
- **CATAPULT** — **take an extra turn** or leap ahead.
So yes — some cards make you **wait a turn**, others grant an **extra turn**, exactly like the tension in Monopoly/Ludo.

---

## B. The flow: 7 stages and the decisions at each (the detail you asked for)

Every stage offers a small menu of **options** with trade-offs across four currencies: **₦ Money · ⏳ Time (turns) · ⭐ Quality · 🛡 Trust** — and a hidden **⚠ Risk** that may trigger a snake later. For the **foundation** we surface ~**3 options per stage**; more unlock in intermediate/advanced.

### Stage 0 — DEFINE THE PROJECT (sets your difficulty)
First you pick **your Model Category**, then a **Scale** and a **Use-Case** card. These set what data/compute/methods you'll need and how rich the reward is.

**The 3 Model Categories** (your revised list):
| Category | Examples | Needs (data) | Typical methods | Signature risk |
|---|---|---|---|---|
| **1. Generative AI** | text/chatbot, code, image, video, audio | huge text / image-caption / audio pairs | **Transformer** (text/code/audio), **Diffusion** or **GAN** (image/video) | **Hallucination**, copyright, deepfakes |
| **2. Classifier** | crop-disease detector, spam filter, X-ray reader, face/voice ID | **labelled** examples | **CNN / Vision Transformer**, **gradient-boosted trees** (tabular) | **Bias**, fails on new/unseen data |
| **3. Predictive / Algorithmic** | recommendation engine (TikTok-style), credit scoring, demand forecast | **behaviour / transaction** logs | **collaborative filtering**, **neural nets**, **gradient boosting** | **Filter bubbles**, unfair/again-the-user outcomes |

**Scale options:** ★
- **Lean (MVP)** — low ₦/⏳, modest reward, easier to win the race.
- **Standard** — balanced.
- **Frontier** — high ₦/⏳/compute, biggest market reward, biggest risk.

### Stage 1 — DATA GATHERING (the real start)
| Option | ₦ | ⏳ | ⭐ Quality | ⚠ Risk |
|---|---|---|---|---|
| **License a clean dataset** | high | low | high | low (safe) |
| **Scrape the web** | low | low | medium | **high** — copyright lawsuit / noisy & biased data |
| **Collect/crowdsource your own** | medium | **high** | high (tailored) | low |
| *(adv.) Synthetic data* | medium | medium | varies | model can "learn its own mistakes" |
**Sub-decision:** spend a turn on **cleaning/labelling** (+⭐, −⏳) or skip it (risk a Bias/Hallucination snake later).

### Stage 2 — COMPUTE / DATA CENTRE
| Option | ₦ | ⏳ to train | Notes / ⚠ |
|---|---|---|---|
| **Rent cloud (pay-as-you-go)** | per-turn cost | flexible | scales to any size; ongoing drain on ₦ |
| **Buy GPUs / own data centre** | big upfront | faster long-run | ⚠ **power cut (NEPA)** events unless you hold a Generator perk |
| **Grant / free credits** | free | limited | can **run out** mid-training (delay) |
**Mechanic:** training takes **⏳ = (model scale × data size) ÷ compute power.** Under-buy compute → **under-trained model** (weak ⭐, a snake at Testing).

### Stage 3 — PRETRAINING (architecture + training approach)
You choose **(a) the architecture** (must fit your category) and **(b) how you train it**:
**(a) Architecture — pick the right one for your category** (right = ladder, wrong = snake):
- Generative → **Transformer** (text/audio/code) · **Diffusion** or **GAN** (image/video)
- Classifier → **CNN / Vision Transformer** · **Gradient-boosted trees** (tabular)
- Predictive → **Collaborative filtering** · **Neural net** · **Gradient boosting**

**(b) Training approach (the top-3 foundation options):** ★
| Approach | ₦ | ⏳ | ⭐ | When it's smart |
|---|---|---|---|---|
| **From scratch** | high | high | high (if data is good) | you have huge clean data + compute |
| **Transfer learning** (start from a foundation model) | low | low | high | the usual smart move — fast & strong |
| **Self-supervised pretraining** | medium | medium | high | lots of *unlabelled* data |

### Stage 4 — FINE-TUNING (specialise + align)
| Method | ₦ | ⏳ | Effect | 
|---|---|---|---|
| **Full fine-tuning** | high | high | strong specialisation |
| **LoRA / lightweight (PEFT)** | low | low | efficient, cheap specialisation |
| **Instruction tuning** | medium | medium | makes it follow user requests |
| **RLHF (human feedback)** | high | high | **aligns to humans, cuts toxicity/hallucination** (+🛡) |
| **RAG (retrieval) — a "perk" card** | medium | low | grounds answers in real sources (**big −hallucination**) |
**Good tuning → ladder (+⭐ +🛡). Skipped/poor tuning → Hallucination snake.**

### Stage 5 — TESTING & EVALUATION (the gate before market)
You must **pass a threshold** to launch. Options (you can do several):
| Test | ₦ | ⏳ | What it catches |
|---|---|---|---|
| **Benchmark eval** | low | low | overall ⭐ quality score |
| **Red-teaming / safety** | medium | medium | harmful/unsafe outputs (+🛡) |
| **Bias / fairness audit** | medium | medium | discrimination (+🛡, avoids scandal) |
| **Beta test with users** | medium | high | real-world failures before launch |
**Skip testing → rush to market but risk a catastrophic Market scandal (Trust crash / hard loss). Thorough testing → trusted launch (ladder).**

### Stage 6 — MARKET / DEPLOYMENT (does it actually succeed?)
Launch, then over a few turns draw **Market cards** that test your product:
- **User feedback** (good reviews +Success; complaints −Trust),
- **Virality** (catapult), **competitor move**, **regulation/policy** check,
- **incident** (if you skipped testing, this is where it bites).
**You win when your launched product reaches the Market Success threshold** (enough ⭐ × 🛡 × use-case fit). A strong, trusted model gets there fast; a rushed one stalls or fails.

---

## C. The decision-outcome system (importing & customising Monopoly)

Every Decision/Event card resolves into one of four outcomes you described:
- **➡ ADVANCE** (forward / clear a gate / +resource)
- **⬅ SETBACK** (back toward previous stage / −resource)
- **⏸ DELAY** (skip next turn)
- **🚀 CATAPULT** (extra turn / leap / perk)

Plus **Perks** (Monopoly-style assets you keep): *Clean-Data Pipeline, GPU Sponsor, Generator (beats power cuts), Safety Team (one free test), Star Researcher (re-roll), Open-Source Boost (skip part of pretraining).*

---

## D. The cards as assets (your colourful + QR spec)

Every card is a **learning object**:
- **Front:** the choice/asset, an icon, and key stats (₦ / ⏳ / ⭐ / 🛡 / ⚠) — colourful, game-first.
- **Back:** a 1–2 line **plain-English explanation** ("*Diffusion models build images by removing noise step by step…*") **+ a QR code** linking to a fuller lesson on your website.
So each turn = a **decision** *and* a **micro-lesson**. The QR packs also let us refresh content as AI changes.

---

## E. Tiers (decide later, noted now)
Beginner / Intermediate / Advanced can be **(a)** separate boxes, **(b)** add-on packs, or **(c)** one box that "folds" — only the foundational layer revealed at first, deeper rules unlocked later. *We lock the foundation first; choose the packaging later.*

---

## F. What I'll build: the digital simulation
A **clickable web simulation** (runs in a browser) so you can *see and feel* it:
- the **board layout** with the 7 zones and snakes/ladders,
- **2–5 player tokens** (you can let the computer auto-play rivals to **simulate competition**),
- **dice roll**, **card draws**, the **₦/⏳/⭐/🛡 dashboards**, and stage-gate logic,
- a log that explains each outcome (so you watch the strategy unfold).
This lets us test pacing, luck balance, and whether the decisions feel meaningful — *before* spending a naira on printing.

---

## G. To build the *right* simulation, three rules to confirm
(Questions sent separately — they shape the core loop.)
