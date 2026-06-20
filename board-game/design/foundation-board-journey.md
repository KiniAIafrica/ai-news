# Foundation Design — "Build an AI" (board journey: Snakes & Ladders × Monopoly)

> This is the **foundation** (the simple core that must work first). It captures the agreed direction: a **board journey** where you **pick what kind of model to train**, then travel from *idea → market* making decisions — **ladders** for good calls/perks, **snakes** for bad calls/setbacks. Training methods (Transformer, Diffusion, GAN…) are the methods you apply at the training stage, decided by your model type. Complexity layers on later; see "What we add later."

---

## 1. The one-sentence game

> *Pick a type of AI to build, then journey from idea to market — gathering the right data, compute, and training methods, while good decisions speed you up (ladders) and bad ones set you back (snakes). First to launch a working, trusted product wins.*

- **Players:** 5–10 (up to 5 solo tokens; 6–10 play as teams of 2).
- **Length:** ~30–40 min (foundation).
- **Feel:** roll-and-move board (Snakes & Ladders) + money, assets, and decision spaces (Monopoly).
- **Why it teaches:** to win you must make the *real* decisions of building your chosen AI — so you learn the pipeline, the methods, and the risks by living them.

---

## 2. The board: a journey in 6 zones

You travel a single winding path (Snakes-&-Ladders style) divided into **6 zones**. Each zone is a real stage of building an AI. Ladders and snakes connect spaces within and across zones.

```
 START ─ DATA ─────── COMPUTE ────── THE FORGE ───── FINE-TUNE ───── THE MARKET ─ FINISH
[Pitch] [District]     [City]       [Pretraining]      [Lab]          [Deploy]
  │        │             │              │                │               │
 pick    gather        rent/buy       train base      specialise      launch, user
 your    the RIGHT     data centre    model using     + safety/RLHF   feedback, use
 model   data for      + compute      the RIGHT       (good tuning    cases, market
 type    your model    time           method          = ladder; bad   reaction →
                                      (Transformer/    = hallucination  score product
                                       Diffusion/GAN)   snake)
```

| Zone | What you do | Example LADDER (good decision/perk) | Example SNAKE (bad decision/setback) |
|---|---|---|---|
| **1. The Pitch (Start)** | Choose your **Model Card** (see §4). | Pick a model that fits cheap available data → smooth start. | Pick an over-ambitious model with no data → slow start. |
| **2. Data District** | Collect the **right data** for your model. | *Clean, diverse, well-labelled data* → climb a ladder (quality boost). | *Scraped copyrighted data* → lawsuit, back 4 spaces + fine. |
| **3. Compute City** | Rent/buy **data centre + compute time**. | *Secured a GPU cluster / sponsor* → faster training perk. | *NEPA power cut, no generator* → lose a turn. |
| **4. The Forge (Pretraining)** | Apply the **method your model needs** (Transformer/Diffusion/GAN/CNN). | *Used the right, modern method* → climb. | *Cheap/wrong method or under-trained* → weak model, back to Data. |
| **5. Fine-Tune Lab** | Specialise + safety (RLHF, evaluation). | *Good fine-tuning + safety testing* → fewer hallucinations, climb. | *Skipped safety* → toxic-output scandal, lose Trust, back 3. |
| **6. The Market (Deploy)** | Launch; face **user feedback & use-case** cards. | *Strong eval before launch* → trusted launch, bonus score. | *Shipped a hallucinating product* → bad reviews, Trust crash. |

**Movement (foundation):** roll a die to move (the familiar Monopoly/Ludo feel). *Later we can replace the die with spending "compute time," so training literally takes time — but not in the foundation.*

---

## 3. The four things you manage (kept minimal for the foundation)

Foundation uses just four, tracked with tokens/a score card:

1. **₦ Money** — buy data, compute, methods, perks.
2. **Data** — the right *type and quality* for your model.
3. **Compute** — needed to train; bigger model = more compute.
4. **Trust** — your product's reputation. Hallucinations, bias, and skipped safety **cut Trust**; good data and testing **raise it**. *Trust is what separates a fast-but-bad AI from a good one.*

> Foundation win = **first to reach The Market with a working product** (minimum Data quality + Compute + Trust met). Later/advanced win = **highest Product Score** = Quality × Trust × Market-fit.

---

## 4. Model Cards — "what kind of AI are you building?" (your branching idea + the AI research)

At the start, each player/team draws or picks a **Model Card**. This **changes your journey**: different data, different method, different signature risk. This is the replayability engine *and* the AI lesson.

| Model Card | What it does | Data it needs | Required METHOD | Signature RISK (its snake) |
|---|---|---|---|---|
| **Chatbot (LLM)** | Answers questions, chats | Massive **text** (web, books, Naija languages) | **Transformer** | **Hallucination**, bias, jailbreaks |
| **Voice / Text-to-Speech** | Reads text aloud in a voice | Paired **audio + text** across accents/languages | Neural TTS (transformer-based) | Robotic/odd output; **voice-clone misuse**; missing accents |
| **Image Generator** | Makes pictures from prompts | **Image + caption** pairs | **Diffusion** (or **GAN**) | **Copyright**, deepfakes, weird artefacts |
| **Vision Classifier** | Recognises things (e.g., crop disease, X-rays) | **Labelled images** | CNN / Vision Transformer | **Bias** (skin tone/region); fails on new data |
| **Recommender** | Suggests content / scores credit | **User behaviour / transactions** | Collaborative filtering / neural net | **Filter bubbles**; unfair credit; addiction |

*(Advanced expansion model cards: **GAN synthetic-data**, **multimodal**, **AI agent**. Not in the foundation.)*

**Why this is the heart of the design:** a Chatbot player hunts text data and must use a Transformer; an Image-Gen player hunts image-caption data and must use Diffusion or a GAN. **Players learn what different AIs are made of by having to build them differently.**

---

## 5. Where the training methods (Transformer / Diffusion / GAN) live

At **The Forge (Pretraining)** you must play a **Method card** that matches your model:

- **Transformer** → chatbots, text-to-speech (data-hungry, scalable).
- **Diffusion** → image generation (great quality, compute-heavy).
- **GAN** → image generation alt + synthetic data (cheaper, but *unstable* — an advanced-mode trade-off).
- **CNN / Vision Transformer** → vision classifiers.

Matching the **right** method = a **ladder**. A wrong/cheap method = a **snake** (weak model). In advanced mode, methods carry trade-offs (GAN cheap but can fail to train; Diffusion superb but needs more compute) so the *choice* itself becomes strategy.

---

## 6. Decision Cards — the "very intellectual" core you described

At key spaces you draw a **Decision Card**: a real building choice tied to your model, with branching outcomes. The "right" answer depends on your situation — that's the thinking.

```
DECISION — Your CHATBOT is hallucinating facts.
  (A) Collect more diverse, higher-quality data   → costs ₦ + time, but +Trust  [ladder]
  (B) Ship it now, fix later                       → fast, but −Trust            [snake]
  (C) Add retrieval (RAG) from trusted sources     → if you can afford it, big +Trust perk
```
```
DECISION — Cheap dataset is available but it's scraped from copyrighted sources.
  (A) Use it       → save ₦ now, risk a Lawsuit event later (−₦, back spaces)
  (B) License clean data → costs ₦, but safe + small Trust bonus
```

These cards are where **policy, safety, ethics, and market reaction** show up as consequences — and they're the easiest thing to expand endlessly (new cards = new content, including via future QR packs).

---

## 7. Perks / unlocks (the Monopoly-style upside)

Along the journey you collect **Perk tokens** that give lasting advantages — your reward for good decisions:

- **Clean Data Pipeline** — ignore one "bad data" snake.
- **Open-Source Base Model** — skip part of pretraining.
- **GPU Sponsor** — compute discount each turn.
- **Safety Team** — one free pass through the safety gate.
- **Star Researcher** — re-roll once per game.

Perks make the board feel like Monopoly (building an advantage), and reward understanding (you earn them by making the smart AI-building call).

---

## 8. How 5–10 people stay engaged

- **Up to 5:** individual tokens on the board.
- **6–10:** **teams of 2** (so 5 teams) — teammates debate each decision (great for class + family; debate = learning).
- **Anti-downtime:** Decision Cards are resolved quickly; while one team moves, others can be choosing their next purchase. (A fully **simultaneous** variant is a later option.)

---

## 9. A sample run (to feel it)

> **Ada picks the Image-Generator model.** In the **Data District** she licenses clean image-caption data (climbs a ladder, +Trust) instead of scraping (avoids a lawsuit snake). In **Compute City** a NEPA power-cut card hits — but she bought a **GPU Sponsor** perk, so she shrugs it off. At **The Forge** she plays **Diffusion** (correct method → ladder). A Decision Card asks whether to rush to market; she spends time on safety filters (+Trust). She launches a trusted product and scores high. *Meanwhile a rival who scraped data and skipped safety got hit by a copyright lawsuit and a deepfake scandal — two snakes — and limps to market with low Trust.* The lesson taught itself.

---

## 10. What's in the FOUNDATION vs. ADDED LATER

**Foundation (build + playtest this first):**
- The 6-zone board with ladders & snakes.
- 5 Model Cards; matching Data + Method requirements.
- ₦ Money, Data, Compute, Trust.
- Decision Cards (one starter deck).
- Perks.
- Win = first to a working launch.

**Added later (increase complexity as we go):**
- Trust/Quality **scoring** for a "best product" win (vs. simple race).
- **Method trade-offs** (GAN instability, Diffusion compute cost), hyperparameters.
- Compute-time **as the movement resource** (training takes real time).
- Player **competition** (poach data, block compute, talent wars).
- Deeper **ethics/policy** dilemmas with table voting.
- Advanced Model Cards (GAN synthetic data, multimodal, agents).
- QR-unlocked content packs (new decisions, new datasets, current events).

---

## 11. Questions to lock the foundation

1. **Win:** for the foundation, keep it a simple **race** ("first to launch wins"), and add the "best/most-trusted product" scoring later? (Recommended.)
2. **The board path:** one **shared path** everyone travels (simplest), or **different branches per model type** (richer, but more to design)? I'd suggest *shared path now, model-specific decisions on it* — branches later.
3. **Movement:** plain **die roll** for the foundation (familiar), swapping to "spend compute time" later?
4. **Next step:** want me to turn this foundation into a **print-and-cut prototype** — the board, ~5 Model Cards, Data/Method/Decision/Perk cards, and tokens — so you can photocopy it and actually play?
